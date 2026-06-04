# Embedded Delivery OS

Short description: repo-native workflow operating system and reusable project scaffold for software delivery.

Current arc: [00 Project Foundation](process/arcs/00-project-foundation/arc.md)

Active phase: [Phase 01 - Source Intake, Discovery, and Distillation](process/arcs/00-project-foundation/phases/01-source-intake-and-distillation/phase.md)

Current status: Git is initialized. The starter documentation, process, QA, review, scratchpad, and user-doc scaffolding are in place. Canonical process references live in `docs/reference/`. The scaffold now supports both imported PRDs and conversation-driven first-brief creation, plus screenshot-assisted UX review when visual tooling exists. No product-specific PRD or implementation stack has been committed yet, so the system map, source-authority doc, environment scaffold, and validation guidance remain intentionally generic.

Key docs:

- System: [System Orientation](system/system.md), [Schema](system/schema.md), [Source Authority](system/source-authority.md), [Decisions](system/decisions/README.md)
- System ops: [External Resources And Infrastructure](system/external-resources-and-infrastructure.md)
- Process: [Change Map](process/change-map.md), [Arc Index](process/arcs/README.md), [Phase And Arc Lifecycle](process/phase-and-arc-lifecycle.md), [First Real Use](process/first-real-use.md), [Templates](process/templates/README.md)
- Cold start: [Cold-Start Playbook](process/cold-start.md)
- Tutorial: [Tutorial Track](tutorial/README.md)
- Current arc: [00 Project Foundation](process/arcs/00-project-foundation/arc.md)
- Active phase: [Phase 01 - Source Intake, Discovery, and Distillation](process/arcs/00-project-foundation/phases/01-source-intake-and-distillation/phase.md)
- QA: [Test Strategy](qa/test-strategy.md), [Manual Testing](qa/manual-testing.md), [Release-Readiness Checklist](qa/release-readiness-checklist.md)
- Reviews: [Review Template](reviews/review-template.md), [Hygiene Checkpoint Template](reviews/hygiene-checkpoint-template.md), [Workflow Coherence Review Template](reviews/workflow-coherence-review-template.md)
- Scratchpad: [Ideas](scratchpad/ideas.md), [Issues](scratchpad/issues.md)
- User docs: [User Manual](../user-docs/user-manual.md)
- Intake area: [PRD v0 README](reference/prd-v0/README.md)
- Canonical references: [Product Discovery Process](reference/product-discovery-process.md), [UX Process](reference/ux-process.md), [Feature Design Process](reference/feature-design-process.md), [Engineering Principles](reference/engineering-principles.md), [Security Posture and Process](reference/security-posture-and-process.md)
- Visual archive: [Screenshot Archive](archive/screenshots/index.md)

Setup and environment notes:

- `.gitignore` is conservative because the implementation stack is not known yet.
- `.env.example` is a placeholder scaffold only; replace or trim keys once the runtime shape is known.
- `docs/reference/prd-v0/` is the default intake location for raw product docs, copied chats, exported specs, and other source material, and it is also the default home for a first discovery brief when no PRD exists yet.
- Update `docs/system/source-authority.md` before treating imported source docs as implementation-authoritative.
- Replace placeholder validation guidance in `docs/qa/test-strategy.md` and `docs/process/change-map.md` as soon as real commands exist.
- Use `docs/system/external-resources-and-infrastructure.md` as soon as the project depends on real external services, accounts, or provisioning.
- If UI work exists and screenshot tooling is available, keep meaningful milestone captures under `docs/archive/screenshots/`.

Immediate next steps:

1. Add the real PRD or create `docs/reference/prd-v0/10-discovery-brief.md` with the Product Discovery Process.
2. Update [docs/system/source-authority.md](system/source-authority.md) to identify primary, secondary, and archive-only sources.
3. Distill the active implementation slice before planning code changes if the source pack or discovery output is dense.
4. Replace the starter arc and phase stubs with project-specific planning once the product direction is known.
5. Decide whether to keep, archive, or remove the tutorial track for the live project repo.
6. Tighten lifecycle, release, and infrastructure docs once the real runtime topology exists.
