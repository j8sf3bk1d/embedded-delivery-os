# Why External Resources Need A Human-Executable Checklist

Many projects look simpler than they really are because the code is visible and the dependencies around it are not.

That creates a recurring trap:

- the app starts on one machine
- a demo works
- everyone assumes the setup is mostly understood

Then the real project hits a wall because critical dependencies were never made explicit.

This lesson explains why external resources need a human-executable checklist, and why infrastructure assumptions cannot stay buried in chat, environment files, or one person's memory.

## How It Was Learned Or Earned

The recurring mess looks like this:

- a project depends on a database, auth provider, email service, object storage, or third-party API
- setup works for the person who already wired it together
- the next person tries to run, deploy, or extend the system and finds missing assumptions everywhere

The hidden problems usually include:

- nobody knows which account or vendor actually owns the dependency
- environment variables exist, but their expected shape is unclear
- provisioning steps were never written down
- no one knows the smallest real connectivity check
- fallback or recovery expectations are unstated

The obvious fix sounds familiar:

- add the missing keys to `.env`
- drop a few setup notes into the README
- explain it when someone gets stuck

Those can patch the moment, but they do not create durable operational clarity.

The insight is that external dependencies are part of the system boundary. If they matter to runtime, they need a first-class, human-executable home.

## The Strategy

The strategy is to treat external resources as explicit operating surfaces rather than background assumptions.

That means documenting, for each meaningful dependency:

- what it is for
- who or what provides it
- what must be provisioned
- what configuration shape it expects
- how to verify the wiring with the smallest meaningful check
- how it connects back to the rest of the system

This is not about writing infra theory.

It is about making the dependency real enough that another person can reason about it, set it up, verify it, and notice drift.

## The Tactics

This repo embeds that idea directly.

### 1. External resources have a dedicated system document

[docs/system/external-resources-and-infrastructure.md](../system/external-resources-and-infrastructure.md) exists so dependencies do not get scattered across ad hoc notes.

It gives each resource a consistent shape:

- purpose
- service or vendor
- provisioning status
- environment variables
- local assumptions
- verification
- connected system paths
- recovery or fallback notes

That turns "some setup stuff" into a real operating artifact.

### 2. Provisioning is treated as executable knowledge

The same doc requires a provisioning checklist that captures:

- what must be created
- which account or service is involved
- what config steps are required
- how to verify connectivity

This matters because a dependency is not really documented if the only proof is that it once worked for the original builder.

### 3. Release readiness depends on external-resource clarity

[docs/qa/release-readiness-checklist.md](../qa/release-readiness-checklist.md) explicitly checks:

- installation or startup path
- environment variable expectations
- operational readiness
- external resources and infrastructure expectations

That helps prevent the common mistake where feature confidence gets mistaken for deployment or operator confidence.

### 4. Drift triggers make the checklist maintainable

The external-resources doc also names the moments when it must be updated:

- a new service is introduced
- env var names or shapes change
- runtime topology changes
- verification commands change

That is important because the problem is not only writing the checklist once. The problem is keeping it true as the system evolves.

## The Proof Or Belief Builders

You know this framework is working when someone other than the original builder can understand the dependency surface without needing a private walkthrough.

### What it prevents

- hidden setup assumptions
- environment variable cargo culting
- unclear ownership of external services
- deployment surprises caused by missing provisioning steps
- runtime failures that could have been caught by a small connectivity check

### What it improves

- onboarding for new contributors
- credibility of setup and deployment docs
- operational readiness for real environments
- visibility into the true system boundary

### What artifacts prove it is embedded

- [docs/system/external-resources-and-infrastructure.md](../system/external-resources-and-infrastructure.md)
- [docs/qa/release-readiness-checklist.md](../qa/release-readiness-checklist.md)
- [.env.example](../../.env.example)
- [docs/process/change-map.md](../process/change-map.md)

If those artifacts stay current, the repo can explain what the system depends on in a way another human can actually execute.

## Why This Matters To Different Readers

### Managers

This makes operational dependency risk visible before it turns into deadline surprise.

### Developers

This stops infra setup from living as tribal knowledge glued together by environment variables and memory.

### Non-Developers

This explains why a project can look complete on the surface while still being impossible to set up or run reliably.
