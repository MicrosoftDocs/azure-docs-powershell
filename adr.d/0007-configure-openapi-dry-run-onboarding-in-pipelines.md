# ADR-0007: Configure reference dry-run onboarding in a shared pipeline

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

## Decision

Use one manual pipeline and reusable job template under `common/pipeline-yaml`.
Their parameters specify an
allowlisted implementation type, target HTTPS repository and branch, service
connection, and a type-specific configuration object. Do not accept arbitrary
script paths, commands, or injected steps as onboarding inputs.

Each supported type supplies checked-in setup and validation step templates.
The shared pipeline owns manual-only execution, the Windows agent, credential-free
checkout, and repository PowerShell tests. Adapters own pinned dependencies,
toolchain tests, configuration validation, and the authenticated non-publishing
validation entry point. Configuration crosses into PowerShell through JSON
environment variables, never executable script interpolation.

OpenAPI 3.2 is the first supported type, not an assertion that legacy toolchains
are dry-run safe. Its configuration contains services following ADR-0006. Every
service must explicitly set `dry_run: true`; publishing mode is rejected before
cloning. Keep its existing manual YAML as a thin compatibility wrapper.

The normal OpenAPI orchestrator also accepts a run-wide `-DryRun` switch.
Effective dry-run behavior is the switch OR the service's configured `dry_run`;
omitting the switch or passing `-DryRun:$false` preserves per-service behavior.
The switch never weakens a configured dry run, mutates configuration, or bypasses
the explicit Boolean requirement from ADR-0006. The validation harness passes
the switch as defense in depth while still requiring every service to opt in.
Forced runs use the same change reporting, failure restoration, and verification
as configured dry runs. This controls generation/restoration, not a separate
pipeline publishing task.

Clone the target with read-only shared authentication into a unique temporary
checkout. Pass the service configuration through a separate file outside that
checkout, without changing the target's `reference.config.yml`. Reuse the normal
orchestrator and generators. Verify the complete checkout's file hashes and
directory inventory (excluding Git internals), HEAD, Git status, and remotes
against their starting state, even after generation fails.

The pipeline has no push task. Retain the disposable checkout for diagnostics
until agent temporary-directory cleanup; delete the temporary configuration.
Source and target authentication requests remain read-only. Existing orchestration
callers continue to read the target's configuration by default.

Onboard another repo by adding configuration. Add code only for a genuinely new
implementation type, and prove its generation/restoration contract before
registering it in the allowlist. Reuse existing orchestration and safety helpers;
extract shared helpers when another adapter needs them rather than cloning them.

## Scope

**In scope:** Shared pipeline composition, type adapters, existing target
repository validation, configuration-driven repo onboarding, exact restoration
verification, and agent guidance for extending the pattern.

**Out of scope:** Publishing, provisioning pipeline definitions, docs-ui schema
validation, migrating other toolchains now, and replacing shared authentication.

## Options considered

- **Pipeline parameters and one runner (chosen)** — onboarding is data, not code.
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
- Pipeline definitions using the former Foundry YAML must select the shared
  pipeline or OpenAPI compatibility wrapper and supply explicit inputs.
- Registering a new type requires changes to the shared allowlist, both template
  selections, adapter tests, and documentation. Existing publishing stays separate.
- A clean validation proves local restoration, not downstream rendering or
  publishing readiness. Live access still requires appropriate read permissions.
