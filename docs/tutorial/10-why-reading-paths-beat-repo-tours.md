# Why Reading Paths Beat Repo Tours

Projects get slower and stranger when every new contributor, manager, or agent has to rediscover the same context from scratch.

The usual advice is:

- read the repo
- read the docs
- get up to speed

That sounds reasonable, but it fails in practice. Repos are not books. They are live systems with stale paths, uneven detail, and too many places to start.

This lesson explains why reading paths beat repo tours, and how that idea becomes an embedded workflow instead of a one-time onboarding note.

## How It Was Learned Or Earned

The pain is familiar:

- one session reads too much and burns time on irrelevant material
- another reads too little and misses the actual current state
- a third starts from whatever doc looked most official, even if it is no longer the right one

What keeps going wrong is not lack of effort. It is lack of routing.

The real failure mode is this:

- current state lives partly in docs, partly in code, and partly in chat memory
- "start here" is vague
- there is no task-shaped reading path

So people compensate by improvising archaeology.

That works badly for managers, developers, and non-developers alike:

- managers cannot tell which artifacts actually drive work
- developers waste time reading broad background instead of the active slice
- non-developers get the false impression that software delivery is just endless context swallowing

The insight is that onboarding is not the only problem. Mid-stream work needs routing too.

## The Strategy

The strategy is to replace "read the repo" with selective, path-dependent orientation.

That means:

- different tasks should start from different docs
- the repo should tell you what to read next, not just where things live
- the current state should be surfaced explicitly
- raw corpus material should not be treated as the default starting point

The goal is not maximum documentation coverage.

The goal is to minimize wasted reading while increasing the chance that a contributor starts from the right mental model.

This is especially important in agentic workflows, where prompt budget and context quality matter directly.

## The Tactics

In this repo, the strategy becomes several embedded mechanics.

### 1. Always-on routing

[AGENTS.md](../AGENTS.md) is the always-on operating contract.

It does not try to explain the whole repo. It routes by task:

- code changes
- UX work
- QA work
- security or config changes
- release or infrastructure work

That makes it useful mid-stream, not just at first contact.

### 2. Explicit cold-start path

[docs/process/cold-start.md](../process/cold-start.md) exists for true zero-context entry.

This is separate from `AGENTS.md` on purpose.

Why:

- cold-start orientation is important
- but it is not needed on every prompt
- always-on prompts should stay lightweight

### 3. Current-state map

[docs/index.md](../index.md) is the canonical current-state map.

It answers:

- what this project is
- what arc is current
- what phase is active
- what key docs matter right now
- what the immediate next steps are

### 4. Change-map reading paths

[docs/process/change-map.md](../process/change-map.md) routes work by touched area.

Instead of saying "go learn the whole system," it says:

- if you are changing this area, read these docs first
- run this smallest validation first
- escalate only when the blast radius grows

That is a huge difference. It turns reading into a workflow, not an act of faith.

### 5. Source authority before archaeology

[docs/system/source-authority.md](../system/source-authority.md) prevents dense source corpora from becoming a free-for-all.

It makes explicit:

- which docs are primary
- which are derived
- which are background only

Without that, reading paths collapse under the weight of "technically relevant" but operationally unhelpful material.

## The Proof Or Belief Builders

You can tell this framework is real when it changes behavior in obvious ways.

### What it prevents

- rereading broad repo history for a narrow task
- starting implementation from stale or background docs
- hiding the active phase in chat memory
- turning every new session into archaeology

### What it improves

- faster reorientation
- smaller and better context windows for agent work
- clearer handoffs between sessions
- less "I thought this was current" confusion

### What artifacts prove it is embedded

- [AGENTS.md](../AGENTS.md)
- [docs/process/cold-start.md](../process/cold-start.md)
- [docs/index.md](../index.md)
- [docs/process/change-map.md](../process/change-map.md)
- [docs/system/source-authority.md](../system/source-authority.md)

If those are maintained, the reading-path framework is alive. If they drift, the repo goes back to relying on memory and improvisation.

## Why This Matters To Different Readers

### Managers

This is how project state becomes inspectable instead of personality-dependent.

### Developers

This reduces archaeology and helps you start from the right slice of reality faster.

### Non-Developers

This is one of the first ways a chaotic vibe-coded project starts becoming a real delivery system.
