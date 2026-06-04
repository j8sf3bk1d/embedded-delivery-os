# 00 Project Foundation

## Goal

Set up the repo so a cold-start developer or coding agent can orient quickly, triage source materials cleanly, and begin project-specific planning without rebuilding the process baseline.

## Background

This starter repo begins before a PRD or stack-specific implementation is known. The arc therefore focuses on orientation, source-authority setup, and first-slice planning rather than feature work.

## Outcomes

- top-level orientation is clear
- source-of-truth docs are explicit
- change, QA, and review expectations are documented
- the first real project-specific planning slice has an obvious home

## Phases

| Phase | Purpose | Status |
|---|---|---|
| [00 Cold-Start Scaffold](phases/00-cold-start-scaffold/phase.md) | Establish the reusable repo baseline | complete |
| [01 Source Intake, Discovery, and Distillation](phases/01-source-intake-and-distillation/phase.md) | Import and triage the real source corpus or create the first discovery brief | active |
| [02 First Real Arc Planning](phases/02-first-real-arc-planning/phase.md) | Turn the source corpus into the first implementation-ready arc | pending |

## Risks

- source docs may be imported without a clear authority model
- live discovery may happen without being converted into durable source docs
- placeholder test and setup guidance may stay stale after the stack is known
- process docs may diverge from real implementation if not updated early

## Completion criteria

- the real project name and description replace starter placeholders
- imported source materials are triaged through `docs/system/source-authority.md` or a first discovery brief exists when no PRD was provided
- the first real project arc is defined with active phase context
- stack-specific env and validation commands replace generic placeholders

## Related docs

- [docs/index.md](../../../index.md)
- [docs/system/system.md](../../../system/system.md)
- [docs/system/source-authority.md](../../../system/source-authority.md)
- [docs/process/change-map.md](../../change-map.md)
