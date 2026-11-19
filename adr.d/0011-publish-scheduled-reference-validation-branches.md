# ADR-0011: Publish scheduled reference output only to new validation branches

- **Status:** Proposed
- **Date:** 2026-11-09
- **Deciders:** Pending engineering approval
- **Tags:** openapi, schedule, publishing-safety

## Context

Foundry validation needs generated content available for remote review without
changing the content repository's main branch. The owner selected publishing
to a new validation branch rather than read-only restoration. ADR-0007's
manual dry-run contract remains unchanged.

## Decision

Add a separate manual/scheduled entry in ReferenceAutomation. Run Node 26 and
repository Pester tests, then clone the explicit target base branch and use
the normal orchestrator with external configuration and `dry_run: false`.
Use the existing inventory, path, source-clone, authentication, and generator
helpers. Request target contents/write only; no PR permission or API is needed.

Expose Boolean pipeline parameter `dryRun`, default false to preserve scheduled
publication. True dispatches to the existing read-only dry-run validator,
requires no build-ID/head validation, and creates no remote branch or commit.
Both modes run the same Node/Pester gates. Normalize only Azure's exact Boolean
string representations at the YAML/PowerShell boundary; reject missing/other
values. Direct script callers retain strict service Boolean validation.

Each run selects a new `validation/openapi32-foundry-<BuildId>` head. Require
a `validation/` head distinct from the base. Reject an existing remote head,
missing base, no generated changes, out-of-output changes, generation failure,
or a base revision that advances during generation. Stage only the output
boundary and create one commit. Push only the new head ref with an empty-ref
lease so a concurrent head creation cannot be overwritten.

Never push the base, merge content, or open a PR. Remove temporary configuration
on all exits; remove successful checkouts only after a successful push and
retain failed checkouts for diagnosis. If push succeeds but cleanup fails,
report failure and inspect the remote head before retrying.

The proposed schedule is Sunday 23:00 UTC on automation master. It is an
offset, not an exclusion lock against the legacy REST pipeline. Creating or
enabling a definition requires separate operator approval. Existing manual
dry-run workflows retain read-only authentication and exact restoration.

Time clone, inventory, generation/restoration, source cleanup, boundary
verification, commit, push, and successful target cleanup phases on the host
stream. Report inventory counts and periodic inventory/native-process progress
without logging process arguments or changing returned data. Preserve the
60-minute job cap and all whole-checkout safety checks. Use an ordinal
case-insensitive hash set for the union of before/after paths, avoiding
quadratic PowerShell deduplication on large content repositories. A completed
generator is not publication evidence; inspect the parent timeline and last
phase when a run is canceled.

On initial Git remote lookup errors, run bounded, read-only GitHub API probes
using the same credential, then preserve the original failure. Probe metadata,
contents, and one page of installation-token repositories without following
redirects. Log only statuses and target-scope results/counts, never credentials,
response bodies, other repository names, or exception details. An incomplete
scope page cannot establish exclusion, and unsupported installation-token
endpoints do not establish lack of repository access.

## Consequences

- Main is never a push destination; generated output is isolated in reviewable
  remote branches. No content-repository configuration change is needed.
- A new remote branch accumulates per successful run. Retention/deletion is
  an operator responsibility, not an automatic destructive action.
- Branch retry/no-diff behavior is explicit. Scheduled live permissions and
  Node 26 acceptance require actual pipeline evidence.
- The scheduled entry preserves the operator-selected UID
  `microsoft-foundry.rest` and output `articles/foundry/reference/rest`.
  Comparing against Test POC output requires matching UID/output inputs.
