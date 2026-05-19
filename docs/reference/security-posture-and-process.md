---

# Security Posture and Process

This document defines the default security posture and operating process for new projects that use this documentation scaffold.

It is intentionally pragmatic. The goal is not to solve security comprehensively inside the repo. The goal is to reduce avoidable trust-boundary mistakes early, especially around dependencies, secrets, agent-assisted development, and local development environments.

---

## 1. Default Project Policy

Unless the repo documents otherwise:

* dependency installs should use a frozen lockfile
* dependency changes should be isolated from unrelated code changes
* new direct dependencies require explicit review
* dependency lifecycle or build scripts should be blocked, gated, or explicitly approved where the package manager supports it
* ordinary dependency updates should observe a release-age cooldown where the package manager supports it
* security updates may bypass the cooldown, but should still be isolated and reviewed
* real secrets should not be available during dependency installation unless strictly necessary

Project rules:

* dependency changes must include the manifest and lockfile diff together
* lockfiles must not be refreshed during unrelated feature, refactor, or formatting work
* new direct dependencies should be justified in change notes, a review note, or a decision record when the reason is not obvious
* security updates may bypass the normal cooldown when tied to a known vulnerability or active security advisory

---

## 2. Security Posture Goal

Optimize for:

* reduced surprise
* smaller blast radius
* explicit trust boundaries
* deliberate review of risky changes
* recoverable local mistakes
* low-friction habits people will actually follow

Do not optimize for theoretical perfection if it creates process nobody will actually follow.

---

## 3. Threat Model Bias

Assume:

* dependencies may be compromised
* install-time scripts are a trust boundary
* local machines often hold valuable credentials
* agent-assisted development increases the chance of casual package execution
* lockfiles improve repeatability, but do not prove safety
* small convenience packages can create disproportionate trust expansion

The default posture should delay novelty, isolate secrets, and force explicit review when trust boundaries change.

---

## 4. Repo-Level Baseline

For application repos, prefer this baseline early:

* keep direct dependencies exact rather than range-based unless there is a clear reason not to
* commit and review the lockfile as part of dependency changes
* prefer package-manager settings that delay brand-new releases by default
* block or explicitly review dependency build scripts
* disable casual automatic script chaining where practical
* document the accepted dependency workflow in repo docs

Examples of acceptable repo-level controls:

* `pnpm` with `minimumReleaseAge`
* frozen-lockfile installs for normal work
* explicit build-script approvals
* dependency-review checks in CI

Treat dependency additions and dependency updates as trust-boundary events, not routine formatting changes.

For published libraries, dependency ranges may be more appropriate than exact pins in order to avoid over-constraining consumers. Document the choice instead of cargo-culting application defaults.

---

## 5. Two-Lane Dependency Policy

Use two different lanes:

### Normal Updates

For ordinary freshness updates:

* wait for a cooldown period before installing the newest release
* review manifest and lockfile together
* prefer isolated or disposable environments for the update
* do not casually absorb large transitive graph changes

### Security Updates

For known vulnerable dependencies:

* move quickly
* still isolate the update
* still review the diff
* document why the normal cooldown was bypassed

The distinction matters. “Update fast” and “never touch anything new” are both bad universal rules.

---

## 6. Agent-Assisted Development Rule

When using an agentic coding tool, dependency installation is not a casual implementation detail.

Rules:

* an agent may propose a dependency, but dependency additions or updates should remain a reviewed decision
* do not let an agent repeatedly install, remove, or swap packages while exploring unless the work is happening in an isolated environment without valuable secrets
* prefer local code, platform capability, or an existing dependency before accepting a new package purely for convenience

This is one of the easiest places for dependency sprawl and accidental trust expansion to enter a project.

---

## 7. Dependency Addition Standard

Before adding a new direct dependency, prefer this order:

1. existing platform or language standard library capability
2. existing project dependency
3. framework-provided utility
4. small local implementation
5. new dependency

A new dependency is easier to justify when it is:

* mature
* widely used
* actively maintained
* difficult to implement correctly
* security-sensitive in a way where established implementations are safer than custom code

A new dependency is harder to justify when it:

* is a small convenience wrapper
* replaces a few lines of local code
* has unusual install behavior
* significantly expands the transitive graph

---

## 8. Dependency Workflow

When adding or updating dependencies:

1. Confirm the dependency is actually needed.
2. Prefer mature, boring, well-understood packages over fashionable ones.
3. Review the direct manifest change and the lockfile change together.
4. Check whether install-time build scripts or unusual sources appear.
5. Run the smallest meaningful validation after the install.
6. Escalate to broader validation if the dependency affects runtime, auth, storage, networking, or build tooling.

Pause and review more deeply if:

* a new direct dependency is introduced
* the transitive graph expands unexpectedly
* install scripts appear
* the package uses git URLs, tarball URLs, or other unusual fetch sources
* the dependency touches auth, secrets, crypto, network fetches, or code execution

---

## 9. Dependency Review Prompts

For dependency changes, answer:

* Why is this dependency needed?
* Is it direct or transitive?
* Does it add or change install or build scripts?
* Does it touch auth, secrets, networking, storage, parsing, or code execution?
* Was the normal release-age cooldown observed?
* If not, why was it bypassed?

Keep these answers in the PR, commit notes, review notes, or a decision record when the change is non-trivial.

---

## 10. Lockfile Discipline

Lockfiles are for reproducibility, not trust.

Use them to ensure:

* repeatable installs
* intentional dependency graph changes
* easy diff review

Do not treat a lockfile as proof that a package was safe when it first entered the tree.

For normal project work:

* prefer frozen-lockfile installs
* do not refresh lockfiles casually during unrelated changes
* keep dependency updates isolated when possible

---

## 11. Build Script Policy

Dependency build scripts deserve explicit suspicion.

Default posture:

* block or gate dependency build scripts unless reviewed
* allow exceptions intentionally for known packages that genuinely need them
* record approvals in repo config where the package manager supports it

Examples of packages that often require special handling:

* native modules
* bundlers with binary downloads
* browser automation tooling
* image or database bindings

If a package requires build-script execution, treat that as a documented exception rather than weakening the global policy.

---

## 12. Environment Isolation

The biggest practical win is often not a scanner. It is keeping valuable secrets out of the environment where dependencies execute.

Preferred order:

* disposable devcontainer or Codespace with minimal mounts
* separate OS user with limited credentials
* local repo with tightly limited ambient credentials

Avoid:

* mounting `~/.ssh`
* mounting cloud provider credential directories
* mounting registry tokens by default
* exposing real `.env.local` secrets during dependency installs when not required

If a devcontainer is used, mount only what the project truly needs.

---

## 13. Machine-Level and External Controls

Some controls belong outside the repo:

* secret isolation
* OS-user separation
* package firewall or MITM tooling
* browser/session isolation
* host-level credential hygiene

Useful external controls may include:

* devcontainers
* separate local users
* Socket Firewall or similar package firewall tooling
* Dependabot or Renovate
* GitHub Dependency Review
* Scorecard or deps.dev as dependency trust signals

Do not pretend repo-local docs replace machine-level hygiene.

---

## 14. Security Review Triggers

Run a focused security review when:

* authentication or authorization changes
* new dependencies are added
* trust-boundary infra changes
* secret handling changes
* external integrations are introduced
* user-uploaded or externally-fetched content paths are added
* privileged operator actions are introduced

Review for:

* auth scope
* secret handling
* input validation
* dependency risk
* data exposure
* auditability
* abuse potential

---

## 15. New Repo Setup Checklist

When starting a new repo, do the minimum useful security setup early:

* choose a package manager with workable supply-chain controls
* create `.env.example` without exposing real values
* document local env-loading quirks and non-default ports
* choose exact versus ranged dependency policy intentionally
* choose lockfile install policy intentionally
* choose build-script review policy intentionally
* document whether security updates bypass normal dependency cooldown
* document what controls are repo-local versus machine-local

This is usually enough to avoid the most common early-project mistakes.

---

## 16. Notes

* Security process should be durable, not theatrical.
* Prefer a small number of enforced habits over a large number of ignored recommendations.
* Keep security posture docs concise and operational.
* Update the process when the stack or package manager changes.

---
