# ADR-0011: Use supported Node handlers for OfflineBook signing

- **Status:** Proposed
- **Date:** 2026-11-12
- **Deciders:** Pending code-owner review; accepting decision-makers must be named before acceptance.
- **Tags:** OfflineBook, pipelines, signing

## Context

[Content CI run 636978](https://apidrop.visualstudio.com/Content%20CI/_build/results?buildId=636978)
failed at "Sign Cab Files" before signing started. EsrpCodeSigning 5.1.10
declares only a Node16 handler, which the agent's end-of-life policy blocks.
Both OfflineBook build templates use this task version.

The apidrop organization already has EsrpCodeSigning 6.1.3 installed. Its task
metadata declares Node20_1 and Node24 handlers and the same input contract as v5.

## Decision

Use EsrpCodeSigning@6 in the main and E2E OfflineBook build templates.
Preserve the signing inputs, credentials, signing operations, and agent EOL policy.

## Scope

**In scope:** The signing-task major version in the two shared templates consumed
by the production and PPE OfflineBook entry points.
**Out of scope:** Builder packages, .NET SDKs, service deployment, and publishing behavior.

## Options considered

- **Upgrade the task (chosen):** Uses supported handlers already available in apidrop.
- **Disable the agent EOL restriction:** Would retain an unsupported Node runtime
  rather than remove the cause of the failure.
- **Install Node through a pipeline step:** Does not change the task's declared handler.

## Consequences

- **Positive:** Signing can select a supported Node handler without a policy exception.
- **Negative / trade-off:** Both regular and E2E pipelines move to a new task major version.
- **Risk:** Matching input metadata does not prove live signing compatibility.
  Verify an E2E run and one affected book before retrying the remaining books.
  The change is not live until merged into master.
