# Why UX Keeps Regressing Into Screen Soup

A product can gain features and still get worse.

That sounds paradoxical until you see the pattern clearly:

- more screens appear
- more data becomes visible
- more actions become possible
- and yet the product feels less obvious, less focused, and more exhausting

This is not just a design-polish problem. It is usually a workflow-modeling problem.

This lesson explains why UX keeps regressing into screen soup and why the fix is not "do better design later." The fix is an explicit middle layer between outcomes and implementation.

## How It Was Learned Or Earned

The recurring mess looks like this:

- the product has enough capability to be useful
- but the surfaces feel shaped by the system's internals rather than by user goals
- so users can technically do things, but they cannot easily tell what matters, what comes next, or where a path should lead

What keeps going wrong is feature-first accretion.

Teams often know they should "think about UX," but the actual process still jumps from:

- outcome ideas
- straight into features, screens, or data surfaces

At that point, screens start owning too much:

- primary actions
- diagnostic detail
- setup machinery
- trust explanations
- operational state

Everything technically belongs somewhere, so it all gets poured into visible surfaces. That is how screen soup forms.

The deeper insight is that generic UX principles are not enough. They help you critique the mess after it exists, but they do not force outcome-to-path-to-surface traceability before the mess is built.

## The Strategy

The strategy is to insert an explicit workflow-modeling layer between product intent and implementation.

That layer answers four questions:

1. what outcomes matter
2. what paths get users to those outcomes
3. which surfaces own which steps in those paths
4. what data each surface needs to do its job cleanly

Without that layer, screens tend to follow:

- entity structure
- internal module boundaries
- whatever data is already easiest to show

With that layer, screens can instead follow:

- user progress
- decision points
- trust checkpoints
- progressive disclosure

This does not eliminate redesign. It makes redesign far more intentional and less repetitive.

## The Tactics

This repo now encodes that middle layer explicitly.

### 1. Experience models

[docs/process/templates/experience-model-template.md](../process/templates/experience-model-template.md) is the core stabilizer.

It forces an arc or initiative to model:

- outcomes
- paths
- surface ownership
- screen data contracts
- progressive disclosure rules

That is the missing bridge between "we know the feature set" and "the product actually feels coherent."

### 2. Workflow coherence reviews

[docs/reviews/workflow-coherence-review-template.md](../reviews/workflow-coherence-review-template.md) exists because UX drift often appears only after multiple phases land.

It checks:

- whether the main user paths still make sense
- whether screens have clear primary goals
- whether data is answering the right question at the right point
- whether navigation has drifted toward implementation structure

This is not a generic design review. It is specifically about path coherence.

### 3. Lifecycle triggers

[docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md) now says that meaningful user-facing arcs should have an experience model unless there is a clear reason not to.

That matters because it turns workflow modeling into a trigger-based requirement, not an optional afterthought.

### 4. Phase and design prompts

The phase and design templates now ask directly:

- does this phase depend on or update an experience model?
- what outcomes does this design serve?
- which path steps does it own?
- what should it explicitly not own?

That prevents "we'll figure out the flow later" from staying invisible.

### 5. Screenshot-assisted review keeps visual drift from hiding in the code

[docs/reference/ux-process.md](../reference/ux-process.md), [docs/qa/manual-testing.md](../qa/manual-testing.md), and the screenshot archive guidance in [docs/archive/screenshots/index.md](../archive/screenshots/index.md) now treat visual review as a real workflow, not as an optional afterthought.

That matters because code alone often hides the part of UX that users actually feel:

- density
- visual hierarchy
- contrast
- spacing
- responsive drift

The newer guidance also distinguishes between two useful kinds of evidence:

- milestone archive captures for before-and-after review
- screenshot assertions or baselines only when a surface is stable enough that automated comparison will help more than it churns

### 6. Visual guardrails and harness choices make screenshot review usable instead of vague

[docs/process/templates/visual-style-guardrails-template.md](../process/templates/visual-style-guardrails-template.md) and the newer QA guidance add two missing pieces:

- what the product should visually bias toward
- what the lightest useful screenshot harness should be for the runtime

That matters because "review screenshots" is still too vague unless the project knows:

- what good density looks like
- which anti-patterns to avoid
- whether this is a static prototype, a normal dev-server app, or a stateful app that needs isolated local data for captures

Without that, visual review either becomes subjective or quietly disappears.

### 7. Change-map routing for flow work

[docs/process/change-map.md](../process/change-map.md) includes a dedicated row for:

- experience models
- IA docs
- flow docs
- workflow reviews

That is important because it tells contributors that UX work has its own operating path, not just a general "design matters" reminder.

## The Proof Or Belief Builders

You can tell this framework is real when the product stops behaving like a pile of visible internals.

### What it prevents

- screens that own too many unrelated jobs
- navigation shaped by modules instead of user progress
- "dashboard of everything" overview pages
- late rediscovery that the real workflow was never modeled

### What it improves

- clearer primary paths
- better progressive disclosure
- better separation between action, trust, and machinery
- less rework caused by building screens before their jobs are clear

### What artifacts prove it is embedded

- [docs/process/templates/experience-model-template.md](../process/templates/experience-model-template.md)
- [docs/reviews/workflow-coherence-review-template.md](../reviews/workflow-coherence-review-template.md)
- [docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md)
- [docs/process/templates/phase-template.md](../process/templates/phase-template.md)
- [docs/process/templates/design-template.md](../process/templates/design-template.md)
- [docs/process/templates/visual-style-guardrails-template.md](../process/templates/visual-style-guardrails-template.md)
- [docs/reference/ux-process.md](../reference/ux-process.md)
- [docs/qa/test-strategy.md](../qa/test-strategy.md)

### What the repo has learned from real examples

The strongest supporting examples came from real projects where later phases had to explicitly correct a common failure:

- capability existed
- but user paths were weaker than the feature set

That is the signature of missing workflow modeling.

## Why This Matters To Different Readers

### Managers

This gives you a way to explain why "the team shipped the features" and "the product still feels off" can both be true.

### Developers

This protects you from building surfaces that are technically complete but destined for rework because their job was never clearly defined.

### Non-Developers

This explains why vibe-coded apps often feel confusing even when they visibly have lots of stuff in them: the paths were never modeled, only the screens were.
