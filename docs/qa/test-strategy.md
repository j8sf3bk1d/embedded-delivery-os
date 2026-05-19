# Test Strategy

## Current state

This starter repo does not contain implementation code yet, so there are no stack-specific automated commands to run. Use this document as the place to add the real validation surface once the runtime shape exists.

## Default testing policy

When implementation begins, prefer the smallest meaningful validation that can prove the change is safe:

- unit tests for pure logic and data transformations
- integration tests for boundaries between modules, services, and storage
- end-to-end or workflow tests for critical user or operator paths
- smoke tests for runtime startup, core routing, and basic health

## Broader validation triggers

Run broader regression when:

- completing a phase
- changing shared infrastructure or startup behavior
- changing data models or migrations
- changing authentication, authorization, or trust boundaries
- changing user-critical workflows
- changing external service integrations
- preparing for release, external use, or deployment

## Focused validation guidance before the stack exists

Until concrete commands exist:

- verify links, statuses, and current-state notes in docs
- review `.env.example` against the intended runtime shape
- review manifest and lockfile changes together
- use `git status --short` to confirm the changed file set matches the intended scope

## Initial command slots to replace later

Replace these placeholders once the real stack is known:

- install: `<package-manager install command>`
- lint: `<lint command>`
- typecheck: `<typecheck command>`
- unit tests: `<unit test command>`
- integration tests: `<integration test command>`
- build: `<build command>`
- app smoke: `<local startup or health-check command>`

## Dependency hygiene checks

When dependencies change:

- review manifest and lockfile changes together rather than in isolation
- prefer exact direct dependency versions unless there is a documented reason not to
- treat new direct dependencies and install-time scripts as trust-boundary events
- document unresolved advisories or accepted risks in a review or decision record

## Release-readiness rule

Before calling a slice release-ready, launch-ready, or suitable for external use:

- use `docs/qa/release-readiness-checklist.md`
- ensure external-resource assumptions are explicit in `docs/system/external-resources-and-infrastructure.md`
- run the appropriate review gate depth for the trust boundaries involved

Update this document as soon as stack-specific validation commands and riskier system boundaries become real.
