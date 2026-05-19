# Audiences And Reading Paths

This tutorial is meant for three overlapping audiences:

- managers who already do fragments of this instinctively but never formalized it
- developers who have been clearing tickets without seeing the larger delivery system
- non-developers who do not know SDLC vocabulary but know their projects keep becoming chaotic

The same core system should be legible to all three without flattening it into one voice.

## Audience Model

### Managers

What they usually recognize:

- recurring project chaos
- hidden dependencies between planning, design, implementation, and release
- repeated re-explanation cost

What they often need:

- language for the patterns they already sense
- a concrete operating model, not abstract "best practices"
- a way to explain why this is leverage, not bureaucracy

### Developers

What they usually recognize:

- local implementation pain
- rework from unclear specs or stale docs
- review and validation gaps

What they often need:

- the bigger picture that connects tickets to delivery quality
- traceability from product intent to code change to release
- a process model that respects engineering reality

### Non-Developers

What they usually recognize:

- vibe-coded projects get messy fast
- every new session starts with re-explaining context
- the app can "work" and still feel broken or confusing

What they often need:

- pain-first explanations instead of jargon-first explanations
- visible cleanup mechanisms
- a way to understand why structure matters before they learn SDLC terms

## Reading Paths

### Manager Path

1. [00-theory-of-operation.md](00-theory-of-operation.md)
2. [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)
3. [02-embedded-workflows-overview.md](02-embedded-workflows-overview.md)
4. [05-best-of-reading-paths.md](05-best-of-reading-paths.md)
5. the lesson most aligned to the current pain point

Focus:

- recurring failure modes
- operating leverage
- where hidden coordination costs are being captured explicitly

### Developer Path

1. [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)
2. [02-embedded-workflows-overview.md](02-embedded-workflows-overview.md)
3. [05-best-of-reading-paths.md](05-best-of-reading-paths.md)
4. [03-lessons-map.md](03-lessons-map.md)
5. repo-native artifact links inside the relevant lesson
6. [01-framework-for-teaching-frameworks.md](01-framework-for-teaching-frameworks.md) if you want the meta layer on how the lessons are constructed

Focus:

- how the workflows change day-to-day engineering behavior
- what artifacts carry operational memory
- what closes the loop between design, implementation, and review

### Non-Developer Path

1. [00-theory-of-operation.md](00-theory-of-operation.md)
2. [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)
3. [05-best-of-reading-paths.md](05-best-of-reading-paths.md)
4. this file
5. lessons that start from obvious pain

Focus:

- why projects keep becoming chaotic
- what each workflow fixes
- why "more prompts" is not the same thing as a delivery system

## Authoring Rule

Each final lesson should make itself legible to all three audiences.

A simple way to do that:

- start from the pain in common language
- explain the strategy in clear, non-buzzword terms
- show the repo artifact that embodies the tactic
- add short audience-specific notes only where helpful
