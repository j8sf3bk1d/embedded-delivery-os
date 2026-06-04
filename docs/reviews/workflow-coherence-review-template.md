# Workflow Coherence Review Template

Use this when multiple user-facing phases have landed and the repo needs a broader check that screens still form a usable path instead of an implementation-shaped pile of features.

## Review metadata

- Date:
- Reviewer:
- Scope:
- Related arc:
- Trigger:

Suggested triggers:

- after two or more related UX phases land
- before closing a user-facing arc
- when the product feels feature-rich but path-poor
- when screen responsibilities or navigation boundaries feel blurred

## Findings

List concrete findings first. Include file or surface references, the workflow risk, and the expected impact.

If there are no findings, say so explicitly.

## Outcome And Path Check

Check whether:

- primary user outcomes are still explicit
- the main paths to those outcomes are intact
- alternate and recovery paths are understandable
- the workflow still matches the intended actor goals

## Surface Ownership Check

Check whether:

- each important screen has a clear primary goal
- screens are not trying to own too many unrelated jobs
- navigation aligns with user progress rather than internal system structure
- drill-in and return paths still make sense

## Data Contract Check

Check whether:

- each screen has the data needed to answer the user’s real question
- primary data is not buried behind secondary telemetry
- derived data and trust signals are presented at the right point in the path
- empty, loading, and recovery states are still coherent

## Progressive Disclosure Check

Check whether:

- the product shows meaning before machinery
- action comes before telemetry where appropriate
- deeper diagnostics or low-level detail are still secondary

## Visual And Interaction Drift Check

Check whether:

- current screenshots still support the intended primary path when baseline captures exist
- layout density, hierarchy, contrast, and emphasis still support comprehension
- responsive or state-based drift has introduced new friction
- visual changes improved the flow rather than merely restyling it

## Follow-Ups

- Action:
- Owner:
- Due:

## Recommendation

- continue the current arc
- open a workflow refactor phase
- run a design review gate
- update the experience model before more implementation
