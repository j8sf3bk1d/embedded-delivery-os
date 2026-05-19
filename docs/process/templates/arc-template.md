# Arc Template

References:

- `docs/reference/ux-process.md`
- `docs/reference/engineering-principles.md`
- `docs/reference/security-posture-and-process.md`
- `docs/process/change-map.md`
- `docs/process/phase-and-arc-lifecycle.md`
- `docs/qa/test-strategy.md`
- `docs/reviews/review-template.md`

## Goal

## Background

## Outcomes

## Experience model requirement

State whether this arc needs an experience model.

Use one when:

- the arc is user-facing or operator-facing
- multiple related screens or flows will be shaped together
- path-to-outcome traceability matters

If required, link the planned experience-model doc path.

## Phases

| Phase | Purpose | Status |
|---|---|---|

## Planned review hooks

List the review checkpoints the arc is expected to trigger. Do not wait until the end of the arc to invent them.

Minimum expectations:

- phase design review before implementation begins
- phase completion review before marking a phase done
- arc checkpoint review after multiple phases or meaningful system changes

Add higher-level gates when relevant:

- design review gate when system boundaries, ownership, or cross-phase coherence may drift
- security review gate when auth, trust boundaries, secrets, external fetch surfaces, or sensitive data paths change
- workflow coherence review when multiple UX phases may have drifted away from the intended user paths
- pre-release review before deployment, external use, or broader adoption

## Review trigger notes

- Design review gate triggers:
  boundary changes, new major integrations, cross-cutting logic changes, or accumulated architectural drift
- Security review gate triggers:
  auth or authorization changes, privileged operator actions, new secret flows, new external fetch surfaces, or meaningful rollout expansion

## Risks

## Completion criteria

## Related docs

## File organization note

Store each arc in its own folder:

```txt
docs/process/arcs/<nn-arc-slug>/
  arc.md
  phases/
```
