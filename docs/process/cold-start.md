# Cold Start

Use this document only when entering the repo with little or no context.

## Default Read Order

1. `README.md`
2. `docs/index.md`
3. `docs/system/system.md`
4. `docs/system/source-authority.md`
5. `docs/process/arcs/README.md`
6. the current arc and active phase linked from `docs/index.md`

## Task-Specific Follow-On Reading

- If the task is implementation-heavy:
  Read `docs/process/change-map.md`, then the relevant system docs, decisions, and QA docs.

- If the task is UX-heavy:
  Read `docs/reference/ux-process.md` and the relevant design or phase docs.

- If the task is security-, config-, or dependency-heavy:
  Read `docs/reference/security-posture-and-process.md` and the matching change-map row.

- If the task starts from imported source material:
  Read `docs/system/source-authority.md` first, then any derived distillation docs, then raw `docs/reference/prd-v0/*` only if needed.

## What To Confirm Early

- project name and short description
- current arc and active phase
- current source-of-truth and derived-doc setup
- stack or runtime assumptions
- expected validation surface

## Update Rule

Update this file only when the repo's orientation path changes materially. Do not turn it into a second `README.md`.
