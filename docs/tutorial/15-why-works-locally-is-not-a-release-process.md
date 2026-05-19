# Why "Works Locally" Is Not A Release Process

There is a dangerous moment in many projects when everyone can feel the temptation:

- the feature works
- the app starts
- a few happy paths passed

So the team starts acting as if the work is ready for external use.

That leap causes a lot of avoidable damage.

This lesson explains why "works locally" is not a release process, and why release readiness has to be treated as a separate workflow with different questions.

## How It Was Learned Or Earned

The recurring mess looks like this:

- the team validates feature behavior
- the implementation seems coherent
- then real deployment, setup, trust, or operator-use assumptions show up late

At that point people realize they never explicitly checked:

- what the release boundary actually is
- what gets packaged or deployed
- what external services must exist
- whether setup docs are accurate
- whether trust-boundary behavior is good enough for broader use

The obvious fix sounds like:

- run more tests
- do one more pass
- double-check manually before shipping

Those can help, but they are not enough.

The problem is not only validation depth. It is that release readiness asks different questions than feature completion.

The insight is that "ready to merge" and "ready for external use" are not the same state.

## The Strategy

The strategy is to split release readiness into its own workflow.

That workflow has to answer:

- what exactly is being shipped or exposed
- what setup or provisioning assumptions exist
- what trust boundaries are involved
- what documentation must be true for an operator or user
- what important paths were validated, deferred, or left risky

This does not mean every project needs heavyweight release ceremony.

It means the repo must stop pretending that feature validation and release validation are identical.

## The Tactics

This repo encodes that separation directly.

### 1. Release readiness has its own checklist

[docs/qa/release-readiness-checklist.md](../qa/release-readiness-checklist.md) asks a different set of questions than ordinary feature validation.

It checks:

- scope anchor
- packaging boundary
- installation or startup path
- core functional validation
- trust and privacy boundaries
- operator and user-facing accuracy
- operational readiness

That is not just "more testing." It is a different evaluation frame.

### 2. External dependencies are treated as first-class

[docs/system/external-resources-and-infrastructure.md](../system/external-resources-and-infrastructure.md) exists because release posture depends on more than code.

If a system relies on:

- databases
- object storage
- email providers
- auth services
- third-party APIs

then those assumptions need a human-executable home.

Without that, "works locally" hides operational dependency risk.

### 3. Test strategy names release as a separate trigger

[docs/qa/test-strategy.md](../qa/test-strategy.md) now explicitly says that release, external use, and deployment require broader validation and release-readiness checks.

That matters because it stops launch claims from piggybacking casually on ordinary development checks.

### 4. Task routing distinguishes release work

[AGENTS.md](../AGENTS.md) and [docs/process/change-map.md](../process/change-map.md) now treat:

- release-readiness docs
- deployment notes
- external resources

as their own work path.

This is important because release problems often come from assuming they are just ordinary feature work with a little extra QA.

## The Proof Or Belief Builders

You know this framework is working when the repo can explain the difference between "the feature functions" and "the system is fit for broader use."

### What it prevents

- treating happy-path feature validation as launch proof
- vague packaging boundaries
- setup and provisioning surprises
- external trust-boundary assumptions staying implicit
- operator docs lagging behind the actual release claim

### What it improves

- cleaner launch decisions
- more honest scope and caveat statements
- fewer late operational surprises
- better separation between implementation confidence and release confidence

### What artifacts prove it is embedded

- [docs/qa/release-readiness-checklist.md](../qa/release-readiness-checklist.md)
- [docs/system/external-resources-and-infrastructure.md](../system/external-resources-and-infrastructure.md)
- [docs/qa/test-strategy.md](../qa/test-strategy.md)
- [AGENTS.md](../AGENTS.md)
- [docs/process/change-map.md](../process/change-map.md)

If those artifacts stay current, the repo can make more credible release claims instead of just escalating local confidence into public confidence.

## Why This Matters To Different Readers

### Managers

This gives you a concrete way to separate "we built it" from "we can responsibly ship it."

### Developers

This prevents release work from showing up as a vague late-stage scramble after the feature already looked done.

### Non-Developers

This explains why a project can seem finished in a demo and still not be ready for real use.

