# Why Decision Records Should Be Triggered, Not Overused

Some teams never write decisions down, so the same arguments keep coming back.

Other teams swing too far the other direction and start documenting every small choice until the decision log becomes noise.

Both failure modes are expensive.

This lesson explains why decision records should be triggered, not overused, and why the value of a decision log depends on when it is created, not just whether it exists.

## How It Was Learned Or Earned

The recurring mess usually takes one of two forms.

In the first version:

- a meaningful architecture or operational choice gets made
- people think the rationale is obvious
- later contributors cannot tell why that path was chosen
- the same decision gets reopened in fragments

In the second version:

- the team tries to be disciplined
- lots of small choices get recorded
- the decision folder fills with low-signal entries
- nobody can tell which records still matter

The obvious fix usually sounds like:

- "we should write more ADRs"
- or, after that fails, "decision docs are overhead"

Both reactions miss the point.

The insight is that decision records are most useful when they are created by trigger, not by habit alone.

They should capture durable choices that future contributors would reasonably need explained. They should not become a diary of every local move.

## The Strategy

The strategy is to make decision records conditional on impact.

A decision record should exist when a change creates a durable choice about:

- architecture or runtime posture
- data ownership or trust boundaries
- auth, dependency, or external-service posture
- scope or workflow commitments with meaningful technical consequences

If a choice is temporary, local to one phase, or obvious from the implementation and phase docs, it often does not need its own record.

This keeps the decision layer small enough to trust and important enough to revisit.

## The Tactics

This repo encodes that restraint directly.

### 1. The decisions folder defines good candidates

[docs/system/decisions/README.md](../system/decisions/README.md) does not say "record everything."

It names strong candidates:

- architecture or runtime posture
- data ownership boundaries
- auth or trust-boundary choices
- dependency or package-manager posture
- external-service decisions
- meaningful UX or workflow commitments with technical impact

That creates a filter instead of a dumping ground.

### 2. Lifecycle rules trigger decisions from real events

[docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md) says to create a decision record when a review finding forces a durable architecture, security, scope, or operational choice.

That matters because it ties decision creation to moments of consequence:

- a review surfaces a real boundary question
- a phase uncovers a durable tradeoff
- closeout reveals a choice that future work must inherit

This is much better than writing decisions on a calendar or by template ritual.

### 3. Templates keep decisions linked to active work

[docs/process/templates/decision-template.md](../process/templates/decision-template.md) is intentionally compact:

- context
- decision
- alternatives considered
- tradeoffs
- known limitations
- related files and docs

That shape keeps the record useful without turning it into a mini-spec.

Related templates such as [docs/process/templates/phase-template.md](../process/templates/phase-template.md) and [docs/process/templates/implementation-template.md](../process/templates/implementation-template.md) also explicitly call out `docs/system/decisions/*.md` when a phase changes durable reality.

### 4. The change map treats decisions as part of high-risk work

[docs/process/change-map.md](../process/change-map.md) repeatedly routes system, infra, config, and trust-boundary work through relevant decisions.

That is important because a decision record only matters if later work knows to read it before repeating the same debate.

## The Proof Or Belief Builders

You know this framework is working when the decision log stays short, legible, and disproportionately useful.

### What it prevents

- repeating old architecture arguments
- losing rationale for high-impact choices
- polluting the decision log with trivial local moves
- treating phase notes and decision records as interchangeable

### What it improves

- continuity across long-running work
- clarity around inherited constraints
- trust in the decisions folder as a high-signal surface
- better handoffs between planning, review, and implementation

### What artifacts prove it is embedded

- [docs/system/decisions/README.md](../system/decisions/README.md)
- [docs/process/phase-and-arc-lifecycle.md](../process/phase-and-arc-lifecycle.md)
- [docs/process/templates/decision-template.md](../process/templates/decision-template.md)
- [docs/process/templates/phase-template.md](../process/templates/phase-template.md)
- [docs/process/templates/implementation-template.md](../process/templates/implementation-template.md)
- [docs/process/change-map.md](../process/change-map.md)

If those artifacts stay aligned, the repo can preserve the important choices without turning the decision layer into background noise.

## Why This Matters To Different Readers

### Managers

This gives you a durable explanation surface for consequential choices without forcing the team to formalize every small move.

### Developers

This keeps high-impact rationale findable while avoiding an ADR graveyard full of documents no one reads.

### Non-Developers

This explains why some choices need a permanent record and others should stay inside the normal flow of project work.
