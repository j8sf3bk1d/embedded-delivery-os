# Embedded Workflows Overview

This repo's process model can be understood as a stack of embedded workflows.

Each workflow exists because some recurring coordination burden became too expensive to keep handling manually.

## Workflow Layers

### Orientation And Reading Paths

Problem:
contributors and agents waste time rereading the wrong things or missing the current state.

Repo artifacts:

- `AGENTS.md`
- `README.md`
- `docs/index.md`
- `docs/process/cold-start.md`
- `docs/process/change-map.md`

### Source Authority And Distillation

Problem:
raw PRDs, chats, and strategy docs are not equal authority, but teams often treat them that way under pressure.

Repo artifacts:

- `docs/system/source-authority.md`
- `docs/process/templates/source-authority-template.md`
- `docs/process/templates/distillation-template.md`

### Arc And Phase Execution

Problem:
work is often "current" only in chat memory, so active phases, blockers, and closeout rules drift.

Repo artifacts:

- `docs/process/arcs/`
- `docs/process/phase-and-arc-lifecycle.md`
- arc, phase, design, and implementation templates

### Review And Finding Routing

Problem:
reviews happen, but their findings do not always become durable follow-up.

Repo artifacts:

- `docs/reviews/review-template.md`
- `docs/reviews/hygiene-checkpoint-template.md`
- `docs/reviews/workflow-coherence-review-template.md`
- `docs/scratchpad/issues.md`

### UX And Workflow Coherence

Problem:
features arrive before user paths are fully modeled, so screens drift toward implementation structure and get reworked later.

Repo artifacts:

- `docs/reference/ux-process.md`
- `docs/process/templates/experience-model-template.md`
- `docs/reviews/workflow-coherence-review-template.md`

### Release And Operations Readiness

Problem:
teams can build features without making the path to real deployment, setup, and external use explicit.

Repo artifacts:

- `docs/system/external-resources-and-infrastructure.md`
- `docs/qa/release-readiness-checklist.md`
- `docs/qa/test-strategy.md`

## Tutorial Point

The repo is not trying to teach "documentation."

It is trying to teach how recurring coordination pain can be turned into embedded, reusable workflow mechanics.
