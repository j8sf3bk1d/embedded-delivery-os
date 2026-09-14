# Coordination Board

This optional directory is the project-local control plane for concurrent work.
It is intentionally empty in the starter; governing rules live in
[Parallel Work Coordination](../docs/process/parallel-work-coordination.md).

When enabled, create the smallest board that can answer what is ready, who owns
it, which resources are constrained, which workspace it uses, and what artifact
and validation close it.

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

Verify constrained-resource capability before dispatching. Task notes and
handoffs name operator-owned state that must not be touched and cleanup
ownership for long-running processes. Use a task brief for work whose contract
will not fit safely in a row, and a project-local dispatch policy when
allocation matters. Fast mode is prohibited for subagents unless the human user
explicitly authorizes an exception.

The starter does not prescribe a scheduler. Add automation only after a
project exposes a repeatable board-operation failure mode.
