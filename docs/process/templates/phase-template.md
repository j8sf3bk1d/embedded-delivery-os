# Phase Template

References:

- `docs/reference/ux-process.md`
- `docs/reference/engineering-principles.md`
- `docs/reference/security-posture-and-process.md`
- `docs/process/change-map.md`
- `docs/process/phase-and-arc-lifecycle.md`
- `docs/qa/test-strategy.md`
- `docs/reviews/review-template.md`

Use this file for a compact phase record when one document with clear `Design` and `Implementation` sections is enough.

Default location:

```txt
docs/process/arcs/<nn-arc-slug>/phases/<phase-slug>/phase.md
```

Split design and implementation into separate files only when the combined phase file becomes hard to use.

## Phase name

## Status

## Design

### Intent

### User or system outcome

### Constraints and assumptions

### Interfaces and boundaries

### Data and state ownership

### Edge cases and risks

### Definition of done

### Validation plan

### Review requirements

At minimum, decide whether this phase needs:

- a design review before implementation starts
- a phase completion review before marking done

For meaningful user-facing work, also decide whether this phase depends on or should update an experience model.

Also decide whether this phase should trigger a higher-level gate:

- design review gate for boundary, ownership, or cross-phase coherence changes
- security review gate for auth, secrets, trust-boundary, sensitive-data, or external-fetch changes
- workflow coherence review if multiple related UX phases may now need a broader path and screen-ownership check
- pre-release review if this phase materially contributes to deployable or externally used behavior

### Experience-model links

Link the relevant experience-model doc when the phase is shaping user-facing or operator-facing workflows.

Suggested pattern:

- `docs/process/arcs/<nn-arc-slug>/experience-model.md`

## Implementation

### Task breakdown

### Dependencies

### Expected files or areas touched

### Checkpoints

### Validation commands

### Documentation updates needed

Name the concrete docs that must be refreshed if this phase changes reality.

Common candidates:

- `docs/index.md`
- `docs/system/system.md`
- `docs/system/schema.md`
- `docs/process/change-map.md`
- `docs/qa/test-strategy.md`
- `docs/qa/manual-testing.md`
- `docs/system/decisions/*.md`
- `user-docs/user-manual.md`
- `.env.example` and any setup or runbook docs

If a candidate does not apply, say so explicitly rather than leaving it implicit.

### Docs cleanup and normalization

Use this section to capture:

- stale status text or links that must be updated
- temporary notes that should be promoted, trimmed, archived, or deleted
- places where source docs, derived docs, and implementation docs may drift
- app or package README updates needed to keep boundaries rediscoverable

### Review artifacts to create or update

Link the expected review doc paths here when known.

Suggested pattern:

- `docs/reviews/YYYY-MM-DD-<phase-slug>-design-review.md`
- `docs/reviews/YYYY-MM-DD-<phase-slug>-completion-review.md`
- `docs/reviews/YYYY-MM-DD-<phase-slug>-security-gate.md`

### Git hygiene and checkpoint plan

### Completion notes

### Closeout gate check

Before marking the phase complete, confirm:

- the planned review work was done or explicitly deferred
- any required design, security, or release gate decision is recorded
- docs and validation notes match the final implementation state
- `docs/index.md` reflects the correct current arc, active phase, and next step
- system, schema, QA, change-map, and user-doc updates were applied where relevant
- implementation still matches the design, or the divergence is recorded explicitly
- user-facing work still aligns with `docs/reference/ux-process.md`

### Current progress
