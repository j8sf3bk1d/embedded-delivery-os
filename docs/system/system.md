# System Orientation

Purpose:
Provide the fastest path for a cold-start developer or coding agent to understand what the system is, how it is organized, and where important boundaries live.

Current state:
This repository is a starter scaffold, not a product implementation. Replace the placeholders below once the real project shape is known.

## Project summary

- Product or system name: not set yet
- Primary user or operator: not set yet
- Primary outcome: not set yet
- Current runtime shape: unknown

## Major components

Use this table once the real system exists. Keep it concise and link to real paths.

| Component | Responsibility | Key paths | Notes |
|---|---|---|---|
| Product surface | Replace with the primary user-facing or operator-facing app | `app/` or `src/` | Add runtime and ownership notes |
| API or backend | Replace with request handling, jobs, or service boundaries | `api/`, `server/`, `backend/`, or `packages/` | Note trust boundaries and integrations |
| Data layer | Replace with schema, ORM, migrations, or storage adapters | `db/`, `prisma/`, `migrations/` | Link to `schema.md` |
| Background work | Replace if jobs, queues, or schedulers exist | `worker/`, `jobs/`, or `scripts/` | Note triggers and failure handling |
| External integrations | Replace with third-party services or internal dependencies | relevant config or adapter paths | Note secret or auth requirements |

## System boundaries

- Source-of-truth product inputs belong in `docs/reference/` and should be triaged through `docs/system/source-authority.md`.
- Active planning belongs in `docs/process/arcs/` and related templates.
- Canonical current-state navigation belongs in `docs/index.md`.
- User-facing instructions belong in `user-docs/`.

## Expected data flow notes

When the real system exists, document:

- where requests or events enter the system
- where state is persisted
- what background processes or external systems are involved
- what surfaces users or operators depend on
- what failure modes are important

## Update rule

Update this file whenever implementation changes the actual architecture, major boundaries, runtime shape, or ownership of state.

