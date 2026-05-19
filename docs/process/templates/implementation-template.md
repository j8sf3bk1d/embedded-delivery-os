# Implementation Document Template

References:

- `docs/reference/ux-process.md`
- `docs/reference/engineering-principles.md`
- `docs/reference/security-posture-and-process.md`
- `docs/process/change-map.md`
- `docs/process/phase-and-arc-lifecycle.md`
- `docs/qa/test-strategy.md`
- `docs/reviews/review-template.md`

## Scope

## Step-by-step task breakdown

## Dependencies

## Expected files or areas touched

## Checkpoints

## Validation commands

## Documentation updates needed

List the concrete docs that should change before closeout.

Common candidates:

- `docs/index.md`
- `docs/system/system.md`
- `docs/system/schema.md`
- `docs/process/change-map.md`
- `docs/qa/test-strategy.md`
- `docs/qa/manual-testing.md`
- `docs/system/decisions/*.md`
- `user-docs/user-manual.md`
- `.env.example` and setup or runbook docs

If a doc does not need changes, say so explicitly.

## Docs cleanup and normalization

Record any cleanup needed to keep documentation fresh:

- stale links or outdated status references
- temporary notes to remove or preserve intentionally
- README or package-boundary docs that should reflect the new implementation shape

## Review requirements

Confirm which of these are required before closeout:

- phase completion review
- design review gate follow-up
- security review gate
- pre-release review

If none apply, say so explicitly.

## Closeout checklist

- Git hygiene:
  verify only intended files changed and note any deliberate leftover work
- Testing:
  record focused validation results and whether broader validation ran
- Documentation:
  update `docs/index.md`, system docs, schema docs, QA docs, change-map rows, decisions, and user docs when the change affects them
- Design consistency:
  confirm the implementation still matches the phase design or document the drift
- UX consistency:
  for user-facing work, verify language, flows, and recovery states against `docs/reference/ux-process.md`
- Review:
  note which review lenses were applied and any follow-up issues created

## Completion notes
