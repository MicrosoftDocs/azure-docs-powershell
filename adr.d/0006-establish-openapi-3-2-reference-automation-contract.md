# ADR-0006: Establish an isolated OpenAPI 3.2 reference automation contract

- **Status:** Accepted
- **Date:** 2026-10-13
- **Deciders:** Will Bjorn — engineering lead
- **Tags:** pipeline, rest, openapi, generation, publishing-safety

Stakeholder acceptance was confirmed during implementation planning. The
entry-point and fail-closed filesystem refinements below were also confirmed
before Changeset 3 implementation.

## Context

ReferenceAutomation needs to productionize an existing OpenAPI 3.2 proof of
concept and orchestrate it from content-repository configuration. The
repository already has a legacy REST toolchain, shared target-repository pull
and push scripts, and Windows PowerShell 5.1 pipeline entry points. The new
flow must reuse the safe shared Git behavior without coupling OpenAPI 3.2
generation to the legacy REST preprocessor or changing existing REST
pipelines.

The legacy preprocessor cannot serve as a read-only configuration adapter. It
assumes the legacy REST configuration shape, rewrites
`reference.config.yml`, and deletes configured output. Windows PowerShell 5.1
also has no native YAML parser, while adding an unpinned PowerShell module
would make pipeline behavior depend on an external installation.

Generation introduces additional repository-safety concerns:

- a service must clean up stale generated pages without deleting adjacent
  authored content;
- multiple services can share one target repository, so their output
  boundaries cannot overlap;
- a dry run must execute the real generator and report its diff without
  leaving tracked or newly created files behind;
- a later service failure must prevent publishing changes retained by an
  earlier service;
- pull-request validation must never reach a task capable of pushing; and
- concurrent writers must not silently overwrite each other's commits.

The detailed implementation and validation contracts are maintained in the
[revised OpenAPI 3.2 implementation
plan](../openapi32-reference-automation-implementation-plan-revised.md). This
record establishes the architectural and safety decisions that the
implementation must preserve.

## Decision

We will implement OpenAPI 3.2 reference generation as an isolated
`REST/openapi32` toolchain with explicit configuration, generation,
orchestration, and publishing boundaries.

### Components and configuration

- A separate `openapi_reference.services` block will configure the new
  toolchain. The legacy REST configuration and entry points remain unchanged.
- A dedicated Node 22 adapter backed by the toolchain's pinned `js-yaml`
  dependency will read the YAML and emit `openapi_reference` as JSON. It will
  not mutate files, clone repositories, run generators, or make publishing
  decisions.
- The page and TOC generators will own OpenAPI transformation and generated
  structure validation. They will not know about Azure Pipelines parameters,
  Git repositories, branches, or publishing.
- The Windows PowerShell orchestrator will own service validation, path
  containment, source acquisition, process execution, change reporting, and
  dry-run restoration. It will reuse the existing branch, clone,
  authentication, target-repository pull, and target-repository push helpers.
- Its entry point will accept the existing `-paramsJson` / `-paramsJsonFile`
  convention and resolve `target_repo.repo_root`. An explicit
  `-TargetRepoRoot` override will support local execution without cloning the
  target or publishing. Target pull and push remain separate pipeline steps.
- The pipeline will not perform docs-ui schema validation. Generator
  validation is limited to the generated page set's internal consistency.

### Build Service environment selection for fork validation

- Source authentication accepts an explicit `auto`, `prod`, or `ppe` Build
  Service environment at the orchestration entry point, not in source-controlled
  content-repository configuration.
- `auto` remains the default and preserves the shared helper's existing
  `OPS-E2E-PPE` repository routing. Existing callers retain their behavior.
- The isolated manual fork-validation pipeline explicitly selects `ppe` to use
  the Learn Build Service Test app installed on the fork. Both the token
  endpoint and Entra resource ID must use the selected environment.
- App installation and authorization of the pipeline identity to the selected
  backend are separate prerequisites. Authentication failures must stop the
  run without falling back to production, anonymous access, or another credential.

### Service contract and failure policy

- `format` must be the exact value `openapi3.2`.
- Every service must specify an explicit Boolean `dry_run`.
- A missing or empty service collection is an error.
- `output_repo` is reserved but unsupported; its presence is an error.
- All service configurations and output boundaries will be validated before
  any clone or generation begins.
- One invalid or failed service fails the complete run. The push task runs only
  after successful orchestration, so retained changes from an earlier service
  are not published after a later failure.

### Output ownership and path safety

- Configured source and output paths must be relative and must remain within
  their canonical repository roots using separator-aware,
  case-insensitive Windows path comparisons.
- The target repository root, `.git`, and `docs-ref-autogen` are protected
  output locations.
- Identical output folders and ancestor/descendant output folders are
  rejected, including paths that differ only by case or separator spelling.
- Source paths are checked in the source checkout, not the unrelated target
  checkout. Source and output paths with reparse-point ancestors are rejected;
  output traversal also rejects nested reparse points and repositories.
- Dirty tracked files, untracked files, and ignored content inside a service
  output boundary cause failure before generation, for both dry-run and
  non-dry-run services. Clean tracked authored files and pre-existing empty
  directories are allowed; unrelated changes outside the boundary are allowed.
- Output files and directories are inventoried before source acquisition and
  rechecked immediately before generation. Temporary source cleanup does not
  follow repository-supplied links.
- Before generation, the generator removes only files bearing an OpenAPI 3.2
  generated MIME type and the service output's `toc.yml`.
- `toc.yml` is generator-owned within each configured service output folder.
  Adjacent Markdown and unrelated YAML remain author-owned and must be
  preserved.

### Validation and dry runs

- Duplicate generated UIDs and output paths are errors.
- Generator-created internal xrefs must resolve within the complete generated
  service page set. External xrefs remain available for downstream
  resolution.
- The generated TOC UID set and page UID set must match.
- Unsupported source constructs produce aggregated Azure Pipelines warnings
  rather than silent omission.
- A dry run executes normal page and TOC generation, reports created,
  modified, and deleted paths, restores tracked changes, removes only
  untracked paths introduced by that service, and verifies that the
  path-scoped state matches its pre-service state.
- Verification includes file hashes and the complete file/directory set, not
  only Git status. Restoration failures are reported alongside an original
  generation failure rather than hiding either error.
- Dry-run restoration runs even when generation fails. Unexpected
  pre-existing changes beneath a service output boundary cause failure rather
  than being absorbed or overwritten.

### Publishing safety

- The push task condition will require both a successful build and a
  non-pull-request build. Existing script-level pull-request and `live` branch
  checks remain defense in depth.
- Existing rebase and `--force-with-lease` behavior remains the concurrency
  boundary. A stale lease may fail the run explicitly; the OpenAPI toolchain
  will not add an automatic second fetch/rebase/push cycle.

## Scope

**In scope:** OpenAPI 3.2 generator ownership and validation, the
`openapi_reference` configuration contract, multi-service orchestration,
Windows path and output isolation, dry-run semantics, pull-request publishing
protection, and interaction with the existing shared Git publishing flow.

**Out of scope:** TypeSpec, Foundry-specific defaults, content-repository
onboarding, support for `output_repo`, docs-ui schema validation, automatic
stale-lease recovery, atomic standalone generator writes, and changes to
legacy `REST/run.ps1` or its pipeline templates.

## Options considered

- **Isolated OpenAPI 3.2 toolchain with explicit safety contracts (chosen)** —
  separates new behavior from the legacy REST flow, pins YAML parsing with the
  generator dependencies, and makes multi-service output and publishing
  behavior testable.
- **Extend the legacy REST preprocessor and pipeline** — rejected because the
  preprocessor mutates configuration and output, carries assumptions unrelated
  to OpenAPI 3.2, and would increase regression risk for existing REST
  pipelines.
- **Parse YAML directly in Windows PowerShell** — rejected because Windows
  PowerShell 5.1 has no native YAML parser. An externally installed module
  would introduce an additional unpinned runtime dependency, while a custom
  parser would duplicate mature YAML behavior.
- **Allow optional `dry_run` with a default** — rejected because an implicit
  default can unexpectedly publish or unexpectedly discard generated changes.
  Each service must state its publishing intent.
- **Allow nested output folders and process services in order** — rejected
  because cleanup and dry-run restoration in one service could delete or
  revert another service's output.
- **Clean the complete output folder** — rejected because service folders may
  contain adjacent authored Markdown or unrelated YAML. Cleanup is limited to
  identifiable generated pages and the reserved TOC.
- **Require every xref to resolve locally** — rejected because valid external
  xrefs are resolved downstream and are not evidence of a broken generated
  page set.
- **Copy the legacy REST push-task condition** — rejected because its
  repository-specific exception can allow the push task to run during a
  ReferenceAutomation pull request.
- **Automatically retry after a stale push lease** — rejected for this
  changeset. The existing lease prevents silent overwrite; adding another
  concurrency loop to shared publishing behavior requires separate design and
  validation.
- **Implement `output_repo` immediately** — rejected because it changes clone,
  authentication, output-containment, and publishing ownership beyond the
  approved orchestration scope.

## Consequences

- **Positive:** the new flow can evolve without changing or destabilizing the
  legacy REST implementation.
- **Positive:** configuration parsing is deterministic, pinned, and read-only.
- **Positive:** validate-all-before-work, fail-whole-run behavior, and a
  success-gated push prevent partial multi-service publication.
- **Positive:** output isolation and MIME-scoped cleanup preserve authored
  content and make dry-run restoration safe.
- **Positive:** pull requests cannot execute the push task, while existing
  script checks provide a second protection layer.
- **Positive:** duplicate identities, broken internal links, and page/TOC
  drift fail before publication; unsupported constructs remain visible as
  warnings.
- **Trade-off:** every service must provide more explicit configuration,
  including `dry_run`, and overlapping outputs that could be made to work
  sequentially are intentionally unsupported.
- **Trade-off:** `toc.yml` cannot be hand-authored inside a configured service
  output folder.
- **Trade-off:** a concurrent push after rebase can fail the pipeline and
  require a rerun, even though no newer commit is overwritten.
- **Risk:** cleanup depends on the generated MIME marker remaining a stable
  ownership signal; regression tests must protect that boundary.
- **Risk:** Windows path rules are easy to weaken accidentally; tests must
  cover traversal, case variants, separator variants, protected paths, and
  sibling-prefix paths.
- **Follow-up:** implement the contracts and CI coverage described in the
  revised implementation plan, then separately onboard Microsoft Foundry in
  dry-run mode and confirm its approved generated-output baseline.
