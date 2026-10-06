# ADR-0001: Record architecture decisions

- **Status:** Proposed
- **Date:** 2026-08-27
- **Deciders:** Lyndon Swan — *co-signer needed: accountable service owner for this repo (`Engineering\Service Owners\Osmond` per `es-metadata.yml`). Fill in before requesting acceptance.*

## Context

Design decisions in this repo currently live in people's heads, chat threads, or nowhere at all. That knowledge is expensive to rediscover once the person who made the call has moved on, and an AI agent working in this repo has no way to ask — it can only retrieve what was written down. We need a durable, in-repo, reviewable way to capture *why* decisions were made so future maintainers (human or agent) don't re-litigate settled questions or break load-bearing constraints by accident.

## Decision

We will record significant, hard-to-reverse, or surprising architecture decisions as Architecture Decision Records (ADRs) in `docs/adr.d/`, using the Michael Nygard format (Context / Decision / Scope / Options considered / Consequences). ADRs are immutable once `Accepted` and are superseded, never rewritten.

## Scope

**In scope:** decisions about this repo's design, constraints, and process going forward.
**Out of scope:** whether a stronger "ADR coverage for every mutation" policy (with evidence pairing and CI enforcement) is adopted — that is a separate, explicitly-accepted decision.

## Options considered

- **ADRs in `docs/adr.d/` (chosen)** — versioned with the code, reviewed in PRs, discoverable from the repo, industry-standard format.
- **A wiki / Loop page** — drifts out of sync, isn't reviewed with the code, doesn't survive a handover.
- **No formal record** — the status quo, and the reason decision rationale is currently unrecoverable.

## Consequences

- **Positive:** decision rationale becomes discoverable and survives ownership changes.
- **Trade-off:** a small per-decision authoring cost.
- **Follow-up:** this repo's owners should explicitly accept or amend this record, and decide whether to adopt the stronger coverage-and-evidence policy.
