# ADR-0002: mdoc's reference-assembly closure is an explicit, centrally-declared build prerequisite

- **Status:** Proposed
- **Date:** 2026-08-27
- **Deciders:** Lyndon Swan — *co-signer needed: accountable service owner for this repo. Fill in before requesting acceptance.*
- **Tags:** pipeline, dotnet, mdoc, build-reliability

## Context

The **Azure .NET SDK - Bundle Job** (`apidrop`/`Content CI` definition 397, sourced from this repo at `refs/heads/master`) failed on every run for over two weeks — [Bug 1169371](https://ceapex.visualstudio.com/Engineering/_workitems/edit/1169371), reference [build 620935](https://apidrop.visualstudio.com/Content%20CI/_build/results?buildId=620935).

The proximate error: `mdoc` could not resolve `System.Net.ServerSentEvents, Version=10.0.0.0` while processing `System.ClientModel` 1.15.0, and `Mono.Cecil` threw `AssemblyResolutionException`.

What the investigation established, from the build log and the package itself:

- **All four** TFM assets of `System.ClientModel` 1.15.0 — `net10.0`, `net9.0`, `net8.0`, `netstandard2.0` — reference `System.Net.ServerSentEvents` at `10.0.0.0`. Which asset Nue selected is therefore irrelevant to the failure.
- That assembly ships **inbox in .NET 10** (present in `Microsoft.NETCore.App.Ref` 10.0.0 at exactly `10.0.0.0`). Accordingly the package's `net10.0` dependency group omits it, while the `net8.0`/`net9.0`/`netstandard2.0` groups declare it as `System.Net.ServerSentEvents 10.0.9`.
- Nue never staged it. The string appears **twice in 129,176 log lines**: once as a listed `9.0` dependency of an unrelated package, once in the exception.
- The only remaining source was the agent's targeting packs, and the agent had exactly **one**: `Microsoft.NETCore.App.Ref\3.1.0`.

The deeper cause is structural, not a missing package:

- mdoc's entire resolution closure is derived at runtime from `(Get-Command dotnet).Source` ([`dotnet/nuget-run.ps1`](../../dotnet/nuget-run.ps1) line 123, [`dotnet/run.ps1`](../../dotnet/run.ps1) line 127). What mdoc can resolve equals whatever SDKs happen to be installed on the agent.
- Those SDKs are installed by steps that exist for unrelated reasons and never declare themselves load-bearing. The single pack the build had came from a step named *"Use .NET Core sdk 3.x"*.
- The same six `-L` paths are duplicated verbatim in `nuget-run.ps1` (145–150) and `run.ps1` (137–142), fed by two templates using two different mechanisms: `UseDotNet@2 version: 3.x` versus a pinned array `@("3.1.426","6.0.203","8.0.307","9.0.100")` in an inline `dotnet-install.ps1` loop.
- The input floats while the toolchain is pinned: NuGet packages adopt new TFMs on their own schedule, so the build breaks with no change in this repo. This was already the **second** pipeline patched reactively for .NET 10 (PR 2320, Samples, June 2026).
- Failure surfaced roughly **70 minutes** into the run (05:54 → 07:05) as a Cecil stack trace naming a *type*, not a missing prerequisite.

## Decision

We will treat the .NET assembly set mdoc resolves against as an **explicit, declared prerequisite of the build** rather than an incidental side effect of unrelated SDK installs. Three mechanisms implement that single principle:

1. The required .NET is installed **deliberately**, with `packageType: runtime` and an `installationPath` matching the root the `-L` paths are derived from — in `common-steps-in-dotnet-nuget.yml`, the only template that needs it. **It must be the runtime, never the SDK.** The SDK's targeting pack is type-forwarding facades; on the same search path as the .NET Framework reference assemblies, the two forward the same type to each other and mdoc recurses until it dies with a `StackOverflowException` about an hour in.
2. The `-L` list is constructed **once**, by `Get-MdocDotNetSearchArgs` in `dotnet/common.ps1`, and consumed by both `run.ps1` and `nuget-run.ps1`.
3. That function **asserts** any .NET majors the caller declares — satisfied by either a targeting pack or a shared runtime — and fails with a named prerequisite. The requirement is **opt-in**: `nuget-run.ps1` declares major `10`; `run.ps1` declares nothing, because it is shared with `uwp/Run.ps1` whose agent uses a different dotnet root. A second, **advisory** check (`Test-MdocAssemblyReferences`) walks every staged assembly with Mono.Cecil — which ships alongside mdoc — and warns about any reference absent from every search path.

The two checks are deliberately asymmetric. A declared requirement is a fact about our own configuration, so it **fails the build**. Reference resolvability depends on what upstream packages did, and mdoc resolves lazily, so that check only **warns**.

The .NET 10 requirement for the nuget template is pinned by `tests/dotnet/pipeline-yaml.Tests.ps1`, not by a runtime default that shared callers would inherit.

### Verification

Reproduced and fixed locally against mdoc 5.9.7, the real `System.ClientModel` 1.15.0, and a `System.Runtime` facade — the same ingredients as the production loop:

| Case | Configuration | Result |
|---|---|---|
| A | 3.1 targeting pack only *(production)* | exit 1 — `Failed to resolve assembly: 'System.Net.ServerSentEvents, Version=10.0.0.0'` |
| B | \+ .NET 10 **targeting pack** | **exit -1073741571 (STATUS_STACK_OVERFLOW)**, 0 files |
| C | stage `System.Net.ServerSentEvents.dll` alone | exit 1 — fails on the *next* inbox assembly, `System.Text.Json 10.0.0.0` |
| D | \+ .NET 10 **shared runtime** | **exit 0**, 153 files, zero resolution failures |
| E vs F | same content, with and without the runtime | **0 files differ** — byte-identical output |

Case C is why single-assembly staging was rejected: the net10.0 asset needs several inbox assemblies, and fixing them one at a time only reveals the next. Case E/F is why adding the runtime is safe for existing content.

## Scope

**In scope:** how mdoc obtains reference assemblies for the `dotnet` and `dotnet-nuget` pipelines.

**Out of scope:** which TFM asset Nue selects from a package — Nue is pinned external tooling (`Nue 1.2.3398.86`) and asset selection changes the documented API surface, which is a content decision, not an infrastructure one. Also out of scope: whether to keep pinning SDK majors at all (see follow-ups).

## Options considered

- **Install the .NET 10 runtime into the existing dotnet root, then centralise and assert (chosen)** — supplies every inbox assembly at once, provably without changing existing output, and removes the "fixed it in one of two identical places" failure mode.
- **Install the .NET 10 SDK** — rejected, and measured. Its targeting pack facades create type-forward cycles with the .NET Framework reference assemblies already on the search path; mdoc stack-overflows roughly an hour in. This was tried first and broke both .NET pipelines (builds 624459 and 624460).
- **Stage only the specific missing assembly** — rejected. Case C above: `System.ClientModel`'s net10.0 asset needs several inbox assemblies, so this is whack-a-mole with a ~70-minute feedback loop per round.
- **Omitting `installationPath`** (as PR 2320 did) — rejected. `UseDotNet@2` then installs to the agent tool cache and prepends it to `PATH`, repointing `(Get-Command dotnet).Source` and orphaning everything else.
- **Add `System.Net.ServerSentEvents` to the bundle package list** — rejected. That list lives in `Azure/azure-docs-sdk-dotnet`, not here, and it has case C's problem too.
- **Pin Nue to an older TFM** — rejected, as out of scope above.
- **Continue patching reactively per pipeline** — rejected. This is the status quo; it had already recurred once and cost two weeks of broken `main`.

## Consequences

- **Positive:** the resolution closure becomes declared rather than emergent; one place to change it; the failure mode becomes a named prerequisite at minute 2 instead of a Cecil stack trace at minute 70.
- **Verified neutral:** adding the .NET 10 runtime leaves existing generated XML byte-identical (case E/F above), so this carries no content risk.
- **Learned the hard way, twice.** The first form of the prerequisite check *defaulted* to requiring majors 3 and 10, which failed `[Regression Test][UWP] winrt-api-build` — a working pipeline, because `uwp/Run.ps1` also calls `run.ps1` and its agent resolves `dotnet` to `C:\ToolCache\dotnet` with only the 8.0 pack. A shared helper must not carry one caller's environment assumption as a default. The second form installed the .NET 10 **SDK**, whose targeting pack facades stack-overflowed mdoc in both .NET pipelines. Both were caught by PR validation, and both came from changing more than the failure required.
- **Scope discipline:** `common-steps-in-dotnet-dll.yml` is deliberately left alone. It does not need .NET 10, and speculatively adding it is what produced build 624459's overflow. It will need this treatment when a DLL-sourced package first references a .NET 10 inbox assembly — at which point the advisory scan will name it.
- **Trade-off:** the advisory scan reads every staged assembly and enumerates the search paths, adding a few minutes to a build that already runs over an hour. It matches on name only, ignoring version, because Cecil tolerates version drift but cannot invent a missing file.
- **Follow-up:** `10.0.x` is a pin. This recurs when packages adopt `net11.0`, preceded by a warning that names the assembly.
