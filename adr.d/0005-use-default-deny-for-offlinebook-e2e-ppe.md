# ADR-0005: Use Default Deny for OfflineBook E2E PPE

- **Status:** Proposed
- **Date:** 2026-09-09
- **Deciders:** Osmond Jiang — accountable owner
- **Tags:** pipeline, security, network-isolation, offlinebook

## Context

The `E2ETesting_OfflineBook_Reference_PPE` pipeline extends the 1ES unofficial
pipeline template, which injects the network-isolation task. Build 626395 ran
that task in enforcement mode but selected the `Permissive` policy from the
pipeline policy map. That policy allows general Internet access and does not
satisfy the SFI-ES4.2.4 Default Deny requirement.

The 1ES template supports selecting a policy through
`settings.networkIsolationPolicy`.

## Decision

We will explicitly select the `DefaultDeny` network-isolation policy in
`OfflineBook/azure-pipelines-e2etest-ppe.yml`.

## Scope

**In scope:** the PPE end-to-end OfflineBook pipeline definition.

**Out of scope:** the production end-to-end pipeline, the regular OfflineBook
pipelines, and changes to the centrally managed network-isolation allowlists.

## Options considered

- **Set `settings.networkIsolationPolicy` to `DefaultDeny` (chosen)** — uses the
  supported 1ES template contract and makes the required policy visible in
  source control.
- **Keep the policy-map-provided `Permissive` policy** — rejected because it
  allows general Internet access and leaves the S360 action item unresolved.
- **Add firewall rules in pipeline steps** — rejected because they would
  duplicate and potentially conflict with centrally managed 1ES network
  isolation.

## Consequences

- **Positive:** outbound connections not covered by the selected policy are
  denied for this pipeline's agent jobs.
- **Positive:** a Pester regression test prevents the pipeline from silently
  returning to an implicit or permissive policy.
- **Trade-off:** endpoints required by OfflineBook automation must be present in
  the centrally managed policy; missing endpoints will fail pipeline tasks and
  require an allowlist request.
