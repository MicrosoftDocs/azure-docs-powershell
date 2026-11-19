# ADR-0009: Align OpenAPI generator output with the Test baseline

- **Status:** Proposed
- **Date:** 2026-11-03
- **Deciders:** Pending engineering lead approval
- **Tags:** openapi, generation, output-compatibility

## Context

The Test repository's `test/openapi32/generate-pages.mjs` evolved beyond the
productionized copy. Identical Foundry source and UID produced 284 output files
in each toolchain, all byte-different. Prose fields, dictionary projections,
nullable descriptions, unsupported media fields, and the TOC comment drifted.

The user requested alignment with that source generator, retained full-spec
generation without manifest support, and approved matching the smoke-test UID
default to `microsoft-foundry.openapi-3-2`.

## Decision

Align the production page transformation and TOC bytes with the baseline:

- Use summary for normalized prose and extendedSummary for service overview;
  preserve generated metadata.description and operation code-sample scenarios.
- Retain outer descriptions on collapsed nullable wrappers, expose typed
  additionalProperties as index-signature entries alongside named properties,
  and use any for unconstrained union branch labels.
- Omit unsupported media example/examples and encoding fields with aggregated
  warnings. Do not remove the source specification or code-sample scenarios.
- Do not author toc_rel in generated pages. Match the baseline TOC formatting,
  comment, UID references, and tag/path/method ordering.
- Preserve schema defaults through reference resolution and nullable-wrapper
  collapse, preferring the outermost authored default. Retain default-only
  shapes and serialize defaults losslessly rather than as normalized prose.
  Do not substitute schema examples for defaults. This also applies to
  server-variable default serialization. Exclude arbitrary default payloads
  from generated identity/xref discovery, even when payload keys are named
  `uid` or end in `Uid`; generated references outside defaults remain validated.

Preserve accepted ADR-0006: explicit inputs, pinned dependencies, MIME-scoped
cleanup, complete UID/path/internal-xref checks, warning aggregation, and
orchestrator-owned restoration. Do not copy the POC's dependency fallback,
optional cleanup, generator dry-run flag, or unchecked writes.

Keep full-spec operationId-derived filenames and UIDs. The Test representative
manifest selects 25 operations with authored identity/server overrides; those
are not the default transformation contract and remain unsupported here.
The new smoke-test UID default matches the baseline service prefix, but does
not reinterpret manifest-authored operation identities or migrate existing
queued runs.

Do not introduce a runtime dependency on an adjacent Test checkout or execute
source-repository generators. Capture a small baseline-generated page/TOC
fixture in this repository for byte-level regression tests.
Pin expected YAML to LF using fixture-local Git attributes so Windows checkout
conversion cannot introduce false byte differences. Keep strict output-byte
comparison rather than normalizing generated output in the assertion.

## Evidence and provenance

Baseline files captured from the local Test checkout on 2026-11-03:

| File | SHA256 |
| --- | --- |
| test/openapi32/generate-pages.mjs | 023F63C65929361DE4F2A78B721058BC3C0B6454A8E49917812087DEC0CA9FE3 |
| test/openapi32/generate-toc.mjs | EFE4C8BBE6D467708EC0F3F32F95DAEAF8F938BFD784D9606D3CCADAE3D0FBE8 |

After alignment, the same Foundry input, UID, and no-manifest selection produced
284 files per toolchain with zero byte differences after both generators ran.
The comparison used disposable session directories and did not modify Test.
This is output-parity evidence, not docs-ui validation or live pipeline evidence.

### Baseline refresh on 2026-11-12

The comparison now uses Test `main` commit
`373f0d3f27301c3bee4ddc6473dd6cf8f3f6995a` (request-body starter defaults)
and Foundry source from `openapi-3-2-reference-content-entire-spec-example`,
whose source Git blob is `d5121ee657b4c734b33000aa30c8586a0f0a7a04`.
Only the two generator paths were synchronized from `main` into that content
branch; the TOC generator was already identical.

| File | SHA256 |
| --- | --- |
| test/openapi32/generate-pages.mjs | 7D12215439F6618F551E8D9C1EC5CDBB9D20EFCE00D8F3DB45292CB6F7F47BAB |
| test/openapi32/generate-toc.mjs | EFE4C8BBE6D467708EC0F3F32F95DAEAF8F938BFD784D9606D3CCADAE3D0FBE8 |

Identical full-spec inputs initially produced 348 files in each toolchain with
159 byte-different files. After carrying over default preservation and lossless
serialization, all 348 files, including the TOC, are byte-identical on Node
26.13.0. All 35 Node tests pass, with page/TOC line coverage of 86.03%/93.72%
(both above the required 80%).
All 155 affected OpenAPI Pester tests also pass on Windows PowerShell 5.1.
The expanded baseline fixture also matches Test output byte-for-byte and covers
false/zero/null/empty and structured defaults, whitespace, references, nullable
wrappers, recursive schemas, parameters, headers, response bodies, and streaming
item shapes. Test generators run as byte-identical isolated copies against this
toolchain's pinned YAML dependency; neither comparison writes generated output
into the content checkout.

## Consequences

- A first run against previously generated production output changes prose and
  dictionary projections intentionally; unsupported emitted fields disappear.
- Comparing the full output with the selected/authored Test sample still shows
  new pages and manifest-dependent identity/server differences.
- Future baseline updates require reviewed fixture changes and parity checks.
- Engineering approval and supported-runtime pipeline verification remain
  separate gates.
