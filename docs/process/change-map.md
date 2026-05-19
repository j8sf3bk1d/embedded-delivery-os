# Change Map

Read this before making changes. Match the area you expect to touch, read the listed docs first, and run the smallest validation that can provide useful signal.

Current note:
This is a stack-neutral starter repo. Several rows below intentionally point to placeholder validation until the real implementation and commands exist. Tighten the rows as soon as concrete code paths and test commands exist.

| Touched area | Read first | Focused validation | Broader validation triggers |
|---|---|---|---|
| `README.md`, `docs/index.md`, `docs/process/**`, `docs/reviews/**`, `docs/scratchpad/**` | `docs/index.md`, `docs/process/arcs/README.md`, active arc and phase docs, `docs/reference/engineering-principles.md` | Verify links, statuses, and next steps are current | Re-review the full project map when arc ownership, repo shape, or startup instructions change |
| user-facing or operator-facing flow docs, experience models, IA docs, workflow reviews | `docs/reference/ux-process.md`, the relevant experience model, active arc and phase docs, `docs/reviews/workflow-coherence-review-template.md` | Verify outcome-to-path-to-surface traceability and that the main workflow still reads clearly | Escalate when multiple screens, role differences, or progressive-disclosure rules are being reshaped together |
| `docs/system/**` | `docs/system/system.md`, `docs/system/schema.md`, `docs/system/source-authority.md`, relevant decisions | Confirm boundaries, ownership, and current-state notes still match reality | Re-review all system docs when architecture, runtime shape, or state ownership changes |
| `docs/system/external-resources-and-infrastructure.md`, deployment notes, env bootstrap, infra runbooks | `docs/system/external-resources-and-infrastructure.md`, `docs/index.md`, `docs/reference/security-posture-and-process.md`, relevant decisions | Verify provisioning steps, env names, connectivity checks, and local assumptions against reality | Escalate when a new external service, deployment profile, secret flow, or trust boundary is introduced |
| `docs/reference/**` | `docs/system/source-authority.md`, then the specific source doc or reference doc | Preserve source-versus-derived roles and keep canonical references unmodified unless intentionally updating process guidance | Run a broader docs pass when the product source of truth or active implementation slice changes materially |
| `.env.example`, runtime config, package manifests, lockfiles, infra config | `docs/index.md`, `docs/qa/test-strategy.md`, `docs/reference/security-posture-and-process.md`, relevant decisions | Check variable names, placeholder shapes, dependency changes, and config notes for accuracy | Run broader validation when runtime stack, trust boundaries, or external services change |
| `src/**`, `app/**`, `backend/**`, `packages/**`, `worker/**`, `scripts/**` | `docs/system/system.md`, `docs/system/schema.md`, active arc and phase docs, `docs/qa/test-strategy.md` | Run the smallest meaningful stack-specific lint, typecheck, unit test, or smoke command for the touched area | Escalate to broader integration, workflow, or end-to-end checks when shared state, auth, data models, or user-critical flows change |
| `tests/**` | active arc and phase docs, `docs/qa/test-strategy.md`, relevant system docs | Run the focused test slice and confirm it still reflects current behavior | Run broader regression when tests change shared harnesses, fixtures, or release confidence |
| `user-docs/**` | `user-docs/user-manual.md`, active arc and phase docs, manual-testing notes | Confirm the instructions still match the current product behavior | Re-run manual QA for the affected user flow when user-visible behavior changes |
| `docs/qa/release-readiness-checklist.md`, deployment profiles, packaging or launch-readiness docs | `docs/qa/release-readiness-checklist.md`, `docs/system/external-resources-and-infrastructure.md`, active arc and phase docs, `docs/reviews/review-template.md` | Verify the intended release boundary, supported runtime shape, and narrowest realistic install or startup path | Escalate before external use, deployment, launch, or when release claims become broader |
| `docs/reviews/**`, hygiene or sweep checkpoints | `docs/reviews/review-template.md`, `docs/reviews/hygiene-checkpoint-template.md`, `docs/process/phase-and-arc-lifecycle.md`, `docs/scratchpad/issues.md` | Check findings, follow-ups, and status references for consistency | Run a broader docs and system sweep when multiple phases landed or process drift is suspected |

## Default workflow

1. Identify the area you expect to touch.
2. Read the matching row and linked docs first.
3. Run the smallest meaningful validation.
4. Escalate to broader validation when blast radius is high or the change closes a phase.
