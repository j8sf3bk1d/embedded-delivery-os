# Phase 00 - Cold-Start Scaffold

## Status

Complete

## Design

### Intent

Create the minimum durable scaffold needed for a future project to start cleanly.

### User or system outcome

A future contributor can open the repo cold, read a small number of docs, and understand where product inputs, current plans, system notes, QA guidance, and templates live.

### Constraints and assumptions

- the implementation stack is not known yet
- the repo must remain reusable across different project types
- canonical process references already exist under `docs/reference/`

### Interfaces and boundaries

- top-level orientation starts in `README.md`
- current-state navigation lives in `docs/index.md`
- derived authority and system notes live in `docs/system/`
- process and phase planning live in `docs/process/`

### Data and state ownership

No product-specific state exists yet.

### Edge cases and risks

- placeholders may accidentally be treated as final project truth
- generic commands may become stale after a stack is chosen

### Definition of done

- base docs and folders exist
- templates are present
- QA, review, and scratchpad docs are initialized
- git and conservative ignore/env scaffolds exist

### Validation plan

- review all created docs for link integrity and internal consistency
- confirm the repo is initialized as git

## Implementation

### Task breakdown

- initialize git
- create starter README and docs index
- add system, process, QA, review, archive, and user-doc scaffolding
- add source-authority, templates, and starter intake folder

### Dependencies

- canonical references already present in `docs/reference/`

### Expected files or areas touched

- repo root
- `docs/`
- `user-docs/`

### Checkpoints

- scaffold folders created
- top-level orientation complete
- templates added

### Validation commands

- `git status --short`

### Documentation updates needed

- replace starter placeholders once the real project exists

### Completion notes

This phase is meant to be copied forward, then quickly superseded by project-specific planning.

