# Parallel Work Coordination

Status: standard project coordination guidance. Start with the supplied board
and history for each project, and scale the detail to the work. One person or
agent can carry a small sequential outcome through completion; concurrency is
not required to use coordination.

Coordination makes work inspectable without treating a task list as product
authority. The human and governing project documents own scope and decisions;
the board owns task and dispatch state. A board does not authorize delegation,
new scope, or external actions.

## Start small and scale

Record the current outcome, state, owner or next owner, relevant dependencies
and blockers, expected artifact, focused verification, and next action. The
starter provides empty task and history headers. Add real rows as work begins;
small edits can stay in an existing owner’s task. Record task transitions in
history. Use briefs, resource leases, worktrees, separate reviews, and
integration tasks when the work actually needs them. A single task can include
design, implementation, verification, and integration when appropriate.

When contributors or agents work concurrently, add explicit resource,
workspace, ownership, and integration controls for shared boundaries.

Keep five concerns separate:

1. task dependency — what must finish before work begins;
2. role and ownership — which capability and worker own the work;
3. resource capacity — what may run concurrently;
4. workspace isolation — where work can safely happen; and
5. planning state — what is committed, conditional, or still a decision.

## Board contract

Use the supplied project-local `coordination/tasks.tsv` and `history.tsv`.
Add `roles.tsv` or `resources.tsv` only when they answer a real routing or
capacity question. The headers are a starting schema; adapt them deliberately
when project needs differ, keeping task identity, state, ownership, and
transition evidence legible.

The portable task header is:

```text
id	status	kind	role	owner	deps	resource	workspace	artifact	validation	title	note
```

Use stable, never-recycled IDs; `none` for an empty source field;
`unassigned` for an open owner; comma-separated dependency IDs; and
semicolon-separated artifacts or checks. Keep model/effort allocation out of
this portable header; use a task brief, handoff, or project-local policy.

Statuses are `proposed`, `conditional`, `ready`, `claimed`, `blocked`, `done`,
`superseded`, and `cancelled`. Only `ready` tasks count toward the launchable
queue. A future task in a recommended chain is not claimable until it is ready.

## Activation and task transitions

When starting a project or opening a new work slice:

1. Add only the committed frontier, required review/integration work, and
   useful conditional work.
2. Record workspace isolation before fan-out.
3. Name one integration owner; use a separate integration task when parallel
   work touches shared runtime, configuration, generated output, or combined
   validation and the boundary needs independent coordination.
4. Serialize board edits through one coordinator or an equivalent lock.
5. Require a handoff before a task becomes `done`.

The normal path is `ready` → `claimed` → `done`. A claim needs an owner; a
block needs a named clearing event. Record claims, releases, blocks,
completions, supersessions, and graph changes in history. A task is done only
when its stated artifact and focused validation are readable, or its handoff
names the exception and who owns it. A concise task note can be the handoff
when it carries the relevant evidence; use a separate document when needed.

Use a [task brief](templates/task-brief-template.md) when a TSV row cannot
safely carry the acceptance contract—especially for decision frontiers,
trust-boundary work, integration/closeout, or non-obvious exclusions.

## Allocation policy

Reasoning fit and worker allocation are separate. Describe fit as
`straightforward`, `moderate`, or `deep`; let each project select the workers
and effort that fit those shapes.

When allocation matters, create `coordination/dispatch-policy.md` from the
[dispatch policy template](templates/dispatch-policy-template.md). It may
suggest GPT-6 Luna for bounded execution, GPT-6.1 Sol for reasoning, design, or
review, and GPT-6 Astra for exceptional graph-changing or high-risk integration
review. These are suggestions, not a required roster.

**Fast mode is prohibited for subagents unless the human user explicitly
authorizes an exception.** Record any exception, actual worker/model, effort,
and rationale in the task brief or handoff.

## Decisions, replanning, and dispatch

When the user may not be watching the conversation, follow the portable
[Agent Attention and Interruption](../reference/agent-attention-and-interruption.md)
policy: put the full ask in the originating thread and use an enabled external
channel only as a minimal nudge.

Use an [ambiguity gate](templates/ambiguity-gate-template.md) when an answer
can expand, collapse, redirect, or defer the graph. Keep hypothetical work in
a [conditional task](templates/conditional-task-template.md); it never inflates
the ready queue.

Run a [replanning checkpoint](templates/replanning-checkpoint-template.md) at
ambiguity resolution, fan-out/fan-in, material scope or architecture changes,
repeated blocks, resource/workspace contention, or whenever the board no
longer matches repository reality. At fan-in, reconcile artifacts, validation,
commit/import facts, untracked work, leases, and the next frontier.

Every board-aware handoff says:

```text
Board result:
Claimable sequence:
Launch now: N
Capacity:
Blocked/waiting:
Orchestrator action:
```

When useful, distinguish graph-ready, launchable-now, resource-waiting, and
dependency-waiting work.

## Workspaces, resources, and recovery

Choose `shared` only for explicit non-overlap; use `isolated` for overlapping
source, refactors, dependencies, migrations, or long-running work; and use
`integration` for shared wiring, generated output, merge resolution, broad
validation, and release preparation.

A resource lease is a capability check as well as a mutex. Verify that the
target runtime can use a browser, port, database, account, or session before
dispatch. Record operator-owned state that must not be stopped, restarted,
bound, mutated, or otherwise disturbed. Clean up task-owned processes before
handoff; named shared processes need an identity, owner, purpose, and cleanup
owner.

For interruption recovery: inspect the board, working tree, commits,
task-owned processes, and leases; determine whether work is complete, partial,
or absent; record and release/reassign/split/block the task; then re-check
capability before relaunching persistent work. Do not infer recovery from an
agent status alone.

## Proof standard

The pattern is working when the board reflects repository reality, work does
not duplicate claimed lanes, resource contention is explicit, and a completed
task is an integrated, validated handoff rather than just a finished agent
response. Measure completion-to-next-launch time, claim errors, collisions,
blocked-task age, handoff rework, and human coordination cost; improve from
evidence rather than adding ceremony by default.
