# Lessons Map

This file maps candidate tutorial lessons to the repo artifacts they explain.

## Candidate Lessons

### 00. Projects Need An Embedded Workflow Operating System

- pain:
  the same coordination failures keep recurring because the fixes stay trapped in chat, memory, or habit
- artifact anchors:
  `AGENTS.md`, `docs/index.md`, `docs/process/change-map.md`, `docs/system/source-authority.md`, `docs/process/phase-and-arc-lifecycle.md`
- published lesson:
  [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)

### 01. Reading Paths Instead Of Repo Tours

- pain:
  people read too much, too little, or the wrong things
- artifact anchors:
  `AGENTS.md`, `docs/process/change-map.md`, `docs/process/cold-start.md`
- published lesson:
  [10-why-reading-paths-beat-repo-tours.md](10-why-reading-paths-beat-repo-tours.md)

### 02. Source Authority Before Implementation

- pain:
  dense source corpora become contradictory and implementation starts from the wrong document
- artifact anchors:
  `docs/system/source-authority.md`, source-authority and distillation templates
- published lesson:
  [12-why-source-authority-must-exist-before-implementation.md](12-why-source-authority-must-exist-before-implementation.md)

### 03. Arc And Phase State As Operational Memory

- pain:
  "what is actually active?" lives only in chat or in someone's head
- artifact anchors:
  `docs/index.md`, `docs/process/arcs/`, `docs/process/phase-and-arc-lifecycle.md`
- published lesson:
  [13-why-active-work-cannot-live-only-in-chat-memory.md](13-why-active-work-cannot-live-only-in-chat-memory.md)

### 04. Reviews Need Routing, Not Just Findings

- pain:
  issues found in review evaporate instead of becoming decisions, issues, or new phases
- artifact anchors:
  review templates, hygiene checkpoint, `docs/scratchpad/issues.md`
- published lesson:
  [14-why-reviews-need-routing-not-just-findings.md](14-why-reviews-need-routing-not-just-findings.md)

### 05. UX Needs Outcome-Path-Screen Traceability

- pain:
  screens accrete features before the user workflow is modeled, then get reworked later
- artifact anchors:
  `docs/process/templates/experience-model-template.md`, workflow coherence review
- published lesson:
  [11-why-ux-keeps-regressing-into-screen-soup.md](11-why-ux-keeps-regressing-into-screen-soup.md)

### 06. Release Readiness Is A Different Workflow Than Feature Completion

- pain:
  "it works locally" gets confused with "it is fit for external use"
- artifact anchors:
  `docs/qa/release-readiness-checklist.md`, `docs/system/external-resources-and-infrastructure.md`
- published lesson:
  [15-why-works-locally-is-not-a-release-process.md](15-why-works-locally-is-not-a-release-process.md)

### 07. Closeout Hygiene Preserves Continuity

- pain:
  work looks done, but the repo no longer matches reality and the next phase starts from drift
- artifact anchors:
  `docs/process/phase-and-arc-lifecycle.md`, phase and implementation templates, hygiene checkpoint
- published lesson:
  [16-why-closeout-hygiene-matters.md](16-why-closeout-hygiene-matters.md)

### 08. External Resources Need A Human-Executable Checklist

- pain:
  runtime dependencies stay implicit until setup, deployment, or handoff fails
- artifact anchors:
  `docs/system/external-resources-and-infrastructure.md`, `docs/qa/release-readiness-checklist.md`, `.env.example`
- published lesson:
  [17-why-external-resources-need-a-human-executable-checklist.md](17-why-external-resources-need-a-human-executable-checklist.md)

### 09. Progressive Disclosure Beats Flat Operational Surfaces

- pain:
  the repo has plenty of information, but the surfaces are overloaded and people still cannot tell what to read
- artifact anchors:
  `AGENTS.md`, `README.md`, `docs/process/cold-start.md`, `docs/index.md`, `docs/process/change-map.md`
- published lesson:
  [18-why-progressive-disclosure-beats-flat-operational-surfaces.md](18-why-progressive-disclosure-beats-flat-operational-surfaces.md)

### 10. Decision Records Should Be Triggered, Not Overused

- pain:
  consequential choices either disappear into memory or get buried in a noisy ADR graveyard
- artifact anchors:
  `docs/system/decisions/README.md`, `docs/process/phase-and-arc-lifecycle.md`, `docs/process/templates/decision-template.md`
- published lesson:
  [19-why-decision-records-should-be-triggered-not-overused.md](19-why-decision-records-should-be-triggered-not-overused.md)

## Authoring Note

The lesson list should stay selective.

Only create a lesson when:

- the pain is real and recurring
- the strategy is distinguishable
- the repo has a concrete artifact that embodies it
