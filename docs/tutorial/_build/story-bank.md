# Story Bank

Purpose:
Collect recurring pain stories, drift patterns, and "this is why the framework exists" material before writing polished lessons.

These stories do not need to be literary. They need to preserve the failure mode clearly enough that the lesson feels earned.

## Story format

- Failure pattern:
- What kept going wrong:
- Why the obvious fix was insufficient:
- The insight:
- Which framework it created or strengthened:
- Which repo artifact now embodies it:

## Seed story candidates

### Operating-system insight

- Failure pattern:
  the same kinds of coordination mess kept coming back even after local fixes seemed to work
- What kept going wrong:
  each fix lived in chat, memory, or one contributor's habit instead of becoming part of the repo's normal workflow surface
- Why the obvious fix was insufficient:
  better explanations, better prompting, and better intentions still decay if the missing move is not embedded
- The insight:
  recurring project mess should be turned into named workflow mechanics with triggers, routing, and closeout
- Framework:
  embedded workflow operating system

### Reading-path chaos

- Failure pattern:
  each session starts with rereading too much or too little
- What kept going wrong:
  current state, source of truth, and next step lived in chat memory
- Why the obvious fix was insufficient:
  "just read the repo" is not a real operating path
- The insight:
  reading paths must be selective and task-shaped
- Framework:
  change map, AGENTS routing, cold-start flow

### UX screen soup

- Failure pattern:
  features landed, but the product still felt confusing and got reworked
- What kept going wrong:
  screens were shaped by implementation structure rather than user paths
- Why the obvious fix was insufficient:
  generic UX principles did not force path-to-surface traceability
- The insight:
  outcome -> path -> surface -> data must be modeled explicitly
- Framework:
  experience model, workflow coherence review

### Source-authority collapse

- Failure pattern:
  too many imported docs quietly compete to define the work
- What kept going wrong:
  raw PRDs, chats, and strategy notes were treated as equal authority
- Why the obvious fix was insufficient:
  "just read everything carefully" does not tell the repo which docs actually control implementation
- The insight:
  source material must be classified before implementation starts
- Framework:
  source authority, working distillation

### Active-work amnesia

- Failure pattern:
  everyone kind of knows what is current until the conversation disappears
- What kept going wrong:
  active phase, blockers, and next steps lived mostly in chat memory
- Why the obvious fix was insufficient:
  better summaries still fail if the repo has no explicit state model
- The insight:
  active work needs repo-native lifecycle rules and current-state artifacts
- Framework:
  docs index, lifecycle rules, arc and phase docs, issue routing

### Review evaporation

- Failure pattern:
  reviews found real issues, but those issues did not become durable follow-up
- What kept going wrong:
  findings stayed in prose with no routing rule
- Why the obvious fix was insufficient:
  "we should remember this later" is not an operating mechanic
- The insight:
  findings need explicit routing into issues, decisions, or new phases
- Framework:
  review routing, issue register, lifecycle rules

### Release confusion

- Failure pattern:
  the team kept treating "feature complete" as "ready for external use"
- What kept going wrong:
  installation, infra assumptions, trust boundaries, and operator guidance were not checked as a separate workflow
- Why the obvious fix was insufficient:
  broader testing alone does not make release posture explicit
- The insight:
  release readiness is its own workflow with different questions
- Framework:
  release-readiness checklist, external resources and infrastructure

### Closeout drift

- Failure pattern:
  the work ended, but the repo still described the previous reality
- What kept going wrong:
  status, doc freshness, user guidance, and deferred follow-up were treated as cleanup instead of completion work
- Why the obvious fix was insufficient:
  "we'll tidy it up after this" fails as soon as the next task starts or the chat context moves on
- The insight:
  closeout hygiene has to be embedded in lifecycle rules and templates, not left to personal discipline
- Framework:
  lifecycle closeout minimums, phase and implementation closeout checks, hygiene checkpoints

### External dependency invisibility

- Failure pattern:
  the code looked understandable, but the project still failed at setup, deployment, or handoff time
- What kept going wrong:
  databases, auth providers, APIs, storage, and env assumptions lived in scattered notes or one person's head
- Why the obvious fix was insufficient:
  a few README notes and environment variable names do not explain provisioning, verification, ownership, or fallback
- The insight:
  external dependencies need a human-executable checklist because they are part of the real system boundary
- Framework:
  external resources and infrastructure, release-readiness checks, env-shape documentation

### Flat-surface overload

- Failure pattern:
  the repo had lots of documentation, but contributors still could not find the right working context
- What kept going wrong:
  cold-start guidance, always-on rules, current-state navigation, and deep references were flattened into the same surfaces
- Why the obvious fix was insufficient:
  more headings and more links do not fix a surface that is doing too many jobs
- The insight:
  operational docs need progressive disclosure, with distinct layers for routing, orientation, current state, and deep reference
- Framework:
  AGENTS routing, cold-start split, docs index, change-map-driven task disclosure

### Decision-log drift

- Failure pattern:
  important choices were either forgotten entirely or buried in too many low-signal ADRs
- What kept going wrong:
  the team had no trigger for when a choice deserved a durable decision record
- Why the obvious fix was insufficient:
  "write more ADRs" and "skip ADRs altogether" both fail because they ignore selectivity
- The insight:
  decision records should be created when durable architecture, security, scope, or operational choices are forced
- Framework:
  decision candidates in the decisions README, lifecycle-triggered decision creation, compact decision templates
