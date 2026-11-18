# Coordination Board

This directory is the project-local coordination home. The starter supplies
empty `tasks.tsv` and `history.tsv` headers; initialize them with real work
when the project begins. [Coordination guidance](../docs/process/parallel-work-coordination.md)
defines the contract.

Record the active outcome and task state, owner or next owner, relevant
dependencies and blockers, expected artifact and focused verification, and
the next action. Use one owner for a small sequential outcome; do not create
a new row for every edit or test. The board schedules work and does not itself
authorize new scope, delegation, or external actions. Add resource, workspace,
and integration details when those boundaries matter.

```text
coordination/
  README.md
  tasks.tsv
  history.tsv
  roles.tsv       # only when capability routing matters
  resources.tsv   # only when capacity or leases matter
```

The `tasks.tsv` header is:

```text
id	status	kind	role	owner	deps	resource	workspace	artifact	validation	title	note
```

Treat the board as shared state. Serialize mutations; append history for every
claim, release, block, completion, supersession, or graph-changing decision.
A task is done only when its handoff records readable artifacts, focused
validation, commit/import facts, any untracked exception, and the status of
operator acceptance.

For example, a content project may create one `GUIDE-01` row for updating a
guide: mark it `ready`, set owner to `unassigned`, name the guide as the
artifact and a source-and-link check as validation. When work starts, assign
the owner, change the row to `claimed`, and append a history event with the
date, task ID, actor, and transition. At completion, record the artifact and
check in the note or a linked handoff, mark it `done`, and append the
completion event. If a required product decision is missing, mark it `blocked`
and name the decision owner and clearing event. A typo corrected within
`GUIDE-01` needs no separate row.

Verify constrained-resource capability before dispatching. Task notes and
handoffs name operator-owned state that must not be touched and cleanup
ownership for long-running processes. Use a task brief for work whose contract
will not fit safely in a row, and a project-local dispatch policy when
allocation matters. Fast mode is prohibited for subagents unless the human user
explicitly authorizes an exception.

The starter does not prescribe a scheduler. Add automation only after a
project exposes a repeatable board-operation failure mode.
