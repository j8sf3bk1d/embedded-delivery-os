# Dispatch Allocation Policy

Create `coordination/dispatch-policy.md` when worker/model allocation matters.
It defines project defaults without changing readiness, dependencies, or the
portable task-board header.

## Status and scope

- Status: `provisional | active | retired`
- Scope:
- Last reviewed:
- Human owner:

## Hard constraints

- **Fast mode: prohibited unless the human user explicitly authorizes it.**
- Other non-negotiable constraints:

## Default allocation

| Work shape | Suggested worker/model | Reasoning effort | Why |
|---|---|---|---|
| Straightforward bounded execution | Luna or equivalent | high | |
| Moderate implementation or rework | Luna or equivalent | high | |
| Design, ambiguity, architecture, coordination, or review | Terra or equivalent | medium | |
| Exceptional graph-changing or high-risk integration review | Sol or equivalent, if available | high | |

Projects may omit Sol or use capability-oriented labels.

## Override rules

- Record task-level deviations and rationale in the brief or handoff.
- No deviation enables Fast mode without explicit human-user authorization.
- Use the smallest adequate allocation; importance alone is not a reason to raise effort.

## Review trigger

Revisit after meaningful rework, repeated review findings, changed worker
capability, cost/latency friction, or recurring exceptions.
