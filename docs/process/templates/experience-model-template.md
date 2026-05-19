# Experience Model Template

Use this for user-facing or operator-facing arcs where outcome-to-path-to-screen traceability matters.

Create one when any of these are true:

- the arc introduces or reshapes multiple related screens
- the work involves a multi-step workflow with drill-in or handoff between surfaces
- role differences or progressive disclosure matter
- the same underlying data will appear across multiple screens
- previous phases already showed UX drift, feature-first accretion, or workflow confusion

Keep this document focused on user outcomes and surface contracts, not implementation detail.

## Scope

- Arc or initiative:
- Primary actor types:
- Related design or phase docs:

## Outcome Map

For each primary outcome, capture:

- actor
- goal
- entry state
- completion state
- priority
- trust or quality bar

Suggested table:

| Outcome | Actor | Entry state | Completion state | Priority | Notes |
|---|---|---|---|---|---|

## Path Map

For each important outcome, map:

- primary path
- alternate path
- failure or recovery path
- blockers, trust checks, or decision points

Suggested shape:

### Outcome: `<name>`

- Primary path:
- Alternate path:
- Failure or recovery path:
- Decision or trust checkpoints:

## Surface Map

For each important screen or surface, capture:

- primary goal
- secondary supported goals
- which path steps it owns
- what it explicitly should not own
- entry points
- exit pivots

Suggested table:

| Surface | Primary goal | Secondary goals | Path steps owned | Entry points | Exit pivots | Does not own |
|---|---|---|---|---|---|---|

## Screen Data Contracts

For each important surface, capture:

- required primary data
- secondary or derived data
- freshness expectations
- empty, loading, and error states
- permissions or role differences
- actions enabled from the data shown

Suggested shape:

### Surface: `<name>`

- Primary data:
- Secondary or derived data:
- Freshness expectations:
- Empty state:
- Loading state:
- Error or recovery state:
- Permissions or role differences:
- Actions enabled:

## Progressive Disclosure Rules

Document the rules that keep the workflow understandable:

- what should appear before deeper machinery
- what should stay secondary until drill-in
- which screens should emphasize action before telemetry

## Open Questions

- unresolved UX decisions
- unresolved workflow boundaries
- unresolved data requirements

## Review Triggers

State whether this experience model should lead to:

- a phase design review
- a workflow coherence review
- a design review gate

If none apply, say so explicitly.

