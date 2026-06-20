# Manual Testing

Use this file for workflow-level checks that automated validation does not cover yet.

## Default checklist

- confirm the repo map in `README.md` and `docs/index.md` still reflects reality
- confirm the current arc and active phase links are correct
- confirm setup notes still match the real runtime shape
- confirm user-facing instructions in `user-docs/` match current behavior
- confirm env and external-service notes are still accurate
- for UX or UI changes, compare screenshots when tooling exists and note any visible drift in layout, density, contrast, or action clarity
- when a project-local screenshot capture command exists, prefer using it over ad hoc manual browser captures so viewports and states stay repeatable
- for stateful apps, confirm the capture flow used isolated local state rather than the operator's normal runtime data unless the workflow is explicitly destructive
- keep only meaningful visual checkpoints and store them under `docs/archive/screenshots/` when they help future review

## Suggested result format

| Date | Area | Scenario | Result | Notes |
|---|---|---|---|---|
| YYYY-MM-DD | Example area | Example scenario | pass / fail / deferred | Replace with concrete findings |
