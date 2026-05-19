# AGENTS.md

Use this file as the always-on operating contract. Keep it lightweight. Do not use it as a repo tour.

## Scope

- Follow the smallest relevant reading path for the task.
- Prefer canonical and derived docs over raw source material.
- Keep updates concise, explicit, and decision-oriented.

## Task Routing

- Code changes:
  Read `docs/process/change-map.md`, then the relevant system docs and active arc or phase docs.

- UX or user-flow changes:
  Read `docs/reference/ux-process.md`, the relevant active phase or design docs, and the current experience model when one exists.

- QA, testing, or validation work:
  Read `docs/qa/test-strategy.md`, `docs/qa/manual-testing.md`, and the relevant row in `docs/process/change-map.md`.

- Security, auth, dependency, env, or config changes:
  Read `docs/reference/security-posture-and-process.md`, relevant decisions, and the matching change-map row before editing.

- External resources, deployment, or release-readiness work:
  Read `docs/system/external-resources-and-infrastructure.md`, `docs/qa/release-readiness-checklist.md`, and the matching change-map row before editing.

- Docs, process, or planning changes:
  Read `docs/index.md`, the active arc or phase docs, and the relevant templates under `docs/process/templates/`.

- PRD intake or source reconciliation:
  Read `docs/system/source-authority.md` first. Prefer derived distillations over raw files in `docs/reference/prd-v0/`.

## High-Risk Rules

- Surface document conflicts explicitly instead of silently choosing one.
- Treat dependency changes, auth changes, secret handling, and external-service configuration as trust-boundary work.
- Do not widen scope from background or archive docs without saying so.

## Documentation Rules

- Update docs when implementation, architecture, validation, or process reality changes.
- Do not duplicate canonical guidance from `docs/reference/*`; link to it.
- Keep `docs/index.md` aligned with the current arc, active phase, and key reading paths.
- Route durable deferred risks into `docs/scratchpad/issues.md` instead of leaving them only in chat or review notes.

## Validation Rule

- Run the smallest meaningful validation for the touched area first.
- Escalate to broader validation when blast radius, shared state, or trust boundaries increase.
- If validation was not run, say so clearly.

## Response Template

- What changed: high-level summary
- What works: completed behavior or validated result
- Assumptions: only if relevant
- Tests: run, not run, or deferred, only if relevant
- Decisions needed: include a recommendation when relevant
- Next steps: suggested next action or explicit stop point

## Cold Start

Cold-start orientation lives outside this file.

- Human/project entrypoint: `README.md`
- Explicit cold-start playbook: `docs/process/cold-start.md`
