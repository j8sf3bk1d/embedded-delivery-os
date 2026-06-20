# Test Strategy

## Current state

This starter repo does not contain implementation code yet, so there are no stack-specific automated commands to run. Use this document as the place to add the real validation surface once the runtime shape exists.

## Default testing policy

When implementation begins, prefer the smallest meaningful validation that can prove the change is safe:

- unit tests for pure logic and data transformations
- integration tests for boundaries between modules, services, and storage
- end-to-end or workflow tests for critical user or operator paths
- smoke tests for runtime startup, core routing, and basic health

## Broader validation triggers

Run broader regression when:

- completing a phase
- changing shared infrastructure or startup behavior
- changing data models or migrations
- changing authentication, authorization, or trust boundaries
- changing user-critical workflows
- changing external service integrations
- preparing for release, external use, or deployment

## Focused validation guidance before the stack exists

Until concrete commands exist:

- verify links, statuses, and current-state notes in docs
- review `.env.example` against the intended runtime shape
- review manifest and lockfile changes together
- use `git status --short` to confirm the changed file set matches the intended scope
- when planning demo, screenshot, fixture, or visual-QA tooling, decide explicitly whether it touches real local state or isolated temporary state

For UI-heavy projects, choose the screenshot harness shape intentionally once the runtime becomes real:

- static prototype or wireframe repo: tiny local server plus Playwright page captures
- single web app with a normal dev server: Playwright `webServer` using the regular startup command
- stateful app: dedicated visual capture command that seeds or points at isolated local state

If the UI is likely to keep changing, plan for both:

- milestone archive captures under `docs/archive/screenshots/`
- optional Playwright screenshot assertions only for stable, high-value surfaces

## Initial command slots to replace later

Replace these placeholders once the real stack is known:

- install: `<package-manager install command>`
- lint: `<lint command>`
- typecheck: `<typecheck command>`
- unit tests: `<unit test command>`
- integration tests: `<integration test command>`
- build: `<build command>`
- app smoke: `<local startup or health-check command>`
- visual capture: `<project-local screenshot or visual-QA command>`
- visual regression: `<Playwright or equivalent screenshot-baseline command>`

## Common screenshot harness examples

These are starter shapes, not canonical requirements. Choose the lightest one that matches the project.

### Example A - Static prototype or wireframe pages

Good fit:

- plain HTML/CSS/JS prototypes
- builder handoff mockups
- editorial or marketing wireframes without app state

Typical shape:

```txt
prototype files
-> tiny local HTTP server
-> Playwright visits a few important pages
-> full-page screenshots saved under docs/archive/screenshots/
```

Example command slots:

- app smoke: `python3 -m http.server 4321 --directory workflows/site/prototype`
- visual capture: `playwright test tests/visual/prototype-pages.spec.ts`

### Example B - Single web app with a normal dev server

Good fit:

- Vite apps
- Next-style browser shells
- small internal tools with a normal local startup command

Typical shape:

```txt
Playwright webServer
-> starts the normal dev server on a fixed localhost port
-> visits stable workflow states
-> keeps screenshot assertions only for high-value surfaces
```

Example shape:

```ts
webServer: {
  command: "npm run dev -- --host 127.0.0.1 --port 4173",
  url: "http://127.0.0.1:4173",
  reuseExistingServer: true
}
```

Example command slots:

- app smoke: `npm run dev -- --host 127.0.0.1 --port 4173`
- visual regression: `playwright test`

### Example C - Stateful app with isolated local data

Good fit:

- apps with local databases
- workflows that seed fixtures or mutate state
- operator tools where screenshots should never touch the human's normal working data

Typical shape:

```txt
project-local capture command
-> clear or create isolated state
-> start the app with env pointing at that isolated state
-> run one or more Playwright capture specs
-> write milestone captures to docs/archive/screenshots/
```

Example command slots:

- visual capture: `pnpm screenshots:capture`
- visual regression: `playwright test tests/visual/<surface>.spec.ts`

Document clearly:

- where the isolated state lives
- whether it is safe to delete on each run
- which command is archival capture versus screenshot-baseline regression

## Local-state safety rule

When a project later adds commands for demos, screenshots, sample data, fixtures, or visual QA:

- do not point those commands at the operator's normal local database or local runtime by default
- use a temporary database, temporary ports, or isolated fixtures unless the command is intentionally destructive
- document clearly which commands are safe for real local data and which commands mutate or clear it

Local-only tools can still be trust-boundary concerns when they mutate state that a human assumes is durable.

## Dependency hygiene checks

When dependencies change:

- review manifest and lockfile changes together rather than in isolation
- prefer exact direct dependency versions unless there is a documented reason not to
- treat new direct dependencies and install-time scripts as trust-boundary events
- document unresolved advisories or accepted risks in a review or decision record

## Release-readiness rule

Before calling a slice release-ready, launch-ready, or suitable for external use:

- use `docs/qa/release-readiness-checklist.md`
- ensure external-resource assumptions are explicit in `docs/system/external-resources-and-infrastructure.md`
- run the appropriate review gate depth for the trust boundaries involved

Update this document as soon as stack-specific validation commands and riskier system boundaries become real.
