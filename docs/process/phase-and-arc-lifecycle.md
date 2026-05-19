# Phase And Arc Lifecycle

Purpose:
Define the default operating lifecycle for arcs and phases so activation, execution, review, and closeout do not depend on chat memory.

## Core rule

Only one phase should normally be `active` at a time for a given arc unless the arc explicitly calls out parallel lanes.

## Recommended status vocabulary

Use these status values consistently:

- `pending`
- `active`
- `blocked`
- `complete`
- `deferred`
- `cancelled`

Avoid inventing ad hoc status labels unless the project has a specific reason.

## Arc lifecycle

### Arc becomes active when

- the repo has enough source authority and distillation to define a bounded objective
- the arc goal, outcomes, and phase plan are written down
- `docs/index.md` points to the arc as current
- for meaningful user-facing arcs, an experience model exists or the arc explicitly says why one is unnecessary

### Arc stays active while

- one or more phases are still pending, active, or blocked
- the arc goal remains the current highest-priority bounded objective

### Arc can be marked complete when

- the arc completion criteria are checked against reality
- the final active phase is complete or explicitly deferred
- any unresolved follow-up work is moved into a later arc, `docs/scratchpad/issues.md`, or a decision record
- `docs/index.md` and `docs/process/arcs/README.md` point to the next active arc or explicitly note that no new arc is active yet

## Phase lifecycle

### Phase can be opened when

- the work is bounded enough to describe clearly
- the intended outcome, touched areas, and validation plan can be stated
- the phase belongs to a specific arc

### Phase becomes active when

- it is the current implementation focus
- its design section is adequate for the intended level of risk
- review requirements are decided
- `docs/index.md` points to it as the active phase

### Phase stays active while

- implementation is still ongoing
- validation or review work required for closeout is incomplete
- follow-up documentation changes are still pending

### Phase should move to blocked when

- the next step depends on missing information, access, infrastructure, or an unresolved decision
- the blocker is substantial enough that another contributor could not continue safely from the current docs alone

Record the blocker explicitly in the phase doc and in `docs/scratchpad/issues.md` if it will survive beyond the immediate session.

### Phase can be marked complete when

- implementation goals for the phase are met, or any scoped deferrals are explicit
- focused validation ran, or the reason it did not run is recorded
- required reviews are completed or explicitly deferred
- documentation updates named in the phase are applied
- `docs/index.md` and the arc doc reflect the next active phase or next stop point

### Phase should be deferred when

- the work remains valid but is no longer the current priority
- another phase or arc must happen first

### Phase should be cancelled when

- the work is no longer desirable
- the objective was superseded, absorbed elsewhere, or proven unnecessary

Record why it was cancelled so the repo does not reopen it by accident later.

## Review routing rules

### Use a phase design review when

- implementation has not started yet for meaningful new work
- the phase changes UX, system shape, or important workflows enough that plan quality matters

### Use an experience model when

- an arc introduces or reshapes multiple related user-facing or operator-facing screens
- the work involves multi-step workflows, drill-in paths, or role-shaped disclosure
- the same underlying data must support multiple surfaces with different goals
- prior phases showed workflow confusion, feature-first accretion, or screen-level drift

For small isolated screens, explicitly saying an experience model is unnecessary is acceptable.

### Use a phase completion review when

- the phase is about to be marked complete
- the phase introduced meaningful behavior, architecture, or operational changes

### Use an arc checkpoint review when

- multiple phases have landed
- system drift may have accumulated
- the repo needs a broader coherence checkpoint before continuing

### Use a workflow coherence review when

- multiple UX phases have landed in the same user-facing arc
- the product may now have enough surface area for workflow drift
- screens or navigation may have become implementation-oriented instead of outcome-oriented

### Use a design review gate when

- boundaries, ownership, or cross-phase coherence may have drifted

### Use a security review gate when

- auth, trust boundaries, secrets, external fetch surfaces, or sensitive data paths changed

### Use a pre-release review when

- the current slice is about to be deployed, externally used, or treated as release-ready

## Finding routing rules

When a review finds an issue:

- put short-lived implementation follow-up in the active phase doc if it will be handled immediately
- put deferred or cross-phase issues in `docs/scratchpad/issues.md`
- create a decision record when the finding forces a durable architecture, security, scope, or operational choice
- open a new phase when the fix is large enough to deserve its own bounded work item

## Closeout minimums

Before closing a phase or arc, check:

- `docs/index.md`
- relevant arc and phase docs
- `docs/system/system.md` when architecture or boundaries changed
- `docs/system/schema.md` when structured state changed
- `docs/process/change-map.md` when touched-area guidance changed
- `docs/qa/test-strategy.md` or `docs/qa/manual-testing.md` when validation expectations changed
- `user-docs/user-manual.md` when user-visible behavior changed
- `docs/scratchpad/issues.md` for durable deferred work

## Anti-patterns

- marking a phase complete while the next step still lives only in chat
- treating blocked work as active for long periods
- leaving review findings un-routed
- updating code without refreshing the docs named in the phase
- opening multiple active phases in one arc without explicit lane ownership
