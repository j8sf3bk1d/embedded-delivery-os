---

# Engineering Principles

This document captures core engineering principles that guide system design, implementation, and evolution in this project.

These are not rigid rules, but default biases to apply unless there is a clear reason not to.

---

## 1. Optimize for System-Level Outcomes

Avoid optimizing features in isolation if it degrades overall system behavior.

* consider how changes affect data flow, performance, and architecture
* periodically reassess decisions at phase and arc boundaries
* prioritize the health of the system over local convenience

---

## 2. Prefer Deletion Over Addition

When modifying the system:

* look for opportunities to remove or simplify existing code
* avoid layering new logic on top of unclear or redundant behavior
* reduce complexity instead of accumulating it

Every addition increases long-term maintenance cost.

---

## 3. Make Assumptions Explicit

When working with incomplete information:

* clearly state assumptions being made
* proceed conservatively
* update assumptions as more information becomes available

Hidden assumptions lead to misaligned implementations.

---

## 4. Define Clear Ownership of State and Responsibility

For any piece of state or logic:

* define where it lives
* define which component is responsible for it
* avoid duplicating or synchronizing the same state across layers

Unclear ownership leads to inconsistency, redundant work, and bugs.

---

## 5. Prioritize Interfaces and Boundaries

Systems should be understandable through how components interact.

* define clean interfaces between components
* avoid leaking internal details across boundaries
* minimize tight coupling between layers

Clear boundaries make systems easier to extend and reason about.

---

## 6. Be Aware of Data Flow and Hot Paths

For any feature interacting with data or external systems:

* understand what data is accessed and how often
* identify high-frequency or latency-sensitive paths
* avoid redundant fetching, excessive round trips, or unnecessary recomputation

Optimize for efficient and predictable data movement.

---

## 7. Minimize System Surface Area

Be intentional about what the system exposes:

* avoid unnecessary APIs, endpoints, or cross-component dependencies
* limit data exposure to what is required
* reduce the number of places where behavior can change

Smaller surface area improves security, stability, and maintainability.

---

## 8. Design for Observability

The system should make its behavior visible and diagnosable.

* ensure meaningful logging, metrics, and tracing where appropriate
* make it possible to understand failures and performance issues
* avoid “silent” failures or hidden system behavior

If a system cannot be observed, it cannot be reliably maintained.

---

## 9. Align with Cold-Start Understandability

The system should be understandable by someone with no prior context.

* documentation should enable quick orientation
* structure should reflect intent
* relationships between components should be clear

If a new developer or agent cannot understand the system quickly, improve clarity.

---

## 10. Reconcile Design and Implementation Continuously

If implementation begins to diverge from design:

* pause and update the design
* or adjust the implementation intentionally

Do not allow design documents and code to drift apart.

---

## Notes

* These principles guide decision-making across all phases of work
* When deviating from a principle, do so intentionally and document the reasoning
* Favor consistency in applying these principles across the system

---
