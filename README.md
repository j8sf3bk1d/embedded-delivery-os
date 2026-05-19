# Embedded Delivery OS

Most software process fails because it lives outside the work. This repository is a repo-native workflow operating system for software delivery: a way to embed orientation, source authority, planning, review, validation, and release hygiene directly into the project itself.

The goal is not to add more process theater. The goal is to turn recurring project mess into durable workflow that survives handoffs, context loss, changing contributors, and agent-driven execution.

## What This Is

This repo is meant to be:

- a cloneable starter scaffold for new projects
- a concrete example of embedded workflow design
- a public teaching artifact for modern software delivery with humans and agents

## The New Opportunity

The old pattern is familiar:

- process lives in chat, meetings, and memory
- docs drift away from implementation reality
- reviews find issues but do not reliably change the project state
- contributors rebuild context from scratch
- delivery gets slower as coordination gets messier

The opportunity is to embed the coordination layer into the repo itself:

- reading paths instead of repo tours
- source authority instead of document ambiguity
- arcs and phases instead of fuzzy project state
- review routing instead of orphaned findings
- release and infrastructure checklists instead of hidden operational knowledge

## What You Get

- a concise project map in `docs/index.md`
- a durable system orientation and schema home
- an arc and phase work model with reusable templates
- a change map so future work starts with the right docs and smallest validation
- QA, review, scratchpad, and user-doc placeholders
- canonical reference docs in `docs/reference/`
- a tutorial track that explains the operating model, not just the artifacts

## Start Here

Choose the smallest relevant path:

- Fast public overview:
  [docs/tutorial/05-best-of-reading-paths.md](docs/tutorial/05-best-of-reading-paths.md)
- Theory and model:
  [docs/tutorial/00-theory-of-operation.md](docs/tutorial/00-theory-of-operation.md),
  [docs/tutorial/09-why-projects-need-an-embedded-workflow-operating-system.md](docs/tutorial/09-why-projects-need-an-embedded-workflow-operating-system.md),
  [docs/tutorial/06-embedded-workflow-system-diagram.md](docs/tutorial/06-embedded-workflow-system-diagram.md)
- Use this as a project scaffold:
  [docs/index.md](docs/index.md),
  [docs/system/system.md](docs/system/system.md),
  [docs/system/source-authority.md](docs/system/source-authority.md),
  [docs/process/arcs/README.md](docs/process/arcs/README.md)

If a PRD or source corpus has been added, read the derived authority and distillation docs before diving into raw source material.

For a dedicated zero-context startup flow, use [docs/process/cold-start.md](docs/process/cold-start.md).
For the shortest path from scaffold to real project, use [docs/process/first-real-use.md](docs/process/first-real-use.md).

## When You Duplicate This Repo

For a direct adoption checklist and starter prompt, use [docs/process/first-real-use.md](docs/process/first-real-use.md).

1. Rename the project in [README.md](README.md) and [docs/index.md](docs/index.md).
2. Add the real product brief, PRD, or source docs under [docs/reference/prd-v0/](docs/reference/prd-v0/README.md).
3. Update [docs/system/source-authority.md](docs/system/source-authority.md) to identify the real source-of-truth documents.
4. Replace the starter arc and phase with the first real planning slice for the project.
5. Replace placeholder setup, env, and test commands with stack-specific commands.
6. Update [docs/process/change-map.md](docs/process/change-map.md) so touched paths map to the real codebase.

## Default Working Instruction

For a cold-start coding agent, the intended handoff is:

1. Read this `README.md`.
2. Read `docs/index.md` and the linked current arc and phase.
3. Read `docs/system/system.md`, `docs/system/source-authority.md`, and the relevant change-map row.
4. Then read the PRD or active design docs.

If you want a copy-paste starter prompt for the first real session, use [docs/process/first-real-use.md](docs/process/first-real-use.md).

## Current State

This repo is intentionally stack-neutral. It contains documentation and process scaffolding only, plus conservative `.gitignore` and `.env.example` starters. Replace placeholders as soon as the real runtime shape is known.
