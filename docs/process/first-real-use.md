# First Real Use

Use this document when you are turning the scaffold into a real project.

## Purpose

This repo has two valid modes:

- teaching mode: keep the tutorial so the workflow system stays explainable
- project mode: keep only the operating docs you actually want in the live repo

You do not need to delete the tutorial immediately. Decide whether it should stay as reference material, move to `docs/archive/`, or leave the project repo entirely.

## First Real Use Checklist

1. Rename the project in `README.md` and `docs/index.md`.
2. Add the real PRD, idea sketch, exported chats, or source corpus under `docs/reference/prd-v0/`. If no PRD exists yet, create `docs/reference/prd-v0/10-discovery-brief.md` first.
3. Update `docs/system/source-authority.md` to name the real primary, secondary, and archive-only sources.
4. Distill the active implementation slice if the source corpus is dense or contradictory.
5. Replace the starter arc and phase with the first real planning slice for the project.
6. Update `docs/process/change-map.md` so the touched paths and validation guidance reflect the actual codebase.
7. Replace placeholder env, test, release, and infrastructure guidance with stack-specific reality.
8. Decide whether to keep, archive, or remove `docs/tutorial/`.

## Tutorial Decision

Keep `docs/tutorial/` if:

- the repo is also meant to teach the workflow system
- you want future contributors to understand why the process exists
- the project itself is a reference implementation

Archive or remove `docs/tutorial/` if:

- the repo is purely for delivery work
- the tutorial would distract contributors from the operating docs
- the tutorial would be redundant in this repo

If you keep the tutorial, treat it as explanatory material, not the day-to-day operating surface.

## Starter Prompt

Use this as the first real handoff prompt for a new coding agent when a PRD or source pack already exists:

```text
New repo. Read the top-level README, then docs/index.md, then docs/system/source-authority.md, docs/system/system.md, and the relevant row in docs/process/change-map.md. After that, read the imported source material under docs/reference/prd-v0/ and help me define the first real arc and active phase before implementation.
```

If no PRD exists yet, start instead with:

```text
New repo. Read the top-level README, then docs/index.md, then docs/reference/product-discovery-process.md, docs/system/source-authority.md, docs/system/system.md, and the relevant row in docs/process/change-map.md. Help me turn the current discussion into a first discovery brief under docs/reference/prd-v0/10-discovery-brief.md before we plan implementation.
```

## What Good Looks Like

After the first real setup pass:

- `README.md` describes the actual project, not just the scaffold
- `docs/index.md` points to the current real arc and active phase
- `docs/system/source-authority.md` identifies the real source of truth
- `docs/reference/prd-v0/` contains the imported product material or the first discovery brief
- `docs/process/change-map.md` reflects the real codebase and validation surface
- the starter arc has been superseded by project-specific planning
