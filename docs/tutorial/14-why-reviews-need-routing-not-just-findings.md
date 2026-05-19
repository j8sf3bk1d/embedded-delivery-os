# Why Reviews Need Routing, Not Just Findings

A review can be correct and still fail completely.

That sounds odd until you see what happens in real projects:

- a review finds the right issue
- everyone agrees it matters
- maybe it even gets discussed carefully
- and then it never becomes durable follow-up

At that point the review produced insight, but not control.

This lesson explains why reviews need routing, not just findings, and why review quality depends as much on follow-up mechanics as on technical judgment.

## How It Was Learned Or Earned

The recurring mess looks like this:

- issues are discovered during design review, code review, or a sweep pass
- they are written down in prose
- they may even sound important
- but no one encoded what should happen next

Then one of three bad outcomes follows:

- the issue is forgotten
- the issue lives only in a long thread
- the issue lingers as vague unease rather than becoming a bounded work item

The obvious fix is usually:

- "we should remember this"
- "let's keep an eye on it"
- "we'll come back to that later"

That is not a process. That is a delay mechanism.

The insight is that a review finding is only useful if the repo knows where it goes next.

## The Strategy

The strategy is to treat reviews as routing points, not just observation points.

When a review finds something important, the system should answer:

- does this belong in the active phase?
- does this become a durable issue?
- does this require a decision record?
- does this deserve a new phase or cleanup pass?

Without that routing layer, reviews mostly create sentiment:

- "something feels off"
- "there is a risk here"
- "this should be revisited"

With routing, reviews create state change.

That is the real goal.

## The Tactics

This repo encodes review routing in several linked artifacts.

### 1. Reviews capture findings in a reusable shape

[docs/reviews/review-template.md](../reviews/review-template.md) does more than ask for opinions.

It asks for:

- findings first
- risk and impact
- follow-ups
- recommendation

That structure matters because it creates a clean handoff from observation to action.

### 2. Hygiene checkpoints catch drift beyond one phase

[docs/reviews/hygiene-checkpoint-template.md](../reviews/hygiene-checkpoint-template.md) exists for broader sweeps.

This matters because some findings are not feature-specific bugs. They are repo-health problems:

- stale docs
- inconsistent status
- missing review gates
- drift across multiple phases

Those need a different review context than a single phase completion pass.

### 3. Workflow reviews route UX-specific drift

[docs/reviews/workflow-coherence-review-template.md](../reviews/workflow-coherence-review-template.md) exists because some findings are really workflow-model problems, not implementation bugs.

That prevents UX drift from being flattened into "random polish work."

### 4. Lifecycle rules decide what findings become

[docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md) defines finding-routing rules explicitly:

- immediate same-phase follow-up stays in the active phase
- deferred or cross-phase issues go to the issue register
- durable architecture or risk choices can become decision records
- large enough fixes can become a new phase

That is the heart of the framework.

### 5. The issue register keeps durable findings alive

[docs/scratchpad/issues.md](../scratchpad/issues.md) now works as a lightweight risk register.

That matters because not every review finding should explode into a new phase immediately, but it still needs a durable home.

## The Proof Or Belief Builders

You know this framework is working when reviews stop disappearing into prose.

### What it prevents

- good findings being forgotten
- review notes living only in chat or one-off docs
- vague awareness of risk without ownership
- drift surviving multiple review rounds because nothing changed state

### What it improves

- clearer follow-up
- better accountability
- cleaner separation between immediate fixes and durable deferred risks
- more trustworthy review rituals

### What artifacts prove it is embedded

- [docs/reviews/review-template.md](../reviews/review-template.md)
- [docs/reviews/hygiene-checkpoint-template.md](../reviews/hygiene-checkpoint-template.md)
- [docs/reviews/workflow-coherence-review-template.md](../reviews/workflow-coherence-review-template.md)
- [docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md)
- [docs/scratchpad/issues.md](../scratchpad/issues.md)

If those artifacts are maintained and actually used, a review can change the repo's state instead of just producing commentary.

## Why This Matters To Different Readers

### Managers

This is how review stops being performative and starts becoming a control mechanism.

### Developers

This gives technical findings a clean path into real work instead of leaving them stranded in prose.

### Non-Developers

This is how a project stops repeating the same mistakes just because everyone noticed the issue but no one encoded what should happen next.
