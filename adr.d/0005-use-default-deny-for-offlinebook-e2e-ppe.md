# ADR-0005: Use Default Deny for OfflineBook E2E PPE

- **Status:** Proposed
- **Date:** 2026-09-09
- **Deciders:** Osmond Jiang — accountable owner
- **Tags:** pipeline, security, network-isolation, offlinebook

## Context

The `E2ETesting_OfflineBook_Reference_PPE` and
`E2ETesting_OfflineBook_Conceptual_PPE` pipelines share the 1ES unofficial
pipeline template in `OfflineBook/azure-pipelines-e2etest-ppe.yml`, which
injects the network-isolation task. Builds 626395 and 626394 selected the
`Permissive` policy from the pipeline policy map. That policy allows general
Internet access and does not satisfy the SFI-ES4.2.4 Default Deny requirement.

The 1ES template supports selecting a policy through
`settings.networkIsolationPolicy`. The network-isolation report for conceptual
build 626394 identified `offlinebook-pubdev.azurefd.net`, the PPE OfflineBook
service configured by the pipeline, as its only default-deny violation.

## Decision

We will explicitly select the `DefaultDeny` network-isolation policy in
`OfflineBook/azure-pipelines-e2etest-ppe.yml` and allow the observed
`offlinebook-pubdev.azurefd.net` endpoint in addition to the platform policy.

## Scope

**In scope:** the shared PPE end-to-end OfflineBook pipeline definition and
regression coverage for its network-isolation settings.

**Out of scope:** the production end-to-end pipeline, the regular OfflineBook
pipelines, service-side network configuration, and changes to the centrally
managed network-isolation allowlists.

## Options considered

- **Default deny with one exact-domain exception (chosen)** — uses the
  supported 1ES template contract, meets the S360 requirement, and preserves
  the conceptual pipeline's required connection to its PPE service.
- **Default deny without an exception** — blocks the service call observed in
  conceptual build 626394.
- **Keep the policy-map-provided `Permissive` policy** — rejected because it
  allows general Internet access and leaves the S360 action item unresolved.
- **Allow all Azure Front Door endpoints** — broader than the observed
  requirement and weakens least-privilege isolation.

## Consequences

- **Positive:** outbound connections not covered by the selected policy are
  denied for this pipeline's agent jobs.
- **Positive:** a Pester regression test prevents the pipeline from silently
  returning to an implicit or permissive policy or adding broad exceptions.
- **Trade-off:** new required external endpoints must be reviewed and added
  explicitly.
- **Risk:** runtime endpoint changes can fail the pipeline until the allowlist
  is updated.
