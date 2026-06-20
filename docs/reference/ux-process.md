---

# UX Process - Outcome-Driven Design

This document defines the standard process for designing and evaluating user experiences in this project.

The goal is to produce interfaces that help users achieve outcomes with minimal friction, maximum clarity, and appropriate levels of control and visibility.

If no PRD or working brief exists yet, use this alongside `docs/reference/product-discovery-process.md` so the user outcome and gap map are established before interface design begins.

---

## 1. Start with the User Goal

All UX work begins with a clearly defined outcome.

* What is the user trying to accomplish?
* What does success look like from their perspective?
* How will the user know they've succeeded?

Avoid starting from existing UI or system structure. Start from the desired outcome.

---

## 2. Work Backward from Completion

Design the experience by working backward from the goal to the entry point.

Define:

* **Completion state** - what the system looks like when the goal is achieved
* **Entry state** - how the user arrives at this flow
* **Intermediate steps** - the actions required to move from entry to completion

Represent this as a simple flow:

```txt
Entry -> Step 1 -> Step 2 -> Completion
```

Do not assume the current flow is correct. Reconstruct it from first principles.

---

## 3. Evaluate Each Step

For every step in the flow, explicitly analyze:

### Requirements

* What must the user provide, decide, or understand?

### Friction

* Where might the user hesitate, get confused, or make errors?

### Clarity

* Is it obvious what to do next and why?

### Necessity

* Is this step required, or can it be removed, combined, or automated?

### Reassurance and trust

* What proof, confirmation, visibility, or control does the user need at this step?
* Is the real blocker missing confidence rather than missing functionality?

---

## 4. Reduce and Simplify the Flow

Actively minimize effort and cognitive load:

* remove unnecessary steps
* combine related actions
* reduce decision points where possible
* avoid redundant confirmations

If something must happen and the system already has the required data and control:

* perform it automatically
* while maintaining user awareness and the ability to intervene

---

## 5. Preserve User Agency and Observability

Automation should not create opacity or loss of control.

Ensure:

* the user can understand what the system is doing
* important actions are visible and traceable
* the user can override or adjust decisions when appropriate

Avoid silent system behavior that reduces trust.

---

## 6. Let the Constraints Narrow the Pattern

By the time the following are explicit:

* the desired outcome
* the action the user must take
* the information they need
* the reassurance or control they need

the viable interaction patterns should narrow significantly.

Ask:

* does this step need comparison, review, confirmation, drill-in, or simple progression?
* does the user need one obvious next action or several equally valid tools?
* does this pattern reduce friction or merely reflect the implementation structure?

Use this narrowing effect intentionally. It keeps the search space small and the resulting UI more usable.

---

## 7. Design the Interface from the Flow

The UI should be derived from the flow, not the other way around.

For each step:

* define the primary action
* provide only the necessary supporting information
* de-emphasize or defer secondary actions

Use appropriate patterns based on:

* task complexity
* frequency of use
* risk of error

Do not choose patterns based on stylistic preference alone.

---

## 8. Validate Information Completeness

Ensure the system provides everything needed to complete the task:

* Is any required information missing?
* Is anything ambiguous or implicit that should be explicit?
* Can additional data be surfaced to improve decision-making?

If required information is not available:

* identify the gap
* define how it could be captured, inferred, or instrumented

Many UX problems are actually missing-data problems.

---

## 9. Handle Edge Cases and Failure States

Design beyond the happy path.

Account for:

* incomplete or invalid inputs
* system errors
* empty states
* long-running or asynchronous operations

Ensure:

* errors are clear and actionable
* recovery paths are obvious
* system status and progress are visible when delays occur

---

## 10. Maintain Consistency Across the System

Before finalizing:

* does this align with existing patterns and flows?
* are we introducing unnecessary new concepts or interactions?
* will this fragment the user's mental model?

Prefer consistency unless there is a clear and meaningful improvement.

---

## 11. Primary Path Focus

Identify the single most important user path.

* optimize this path aggressively
* ensure it is fast, clear, and low-friction
* avoid over-complicating it to accommodate edge cases

Secondary paths should not degrade the primary experience.

---

## 12. Use Screenshot-Assisted Review When UI Exists

Code often hides the details that matter most in UI work: density, visual hierarchy, spacing, contrast, emphasis, and drift across states.

If screenshot tooling or test scaffolding exists:

* capture meaningful milestone states
* compare before-and-after screenshots when workflows or layouts change
* check desktop and mobile views when relevant
* preserve only the captures that materially help future review or drift detection
* when repeated UI work is expected, create a small visual style guardrails note that records desired density, negative patterns to avoid, and product-specific styling constraints

If screenshot tooling does not exist yet, prefer the lightest useful harness rather than skipping visual review indefinitely.

Common defaults:

* static prototype or wireframe pages: a tiny local HTTP server plus Playwright page captures is usually enough
* single web app with an existing dev server: point Playwright `webServer` at the normal local startup command and capture milestone states or regression baselines from there
* stateful app with mutable local data: add a dedicated screenshot or visual-QA command that uses isolated local state rather than the operator's normal runtime data

Separate two kinds of visual evidence:

* milestone archive captures under `docs/archive/screenshots/` for before-and-after review and project history
* screenshot assertions or baselines in Playwright only when the UI is stable enough that mechanical pixel comparison will save time rather than create churn

Use screenshot evidence to review:

* action clarity
* information density
* visual hierarchy
* contrast and legibility
* empty, loading, and error states
* responsive drift over time

---

## 13. UX Review Checklist

Before completing UX design work, confirm:

* the user goal is clearly defined
* the flow from entry to completion is explicit
* unnecessary steps have been removed or simplified
* actions and next steps are clear at every stage
* system behavior is visible and understandable
* edge cases and failure states are handled
* required information is present and unambiguous
* the design aligns with existing system patterns
* the chosen interaction pattern fits the outcome and information constraints
* available screenshot evidence has been reviewed or intentionally skipped

---

## 14. Notes

* Prioritize outcomes over features
* Favor clarity over cleverness
* Reduce cognitive load wherever possible
* Design for real usage, not ideal conditions
* When in doubt, simplify

---
