# ADR-0010: Parameterize manual OpenAPI production validation

- **Status:** Proposed
- **Date:** 2026-11-09
- **Deciders:** Pending engineering review
- **Tags:** openapi, pipeline, publishing-safety

## Context

The production job derives its target branch from the triggering content
repository and reads service configuration from that checkout. Foundation
validation needs queue-time inputs without changing those production defaults
or depending on the separate draft review-PR publisher.

## Decision

Add a manual-only pipeline accepting explicit target repository/branch and
source repository/branch/file, UID, output folder, and Boolean dry-run inputs.
Require the target branch to use the `validation/` namespace. Validate all
inputs before authentication or cloning and pass service configuration in an
external temporary JSON file, never by rewriting the content configuration.

Reuse production setup, authentication, pull, generation, and push steps.
The shared steps accept an optional configuration file; an empty value keeps
the production content-repository configuration behavior unchanged.

Default the manual entry to the reviewed MicrosoftDocs/test foundation inputs,
using the `openapi-3-2-reference-content-entire-spec-example` source branch and
the `validation/openapi32-foundation-example` target branch with `dryRun: false`.
Prepare that target branch from the example source branch before queueing to
compare generated output without unrelated default-branch history.
False executes real generation and the existing shared publisher against only
the selected validation branch; true restores generated output.
This is publishing validation, not the strictly read-only
onboarding workflow. The shared PR/live guards and concurrency behavior remain
unchanged. No draft PR is created.

## Scope

**In scope:** Scalar pipeline inputs, external configuration, production-path
reuse, validation-branch isolation, and regression tests.

**Out of scope:** Production branch overrides, arbitrary script/step inputs,
review-PR publishing, live pipeline provisioning, or changes to shared Git helpers.

## Options considered

- **Standalone manual entry (chosen):** Exposes operator inputs while preserving
  the content-driven production job and testing its actual publishing path.
- **Override production job parameters:** Changes branch/configuration semantics
  for existing consumers.
- **Reuse the review-PR publisher:** Tests a different workflow and couples the
  foundation to its dependent publishing changeset.

## Consequences

- Foundation validation can run from an automation checkout without installing
  a content-repository pipeline bootstrap.
- Publishing still requires the target's normal publishing configuration and
  authorized write access. Existing or newly created validation branches are
  handled by the shared pull helper.
- The default run publishes to a `validation/` branch. Operators must review
  the destination before queueing or select true for dry-run restoration.
  Local fixture evidence does not establish live pipeline acceptance.
