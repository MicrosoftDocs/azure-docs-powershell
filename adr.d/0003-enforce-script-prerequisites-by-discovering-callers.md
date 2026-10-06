# ADR-0003: Enforce a script's environment prerequisites by discovering its callers

- **Status:** Proposed
- **Date:** 2026-08-28
- **Deciders:** Lyndon Swan — *co-signer needed: accountable service owner for this repo. Fill in before requesting acceptance.*
- **Tags:** pipeline, testing, build-reliability

## Context

[ADR-0002](0002-declare-mdoc-reference-assemblies-as-a-build-prerequisite.md) established that a script needing a particular .NET version declares it, and that the declaration belongs to *"a caller that knows every pipeline consuming it"*. `dotnet/nuget-run.ps1` duly declared `-requiredDotNetMajors @('10')`, justified by a comment asserting that every consumer went through `common-steps-in-dotnet-nuget.yml`.

That assertion was false. Three YAML files invoke `nuget-run.ps1`, and two bypass the shared template entirely:

| File | Installed .NET before this change |
|---|---|
| `common-steps-in-dotnet-nuget.yml` | 3.x + 10 runtime |
| `common-steps-in-dotnet-archive-nuget.yml` | **3.x only** |
| `ReferenceAutomation-Yaml_dotnet-nuget-v2.yml` | **3.x only** |

Both would have failed in `Get-MdocDotNetSearchArgs` on any agent without a preinstalled .NET 10, making behaviour agent-dependent again — the precise property ADR-0002 set out to remove.

The regression guard did not catch it because the guard was written against the *template*, not the *script*. The list was hardcoded, and it was hardcoded from the same mistaken belief as the comment.

This is the third instance of one error class in the same work:

1. `Get-MdocDotNetSearchArgs` defaulted to requiring majors 3 and 10, which broke `uwp/Run.ps1` — a second caller of `run.ps1` nobody had enumerated (build 624430).
2. The .NET 10 **SDK** was installed to obtain one assembly, which stack-overflowed mdoc (builds 624459, 624460).
3. This one: consumers of `nuget-run.ps1` enumerated by reading one template.

Each time the fix was correct for the callers that were known, and wrong for a caller that was not. Aggravating the risk, neither bypassing pipeline has a build-validation policy on pull requests, so CI cannot catch a mistake in them at review time.

## Decision

We will enforce a shared script's environment prerequisites with a test that **discovers its callers by scanning the repository**, never with a hand-maintained list.

Concretely, for `nuget-run.ps1`: `tests/dotnet/pipeline-yaml.Tests.ps1` scans every `*.yml` in the repository for a direct invocation and asserts that the shared `common-steps-in-dotnet-nuget.yml` template is the **only** such caller. The two former bypassing roots are required to route through that template. A future direct caller therefore fails the test immediately instead of inheriting an unverified environment.

A caller-specific requirement stays opt-in, as ADR-0002 requires. What changes is that the claim *"these are all the callers"* is now computed rather than believed.

## Scope

**In scope:** how a hard environment prerequisite declared by a shared script is verified against the pipelines that invoke it.

**Out of scope:** the structural consolidation itself, which is governed separately by [ADR-0004](0004-centralize-nuget-pipeline-steps.md).

## Options considered

- **Discover callers in the test (chosen)** — a new consumer is covered the moment it is added, with no one needing to remember. It removes the class of error, not the instance.
- **Keep a hardcoded list and extend it** — rejected. This is what failed. A list is only correct until the next pipeline is added, and nothing signals when that happens.
- **Drop the hard requirement and rely on the advisory scan** — rejected. The requirement is real and trivially satisfied; downgrading it returns the failure to minute 70 as a Cecil stack trace, which is what ADR-0002 exists to prevent.
- **Consolidate every consumer onto the shared template** — chosen separately by ADR-0004 after the archive and v2 step sequences were compared and the archive's only behavioral difference (artifact publishing) was isolated.

## Consequences

- **Positive:** the "have we found all the callers?" question is answered by the test run rather than by someone's memory. The same pattern can be applied to any future shared-script prerequisite.
- **Positive:** the guard prevents any new direct caller from bypassing the shared prerequisite, and ADR-0004 makes the existing prerequisite structural rather than merely tested.
- **Trade-off:** the test reads every `*.yml` in the repository on each run. Cheap today; if it becomes slow, scope it to the folders that hold pipeline definitions rather than reverting to a list.
- **Limitation:** discovery matches on the literal script name in YAML. A pipeline that invoked the script indirectly — through a variable, or a wrapper script — would not be found. No such consumer exists today.
- **Implemented follow-up:** ADR-0004 consolidates `common-steps-in-dotnet-archive-nuget.yml` and `ReferenceAutomation-Yaml_dotnet-nuget-v2.yml` onto the shared template.
