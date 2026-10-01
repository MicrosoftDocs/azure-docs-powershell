# ADR-0004: Centralize NuGet pipeline steps in one template

- **Status:** Proposed
- **Date:** 2026-08-28
- **Deciders:** Lyndon Swan — *co-signer needed: accountable service owner for this repo. Fill in before requesting acceptance.*
- **Tags:** pipeline, dotnet, build-reliability

## Context

ADR-0003 found that `nuget-run.ps1` had three YAML callers. Two duplicated the setup in `common-steps-in-dotnet-nuget.yml`: the archive flow used `common-steps-in-dotnet-archive-nuget.yml`, and the v2 flow embedded the steps directly. When .NET 10 became a prerequisite, the shared template was updated while both copies were missed.

The archive template has exactly one caller, `azure-sdk-dotnet-archive-steps.yml`. Its steps are equivalent to the shared template except that it intentionally does not publish the `binaries` pipeline artifact. The v2 pipeline is an ordinary root pipeline whose steps duplicate the shared template's default behavior.

The two bypassing flows do not have PR build validation. A test can detect drift, but a single source of truth makes the prerequisite structural rather than merely asserted.

## Decision

We will make `common-steps-in-dotnet-nuget.yml` the only template that invokes `nuget-run.ps1`.

- `ReferenceAutomation-Yaml_dotnet-nuget-v2.yml` uses the shared template directly after its checkout.
- `azure-sdk-dotnet-archive-steps.yml` uses the shared template directly and passes `PublishPipelineArtifact: false`.
- The shared template's `PublishPipelineArtifact` boolean defaults to `true`, preserving existing callers' behavior.
- `common-steps-in-dotnet-archive-nuget.yml` is deleted.

`tests/dotnet/pipeline-yaml.Tests.ps1` enforces the structure: exactly one direct `nuget-run.ps1` invocation, both former bypassers reference the shared template, and the archive flow retains its artifact opt-out.

## Scope

**In scope:** the shared NuGet pipeline setup, the archive and v2 consumers, and tests that prevent their divergence.

**Out of scope:** changing the target repositories, manually queuing production pipelines, or consolidating other language pipeline templates.

## Options considered

- **One shared template with an artifact opt-out (chosen)** — removes duplicate prerequisite and execution steps while preserving the archive flow's sole behavioral difference.
- **Keep the duplicate templates and test all callers** — safer than the prior state, but every shared prerequisite remains a multi-file mutation by construction.
- **Keep an archive wrapper that forwards parameters to the shared template** — avoids a deletion but adds an indirection with no behavior; it has one caller and no independent responsibility.
- **Manually run both bypassing production definitions for validation** — rejected. Their `CI.push.ps1` step writes to configured target branches unless the build is a real pull-request run; that is a production operation, not a safe test.

## Consequences

- **Positive:** .NET prerequisites and mdoc invocation now have one source of truth; a future direct caller fails the structural regression test.
- **Positive:** the archive flow continues to omit the `binaries` artifact explicitly rather than by carrying a duplicate template.
- **Trade-off:** changes to the shared template affect more pipelines and require deliberate validation. PR 2390's existing regression builds validate the shared template; the test protects the two flows without a build policy.
- **Follow-up:** add PR-safe validation coverage for the archive and v2 definitions, so their full YAML compilation is checked without invoking `CI.push.ps1`.