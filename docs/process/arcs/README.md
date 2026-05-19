# Arcs

## Active Arc

- [00 Project Foundation](./00-project-foundation/arc.md)
- Active phase: [Phase 01 - Source Intake and Distillation](./00-project-foundation/phases/01-source-intake-and-distillation/phase.md)
- Current note: this starter arc exists to demonstrate the workflow and should be replaced or updated once a real project brief lands

## Macro Roadmap

1. Project foundation
   Establish repo scaffold, default process, and cold-start orientation.
2. Source intake and distillation
   Import the PRD or source corpus, define authority, and distill the active implementation slice.
3. First implementation plan
   Define the first real arc, its boundaries, validation, and initial phase sequencing.
4. Build, validate, and iterate
   Use arc and phase docs to drive implementation with matching QA and review updates.

## Layout Rule

Store each arc in its own folder:

```txt
docs/process/arcs/<nn-arc-slug>/
  arc.md
  phases/
    <phase-slug>/
      phase.md
      design.md        # only when needed
      implementation.md # only when needed
```

Start with `phase.md` only. Split out `design.md` and `implementation.md` when the combined phase file becomes hard to use.

## Lifecycle Rule

Use [Phase And Arc Lifecycle](../phase-and-arc-lifecycle.md) as the canonical rule set for:

- when arcs and phases become active
- when they can be marked complete
- how review findings should be routed
- which docs must be refreshed at closeout
