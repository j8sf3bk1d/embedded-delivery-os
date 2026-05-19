# Why Closeout Hygiene Matters

Projects rarely get into trouble because one feature was impossible to build.

They get into trouble because a phase looked done, everyone moved on, and the repo quietly stopped matching reality.

That mismatch creates a specific kind of drag:

- the next person reads stale status
- the next phase starts from the wrong assumptions
- deferred work disappears
- system and user docs lag behind the implementation

This lesson explains why closeout hygiene matters, and why "we finished the work" is not enough if the repo cannot prove what changed, what remains true, and what comes next.

## How It Was Learned Or Earned

The recurring mess looks like this:

- implementation lands
- the immediate problem seems solved
- everyone mentally moves to the next task
- the repo still reflects the old state

Then the damage shows up later:

- `docs/index.md` still points at the wrong active phase
- system or schema docs still describe the previous shape
- testing notes do not reflect what actually ran
- user-facing behavior changed but the user manual did not
- the real follow-up work survives only in chat memory

The obvious fix sounds reasonable:

- be more disciplined
- write better summaries
- remember to clean things up before moving on

Those help for a moment, but they do not survive pressure.

The problem is that closeout is often treated like an optional courtesy instead of a required workflow.

The insight is that completion is not only about building the thing. It is also about restoring the repo to a truthful operating state for the next phase, the next contributor, and the next restart.

## The Strategy

The strategy is to treat closeout hygiene as part of completion, not as a separate act of virtue.

That means every meaningful slice of work has to answer:

- what changed in reality
- which docs now need to match that reality
- which findings became issues, decisions, or later phases
- what is active now
- what the next person should trust

This is not bureaucracy for its own sake.

It is how a project stops leaking continuity every time a phase ends.

## The Tactics

This repo embeds closeout hygiene in several places so it is harder to skip accidentally.

### 1. The lifecycle defines closeout as a state transition rule

[docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md) says a phase is not complete just because code landed.

Closeout includes:

- focused validation
- required review work
- documentation updates
- current-state updates in the index and arc docs
- routing durable deferred work into issues or decisions

That matters because it changes closeout from "nice if we remember" into a real completion boundary.

### 2. Phase and implementation templates force doc refresh planning up front

[docs/process/templates/phase-template.md](../process/templates/phase-template.md) and [docs/process/templates/implementation-template.md](../process/templates/implementation-template.md) both require:

- named documentation updates
- docs cleanup and normalization notes
- review requirements
- closeout checks

This is important because the repo asks for the cleanup plan before the work disappears into execution.

### 3. Hygiene checkpoints exist for broader drift

[docs/reviews/hygiene-checkpoint-template.md](../reviews/hygiene-checkpoint-template.md) covers the failure mode where no single phase looks terribly wrong, but several phases together have left the repo stale or inconsistent.

It checks:

- index alignment
- arc and phase status consistency
- system, schema, QA, and user-doc freshness
- stale links and zombie planning notes

That gives the repo a way to recover from accumulated drift before it hardens into confusion.

### 4. Closeout minimums name the exact surfaces that commonly rot

The lifecycle doc explicitly calls out:

- `docs/index.md`
- arc and phase docs
- `docs/system/system.md`
- `docs/system/schema.md`
- `docs/process/change-map.md`
- QA docs
- `user-docs/user-manual.md`
- `docs/scratchpad/issues.md`

This matters because the real problem is usually not forgetting that "docs" exist. It is forgetting which docs carry operating truth.

## The Proof Or Belief Builders

You know this framework is working when the repo can survive a handoff or restart without needing a long memory download from chat.

### What it prevents

- stale active-phase and roadmap state
- deferred work disappearing between phases
- code and system docs quietly diverging
- user-visible behavior changing without user-facing guidance
- each restart beginning with archaeology

### What it improves

- cleaner phase transitions
- better restartability after context compression
- more trustworthy current-state docs
- less rework caused by hidden drift

### What artifacts prove it is embedded

- [docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md)
- [docs/process/templates/phase-template.md](../process/templates/phase-template.md)
- [docs/process/templates/implementation-template.md](../process/templates/implementation-template.md)
- [docs/reviews/hygiene-checkpoint-template.md](../reviews/hygiene-checkpoint-template.md)
- [docs/scratchpad/issues.md](../scratchpad/issues.md)
- [docs/index.md](../index.md)

If those artifacts stay current, the project preserves continuity at the end of each phase instead of throwing it away and rebuilding it later.

## Why This Matters To Different Readers

### Managers

This gives you a concrete definition of "done" that includes continuity, not just shipped code.

### Developers

This reduces the number of times the next task starts with stale docs, hidden follow-up, and unclear current state.

### Non-Developers

This explains why projects can feel chaotic even when people are working hard: the work finishes, but the project record does not.
