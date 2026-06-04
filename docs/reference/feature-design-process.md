---

# Feature and Business Logic Design Process

This document defines the standard process for shaping features, domain behavior, and business logic in this project.

The goal is to design systems that turn inputs into correct, explainable, operable outcomes with clear ownership, explicit tradeoffs, and testable rules.

Use this alongside `/docs/reference/ux-process.md`. UX process governs user-facing flow design. This document governs domain logic, scoring, state, interpretation, and feature behavior behind the interface.

If no PRD or working brief exists yet, use `docs/reference/product-discovery-process.md` first so the desired outcome and first slice are explicit before logic design begins.

---

## 1. Start with the Business Outcome

All feature and logic design begins with the outcome the system must produce.

Define:

* who needs the output
* what decision or action the output enables
* what a successful outcome looks like
* what evidence would make the output trustworthy

Do not start with tables, APIs, or implementation structure. Start with the condition the system must reliably detect or the action it must support.

---

## 2. Work Backward from the Final Decision

Model the flow by working backward from the final business decision or system action.

Define:

* **completion state** - what the system has produced when the job is done
* **entry state** - what inputs or preconditions exist at the start
* **transformations** - what steps convert entry into completion

Represent this as a logic chain:

```txt
Input -> Observation -> Normalization -> Interpretation -> Decision -> Action
```

If there are multiple distinct stages, keep them separate. Do not collapse acquisition, reasoning, and action into one opaque step.

---

## 3. Separate Facts from Interpretation

Explicitly distinguish between:

* raw observations
* normalized evidence
* interpreted signals
* actions, alerts, or downstream decisions

This boundary is mandatory when the system works with ambiguous or externally sourced information.

Ask:

* What is an objective fact?
* What is an inference?
* What confidence belongs to the inference?
* What should remain explainable to a human reviewer?

Avoid allowing one subsystem to silently convert weak evidence into strong conclusions.

---

## 4. Define Ownership of State and Logic

For every important piece of state or behavior, define:

* where it lives
* who writes it
* who reads it
* what makes it valid
* how it changes over time

At minimum, identify:

* source-of-truth records
* derived records
* cached or denormalized views
* user-controlled overrides
* time-sensitive or decaying state

If ownership is fuzzy, redesign the boundary before implementation.

---

## 5. Make Scoring, Rules, and Thresholds Explicit

If the system ranks, scores, suppresses, or prioritizes, define the rules directly.

Document:

* what inputs affect the score
* whether each input affects fit, timing, confidence, cost, urgency, or another dimension
* what thresholds exist
* what can suppress or negate a result
* which rules are deterministic and which are heuristic

Prefer inspectable configuration or rule tables over hidden constants spread across the codebase.

---

## 6. Design for Explainability

A feature is incomplete if a user, operator, or developer cannot answer:

* Why did the system produce this result?
* What evidence contributed to it?
* What was suppressed or ignored?
* What changed since the last result?

Design outputs so they can be explained from structured reasons, not only from freeform summaries.

If the system uses an LLM, keep core state transitions, thresholds, dedupe, and suppression explainable without relying on the model's unstated reasoning.

---

## 7. Define Failure and Degradation Behavior

Business logic should specify what happens when inputs are incomplete, contradictory, stale, duplicated, or blocked.

For each meaningful subsystem, define:

* empty-state behavior
* partial-data behavior
* stale-data behavior
* conflict-resolution behavior
* retry or recovery behavior
* health states where relevant

Differentiate clearly between:

* no evidence
* low-confidence evidence
* unsupported source
* temporary failure
* permanent mismatch

---

## 8. Prefer Deterministic Core Logic with Assisted Interpretation

When combining structured rules with probabilistic tooling:

* use deterministic logic for storage, identity, dedupe, thresholds, decay, and suppression
* use assisted interpretation for extraction, normalization, ambiguity handling, and human-readable summaries

This keeps the system tunable and testable while still benefiting from flexible interpretation where needed.

---

## 9. Model Time, Decay, and Reuse

Feature behavior is often time-sensitive. Define:

* what gets stronger over time
* what decays over time
* what remains durable background context
* when a result becomes stale
* when the same condition should trigger a new alert versus being treated as already known

Treat persistent fit context differently from short-lived urgency or timing context.

---

## 10. Build the Evaluation Harness Early

Do not validate only with happy-path examples.

Create fixtures for:

* true positives
* false positives
* ambiguous inputs
* stale inputs
* duplicate inputs
* contradictory inputs
* high-value but low-confidence cases

Before implementation is considered stable, confirm the system can explain and defend its behavior across these cases.

---

## 11. Review Questions

Before finalizing feature or business-logic design, confirm:

* the business outcome is explicit
* acquisition, normalization, interpretation, and action are separated cleanly
* state ownership is clear
* deterministic and heuristic responsibilities are separated
* thresholds and suppressions are documented
* timing and decay rules are explicit
* explainability is built into the model
* edge cases and degraded states are handled
* the smallest meaningful first slice is identified

---

## 12. Notes

* Favor conservative claims over impressive but weak inference
* Favor auditable rules over hidden magic
* Prefer small, composable pipelines over monolithic feature logic
* Treat human trust as a product requirement
* If the system cannot explain its output, its design is incomplete

---
