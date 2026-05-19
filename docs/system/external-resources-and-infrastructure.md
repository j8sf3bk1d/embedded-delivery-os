# External Resources And Infrastructure

Purpose:
Keep provisioning, external-service setup, runtime dependencies, and connectivity assumptions explicit and human-executable.

Current state:
No project-specific external resources are defined yet. Replace the placeholders below once the real stack is known.

## Usage rule

- Do not assume an external resource is ready unless it has been provisioned and verified.
- Keep secret values out of this file. Document names, expected shapes, where they come from, and how to verify wiring instead.

## Resource inventory

Use one section per external dependency category.

### Example: Database

- Purpose:
- Service or vendor:
- Required account or owner:
- Provisioning status:
- Environment variables:
- Local assumptions:
- Verification:
- Connected system paths:
- Recovery or fallback notes:

### Example: Object storage

- Purpose:
- Service or vendor:
- Required account or owner:
- Provisioning status:
- Environment variables:
- Local assumptions:
- Verification:
- Connected system paths:
- Recovery or fallback notes:

### Example: Email, auth, queue, third-party APIs, observability

Repeat the same shape for each meaningful dependency.

## Provisioning checklist

For each resource, capture:

- what must be created
- which account, service, or plan is required
- what configuration steps are needed
- which environment variables or secret names are involved
- how to verify connectivity using the smallest meaningful check
- how the resource connects back to the project

## Local runtime notes

Document concrete local assumptions when known:

- non-default ports or URLs
- local service wrappers
- version constraints such as a database major version
- whether tooling expects `.env.local`, `.env`, or an explicit loader

## Drift triggers

Update this file when:

- a new external service is introduced
- environment variable names or shapes change
- supported deployment or runtime topology changes
- verification commands or connectivity assumptions change

