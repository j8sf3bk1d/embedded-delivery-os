# Phase 01 - Source Intake, Discovery, and Distillation

## Status

Active

## Design

### Intent

Turn raw source material or live discovery conversations into a small, explicit set of documents that a future implementation agent can trust.

### User or system outcome

A future contributor does not need to reread every imported file to understand what the product is trying to do or what the first implementation slice should cover.

### Constraints and assumptions

- source material may arrive as PRDs, exports, chat logs, brainstorm notes, or copied specs
- in some projects no PRD exists yet and the first authoritative brief must be created from guided discussion
- raw materials should be preserved, but they should not all become equal authority

### Interfaces and boundaries

- raw source material belongs in `docs/reference/prd-v0/`
- a conversation-derived first brief also belongs in `docs/reference/prd-v0/` until a fuller PRD exists
- authority and distillation notes belong in `docs/system/`
- phase and arc planning should use derived docs rather than raw corpus archaeology

### Data and state ownership

Not applicable until the real project exists.

### Edge cases and risks

- multiple source docs may disagree
- imported docs may include stale or wrapper-generated text
- discovery conversations may stay trapped in chat memory instead of becoming a durable brief
- future work may keep referencing raw docs directly instead of derived docs

### Definition of done

- `docs/system/source-authority.md` names the real source-of-truth files
- the active slice has a short derived distillation if the corpus is dense
- a first discovery brief exists when no formal PRD was provided
- `docs/index.md` points to the right planning and source docs

### Validation plan

- verify the authority map reflects actual source usage
- confirm the active arc and change map point to derived docs first

## Implementation

### Task breakdown

- import source docs or run guided discovery if none exist yet
- create `docs/reference/prd-v0/10-discovery-brief.md` when discovery is the starting point
- classify them by authority level
- create a concise working distillation if needed
- update the active arc and next steps

### Dependencies

- product brief or PRD must exist, or discovery access to the human source of intent must exist

### Expected files or areas touched

- `docs/reference/prd-v0/`
- `docs/system/source-authority.md`
- `docs/index.md`
- first real arc and phase docs

### Checkpoints

- source corpus imported
- or first discovery brief created
- authority map updated
- first distillation completed

### Validation commands

- docs consistency review
- `git status --short`

### Documentation updates needed

- replace starter placeholders with real source links and project names

### Current progress

- starter intake location exists
- authority model scaffold exists
- discovery and first-brief process guidance now exists
- waiting on project-specific source material or live discovery input
