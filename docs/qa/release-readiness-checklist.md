# Release-Readiness Checklist

Use this before calling the current slice release-ready, launch-ready, or suitable for external use.

If a section does not apply yet, say so explicitly instead of silently skipping it.

## Scope Anchor

- the release candidate still fits the intended scope and non-goals
- deferred work is written down explicitly
- known gaps are recorded as release gaps, not hidden assumptions

## Packaging Boundary

- the intended release artifact or deployment boundary is explicit
- only operator- or runtime-relevant files are included
- docs, scripts, local-only assets, secrets, and dev artifacts are excluded unless intentionally part of the release
- the supported runtime topology is named clearly

## Installation Or Startup Path

- the installation, bootstrap, or startup path works on a clean target
- required configuration steps are documented clearly
- environment variable expectations are explicit
- the narrowest realistic smoke check succeeds

## Core Functional Validation

- the highest-value critical workflows are validated
- status language remains accurate and not overstated
- important failure and recovery paths are either validated or explicitly deferred

## Data, Privacy, And Trust Boundaries

- sensitive data handling still matches the intended posture
- secrets are not exposed through logs, diagnostics, screenshots, or example files
- auth, authorization, and privileged actions have the required review depth
- external fetch or integration surfaces remain bounded and intentional

## Operator And User-Facing Accuracy

- operator docs and user docs reflect the released behavior
- labels do not claim more certainty than the system actually has
- setup, status, and troubleshooting guidance are still accurate

## Operational Readiness

- deployment or runtime profile docs are current
- backup, restore, rollback, or recovery notes exist if relevant
- external resources and infrastructure expectations are explicit
- monitoring, logging, or diagnosis paths are good enough for the intended audience

## Validation Breadth

- focused validation ran for the touched areas
- broader validation ran where blast radius justified it
- any important paths not exercised are listed explicitly

## Release Decision

- Recommendation:
- Ship now / ship with caveats / do not ship yet
- Blocking issues:
- Non-blocking follow-ups:

