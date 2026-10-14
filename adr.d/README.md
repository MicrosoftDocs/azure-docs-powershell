# Architecture Decision Records

An Architecture Decision Record (ADR) is a short, version-controlled record for one bounded unit of related work: the context faced, the decision made, the options considered, and the consequences accepted.

Code tells us *what* the system does. An ADR tells us *why* it does it that way — the part that's expensive to rediscover once the person who made the call has moved on or forgotten. That gets more important as agents do more of the implementation: a person can ask a colleague for missing context; an agent can only retrieve what was written down.

ADRs live beside the code they govern (`docs/adr.d/`), reviewed and versioned with it — not in a wiki or chat thread that drifts out of sync.

## How to use this folder

1. Search existing ADRs by domain/component/invariant before writing a new one — reuse one that already covers your change.
2. If none covers it, copy `adr-template.md` to `NNNN-<short-slug>.md` (next number, zero-padded) and fill it in.
3. New ADRs start life as **`Proposed`**. They become **`Accepted`** only when the repo's actual named decision-makers explicitly agree — not by default, and not because a tool created the file.
4. ADRs are immutable once `Accepted` — supersede, don't rewrite.

## Bootstrap ADR

`0001-record-architecture-decisions.md` is the seed record explaining *why this folder exists*. It ships as `Proposed` — accept it (or amend it) as your team's first real decision.

## Going further

This minimal scaffold only creates the folder and a template. The stronger policy — **ADR coverage required before every mutation**, paired evidence records, and CI enforcement — is a deliberate, separately-accepted decision. Don't turn on enforcement until the team has explicitly said yes to that stronger bar.
