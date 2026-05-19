# Why Source Authority Must Exist Before Implementation

A surprising amount of software confusion starts before any code is written.

The product team has:

- a PRD
- some chat exports
- maybe a scope doc
- maybe strategy notes
- maybe a brainstorm that produced good ideas but no boundaries

All of it feels relevant, so all of it starts competing for authority.

That is the problem.

This lesson explains why source authority has to exist before implementation, and why "just use your judgment" is not enough once the source corpus gets dense.

## How It Was Learned Or Earned

The recurring mess looks like this:

- one person implements from the PRD
- another remembers an important chat note
- a third finds a strategy memo and treats it like scope
- someone else assumes the latest brainstorm overrides all of it

Everyone is acting in good faith. The failure is structural.

What keeps going wrong is that imported source material arrives without an authority model.

That creates predictable damage:

- contradictory requirements
- accidental scope widening
- repeated archaeology
- "but I thought this doc was the real one" debates

The obvious fix sounds simple:

- be more careful
- read everything
- use common sense

That does not scale.

Once the source set is large enough, "read everything" becomes a way to hide the fact that no one has declared which documents actually control implementation.

The insight is that raw source material is not self-organizing. A repo has to classify it explicitly before implementation starts.

## The Strategy

The strategy is to separate source material into authority classes and force implementation to start from the right class first.

At minimum, that means distinguishing:

- primary source of truth
- implementation-boundary or derived docs
- background or strategy docs
- archive or provenance-only docs

This is not just a filing exercise.

It changes how work begins:

- not every relevant document gets equal weight
- derived docs can replace repeated archaeology
- background material can stay available without silently controlling scope

The goal is not to suppress useful context.

The goal is to stop context from behaving like hidden scope.

## The Tactics

This repo encodes that strategy in a few concrete ways.

### 1. Source authority is a first-class artifact

[docs/system/source-authority.md](../system/source-authority.md) is the canonical place to say:

- which files define product intent
- which files shape the implementation slice
- which files are context only
- which files are kept for provenance

That one move eliminates a huge amount of ambiguity.

### 2. Raw source material has a bounded home

[docs/reference/prd-v0/README.md](../reference/prd-v0/README.md) defines the intake area for imported product material.

That matters because raw source material needs to be preserved without automatically becoming the default reading path for future work.

### 3. Derived docs are expected, not optional

The repo includes:

- [docs/process/templates/source-authority-template.md](../process/templates/source-authority-template.md)
- [docs/process/templates/distillation-template.md](../process/templates/distillation-template.md)

These templates make it normal to create:

- an authority map
- a concise working distillation

That is how active implementation gets protected from repeated archaeology.

### 4. The task routing enforces the pattern

[AGENTS.md](../AGENTS.md) routes PRD intake or source reconciliation through source authority first.

That is important because the authority model only matters if contributors and agents are told to use it before they start making decisions.

### 5. The change map preserves the distinction

[docs/process/change-map.md](../process/change-map.md) tells the repo not to treat every reference doc as equal authority by default.

That keeps source-of-truth logic embedded in the work path, not stranded in one isolated doc.

## The Proof Or Belief Builders

You know this framework is real when implementation stops starting from whichever source someone happened to open last.

### What it prevents

- implementing from background docs by accident
- scope growth caused by brainstorm material
- repeated arguments over which document "really counts"
- forcing every contributor to reread the raw corpus from scratch

### What it improves

- faster planning
- clearer scope boundaries
- better handoffs
- less drift between intent and execution

### What artifacts prove it is embedded

- [docs/system/source-authority.md](../system/source-authority.md)
- [docs/reference/prd-v0/README.md](../reference/prd-v0/README.md)
- [docs/process/templates/source-authority-template.md](../process/templates/source-authority-template.md)
- [docs/process/templates/distillation-template.md](../process/templates/distillation-template.md)
- [AGENTS.md](../AGENTS.md)

If those artifacts are maintained, the repo can absorb dense source material without letting it become chaos.

## Why This Matters To Different Readers

### Managers

This prevents planning drift from turning into implementation drift just because too many docs are floating around.

### Developers

This keeps you from implementing the wrong thing because the repo never told you which document actually controls the work.

### Non-Developers

This is how a project stops being governed by whichever note or chat someone remembers most vividly.

