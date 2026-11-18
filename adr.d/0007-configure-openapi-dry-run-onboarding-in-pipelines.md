# ADR-0007: Configure reference dry-run onboarding in an OpenAPI-local pipeline

- **Status:** Proposed
- **Date:** 2026-10-26
- **Deciders:** Pending engineering lead approval
- **Tags:** pipeline, onboarding, publishing-safety, openapi

## Context

The Foundry validation harness embeds one source and a synthetic target in
PowerShell. Repo owners need to test integrations against existing docs content
without adding a script per integration or changing remote repositories.
ADR-0006 defines generation and restoration but leaves onboarding out of scope.
Other implementation types need the same onboarding pattern without copying a
complete pipeline or assuming that every type has OpenAPI services.
Changes under `common/pipeline-yaml` trigger unrelated validation pipelines,
whose failures should not block introducing the OpenAPI dry-run workflow.

## Decision

Use one manual pipeline and reusable job template under
`REST/openapi32/pipeline-yaml`. Keep this PR's pipeline changes out of
`common/pipeline-yaml`; revisit the shared location when another implementation
needs the pattern.
Their parameters specify an
allowlisted implementation type, service connection, and a type-specific
configuration object. Do not accept arbitrary
script paths, commands, or injected steps as onboarding inputs.

The manual entry points select `openapi3.2` internally rather than exposing a
single-choice implementation parameter. The reusable template retains its
allowlisted selector and multi-service configuration. Both manual entry points
expose scalar `sourceRepo`, `sourceBranch`, `sourceFile`, `uid`, and
`outputFolder` alongside target/authentication inputs. They construct one
service with fixed `dry_run: true`; branches default to `main`. Manual callers
previously passing `services` or `configuration` must migrate to these scalar
inputs, or extend the reusable template for multiple services.
Within OpenAPI configuration, every service owns `target_repo` and
`target_branch` alongside source inputs and `output_folder`. The scalar manual
wrappers map their target parameters into that service object. The reusable
template and validation script no longer accept a separate shared target.
Validate all entries (including non-publishing mode, target/source URLs,
branches, required fields, and lexical path containment) before cloning.
Execute entries sequentially in independent disposable target checkouts,
including entries using the same repository or branch, and stop on first failure.
Identities/output paths need not be unique across independently validated targets.
This proves each integration's restoration, not a combined publish operation.
The normal orchestrator retains its existing shared-target contract.
The per-target helper accepts one parsed service object and reads its target
repository/branch directly. JSON serialization is reserved for external
configuration, not calls between validation helpers.
At the OpenAPI pipeline boundary only, omitted service
`format` is supplied as `openapi3.2` and omitted diagnostic `name` is supplied
from `uid`. Explicit values are preserved for normal validation. The UID remains
a required, non-empty string so generated identities match the intended
published configuration. This adapter normalization preserves ADR-0006's
complete, explicit service contract for direct orchestrator/generator callers.

Each supported type supplies checked-in setup and validation step templates.
The reusable pipeline owns manual-only execution by default, the Windows agent, credential-free
checkout, and repository PowerShell tests. Adapters own pinned dependencies,
toolchain tests, configuration validation, and the authenticated non-publishing
validation entry point. Configuration crosses into PowerShell through JSON
environment variables, never executable script interpolation.

OpenAPI 3.2 is the first supported type, not an assertion that legacy toolchains
are dry-run safe. Its configuration contains services following ADR-0006. Every
service must explicitly set `dry_run: true`; publishing mode is rejected before
cloning. Keep both manual YAML entry points as thin single-service wrappers.
Azure Pipelines can expand Boolean object values as the string `"True"`. The
OpenAPI pipeline adapter normalizes only that exact representation to Boolean
`true` before invoking the validation script. Direct script inputs retain strict
Boolean validation; false, missing, and other string values remain rejected.

The normal OpenAPI orchestrator also accepts a run-wide `-DryRun` switch.
Effective dry-run behavior is the switch OR the service's configured `dry_run`;
omitting the switch or passing `-DryRun:$false` preserves per-service behavior.
The switch never weakens a configured dry run, mutates configuration, or bypasses
the explicit Boolean requirement from ADR-0006. The validation harness passes
the switch as defense in depth while still requiring every service to opt in.
Forced runs use the same change reporting, failure restoration, and verification
as configured dry runs. This controls generation/restoration, not a separate
pipeline publishing task.

Clone each service's target with read-only shared authentication into a unique temporary
checkout. Pass the service configuration through a separate file outside that
checkout, without changing the target's `reference.config.yml`. Reuse the normal
orchestrator and generators. Verify the complete checkout's file hashes and
directory inventory (excluding Git internals), HEAD, Git status, and remotes
against their starting state, even after generation fails.

The pipeline has no push task. Delete successful disposable checkouts only after
generation and complete restoration verification succeed. Cleanup failures are
errors, never silently ignored. Retain failed checkouts at their logged paths
for diagnostics until agent temporary-directory cleanup; delete temporary
configuration on both generation success and failure. Return a single completion
object with Boolean `Completed = $true` and `ServiceCount` only after all services
and successful-checkout cleanup finish.
Source and target authentication requests remain read-only. Existing orchestration
callers continue to read the target's configuration by default.

Onboard another repo by adding configuration. Add code only for a genuinely new
implementation type, and prove its generation/restoration contract before
registering it in the allowlist. Reuse existing orchestration and safety helpers;
extract shared helpers when another adapter needs them rather than cloning them.

Scheduled branch publication is a separate publishing workflow governed by
proposed ADR-0011. It does not change this manual-only, read-only contract.

## Scope

**In scope:** OpenAPI-local reusable pipeline composition, type adapters, existing target
repository validation, configuration-driven repo onboarding, exact restoration
verification, and agent guidance for extending the pattern.

**Out of scope:** Publishing, provisioning pipeline definitions, docs-ui schema
validation, migrating other toolchains now, and replacing shared authentication.

## Options considered

- **Pipeline parameters and one runner (chosen)** — onboarding is data, not code.
- **Place templates under `common/pipeline-yaml` now** — deferred to avoid
  unrelated path-scoped validation while only OpenAPI 3.2 uses the workflow.
- **Arbitrary script or step parameters** — rejected because configuration could
  bypass the reviewed non-publishing adapter boundary.
- **Copy the whole pipeline per type** — rejected because manual-only and
  authentication/test gates would drift.
- **Per-repo PowerShell harnesses** — duplicate safety logic and obscure inputs.
- **Rewrite target configuration before running** — unnecessarily mutates the
  repository under validation and complicates restoration.

## Consequences

- New integrations need YAML changes or queue-time inputs, not new scripts.
- Existing authored content and real stale generated files participate in testing.
- Pipeline definitions using the former Foundry YAML must select the OpenAPI-local
  pipeline or OpenAPI compatibility wrapper and supply explicit inputs.
- Registering a new type requires reviewing the pipeline location and changes
  to the allowlist, both template
  selections, adapter tests, and documentation. Existing publishing stays separate.
- A clean validation proves local restoration, not downstream rendering or
  publishing readiness. Live access still requires appropriate read permissions.
