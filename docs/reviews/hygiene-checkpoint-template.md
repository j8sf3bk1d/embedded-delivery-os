# Hygiene Checkpoint Template

Use this for periodic repo-health sweeps that are broader than a single phase but smaller than a full release review.

## Review metadata

- Date:
- Reviewer:
- Scope:
- Trigger:

Suggested trigger examples:

- after multiple phases land
- after a long burst of implementation work
- before activating a new arc
- when docs freshness feels uncertain

## Result

- No blocking issues / blocking issues found

## Validation

List the commands or manual checks actually used for the checkpoint.

## Docs And Process Check

Check for:

- `docs/index.md` alignment with current arc and active phase
- arc and phase status consistency
- system, schema, change-map, QA, and user-doc freshness where recent work touched them
- stale links, stale phase references, or zombie planning notes

## Design And Architecture Check

Check for:

- cross-phase drift
- unclear ownership or boundaries
- phase sequencing that no longer reflects the current roadmap

## Security And Trust-Boundary Check

Use a light or heavy pass depending on recent work.

Check for:

- dependency or config drift
- newly introduced trust boundaries
- missing review gates for auth, secrets, or external integrations

## Process Hygiene Notes

Capture:

- missing docs
- status inconsistencies
- findings that should become issues, decisions, or new phases

## Recommendation

- continue current arc
- run a planning checkpoint
- open a cleanup phase
- trigger a security or release review

