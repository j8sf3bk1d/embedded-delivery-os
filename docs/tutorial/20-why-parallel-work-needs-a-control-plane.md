# Why Parallel Work Needs A Control Plane

Parallel agents can make delivery faster. They can also make a project less
legible, more collision-prone, and harder to recover after interruption.

The problem is not that multiple workers exist. It is that a task list,
worktree, or completed agent response is often mistaken for coordination.

This lesson explains why parallel work needs a small, repo-native control
plane—and why that control plane should remain optional.

## How It Was Learned Or Earned

The recurring mess looked like this:

- a broad roadmap was treated as a queue of things that could all start now
- two workers changed the same practical boundary through different files
- a browser, port, account, or operator-owned process was named but not usable
- a task was marked complete even though its artifact was untracked, its commit
  chain was incomplete, or its integration proof had not happened
- an interrupted worker left a claim behind with uncertain repository state

The obvious fix is to ask agents to coordinate better, open more worktrees, or
use a stronger orchestration mode. Those help, but none answer the basic
questions that a delivery system must answer:

- what is safe to start now?
- who owns a bounded lane?
- which scarce resource is actually available and usable?
- what proof turns work into a completed handoff?
- what changes when new evidence redirects the plan?

The insight is that concurrent work needs durable dispatch state. The harness
can run workers; the repository must preserve the authority, dependencies,
constraints, and recovery record that make those workers safe to coordinate.

## The Strategy

Use a small control plane only when concurrency creates a real coordination
problem.

The control plane keeps five facts separate:

1. **Dependency:** whether prior work is genuinely complete.
2. **Ownership:** which worker owns the current bounded task.
3. **Capacity:** which browser, port, account, layout surface, or other scarce
   resource can run now.
4. **Workspace:** whether work can share files or needs isolation/integration.
5. **Planning state:** whether work is committed, conditional, blocked, or
   waiting for a decision that can change the graph.

That separation prevents several false equivalences:

```text
task exists             ≠ task is ready
worker finished          ≠ integrated, validated handoff
separate worktree        ≠ isolated external resource
model allocation         ≠ task semantics
goal or roadmap          ≠ dependency graph
```

The goal is not to build a universal scheduler. It is to make the next safe
action, the first blocker, and the recovery path visible to both people and
agents.

## The Tactics

### 1. Keep the board narrow and portable

[Parallel Work Coordination](../process/parallel-work-coordination.md) uses a
small task board with stable IDs, explicit statuses, dependencies, resources,
workspace, artifacts, and validation.

Only `ready` tasks belong to the launch frontier. Proposed and conditional
work remain visible without becoming accidental commitments.

### 2. Treat decisions as graph changes

Some work is not execution. It is a decision frontier: its answer may expand,
collapse, redirect, or defer later tasks.

The [ambiguity gate](../process/templates/ambiguity-gate-template.md),
[conditional task](../process/templates/conditional-task-template.md), and
[replanning checkpoint](../process/templates/replanning-checkpoint-template.md)
make that change explicit instead of quietly inventing downstream work.

### 3. Define completion as evidence, not a status word

A task does not become done because an agent says it is done. Its handoff
names artifacts, focused validation, commit/import facts, untracked exceptions,
operator acceptance when needed, process cleanup, and the next dispatch state.

That contract lives in the
[parallel handoff template](../process/templates/parallel-handoff-template.md).

### 4. Treat resources as capability checks

A browser lease or an isolated worktree does not prove the runtime can actually
use the browser. A task must verify capability and state what it must not touch,
especially an operator-owned port, database, or running service.

The [workspace isolation template](../process/templates/workspace-isolation-template.md)
turns those negative constraints and cleanup ownership into visible decisions.

### 5. Keep allocation policy separate from board truth

Task meaning should not change because a project chooses a different model.
The portable board therefore does not contain model/effort fields. A project
may use a [dispatch policy](../process/templates/dispatch-policy-template.md)
and task briefs to choose allocation.

The standard quality floor is simple: Fast mode is prohibited for subagents
unless the human user explicitly authorizes an exception.

## The Proof Or Belief Builders

You know this framework is working when parallelism produces less waiting and
rework without requiring the coordinator to remember the graph mentally.

### What it prevents

- speculative work being launched as though it were ready
- duplicated execution lanes and hidden shared-state collisions
- claims stranded by interruptions
- resource ownership mistaken for actual usable capability
- agent-completion messages being mistaken for integrated proof

### What it improves

- safe fan-out and explicit fan-in
- recovery after quota, account, process, or session interruptions
- clearer human approval boundaries
- review-led rework that stays bounded instead of silently becoming a rewrite
- reliable handoffs across human and agent execution modes

### What artifacts prove it is embedded

- [docs/process/parallel-work-coordination.md](../process/parallel-work-coordination.md)
- [coordination/README.md](../../coordination/README.md)
- task, handoff, workspace, ambiguity, and replanning templates
- lifecycle and hygiene rules that reconcile board state with repository reality

## Why This Matters To Different Readers

### Managers

This makes the critical path and scarce capacity visible without pretending a
static roadmap is a real-time delivery plan.

### Developers

This protects implementation focus: a clear owned lane, explicit exclusions,
and a known integration point are better than several agents "helping" in the
same area.

### Non-Developers

This explains why more agents do not automatically mean more progress. The
project still needs to know what can start, what is blocked, and what counts as
real completion.
