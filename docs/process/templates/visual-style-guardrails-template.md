# Visual Style Guardrails Template

Use this when a project has meaningful UI work and you want a compact, durable record of:

- the visual direction to aim for
- the negative patterns to avoid
- the density or compactness target
- how screenshot review should evaluate drift over time

Create one when any of these are true:

- the product has a repeated task workflow where speed matters
- multiple UI phases are likely to land over time
- AI-assisted UI generation or builder defaults may create sameness
- screenshots exist and visual drift is becoming hard to judge from code alone
- the team keeps saying "make it feel better" without a stable design direction

Keep this document short, practical, and product-specific.

## Scope

- Arc or initiative:
- Related experience model or phase docs:
- Primary device contexts:
- Review date:

## Why this exists

State why the project needs explicit visual guardrails.

Useful prompts:

- What kind of product is this: operator tool, consumer utility, editorial product, internal dashboard, commerce flow, field workflow?
- What real usage context should shape the UI: standing, walking, desk work, collaborative review, quick check-ins, dense administration?
- What goes wrong if styling defaults are left implicit?

## Product-specific direction

Describe the intended feel in terms of task support, not fashion.

Examples:

- compact over roomy
- scan-first over decorative
- calm over theatrical
- dense enough to reduce scrolling
- explicit and trustworthy over clever

## Negative patterns to avoid

List the patterns that would make this product feel generic, slower, less trustworthy, or less usable.

Suggested table:

| Pattern to avoid | Why it is a bad fit here | Better default |
|---|---|---|
| example: centered marketing-hero composition | slows repeat-use task flow | lead with task context and the next useful action |
| example: oversized padding on every card | burns mobile viewport height | tighten within groups and separate between groups |
| example: decorative gradients or glows | adds mood without meaning | reserve color for state, emphasis, or grouping |

## Compactness and density rules

State how the project should think about density.

Useful prompts:

- Should this UI bias toward compact rows or larger cards?
- What must fit above the fold on mobile or laptop?
- Where is roominess helpful, and where does it slow the workflow down?
- What spacing is useful structure versus empty theater?

## Visual system choices

Capture only the choices that matter:

- typography direction
- color role and restraint
- surface treatment
- radius and shadow bias
- motion rules
- iconography rules

Do not turn this into a full design system unless the project actually needs one.

## Screenshot and review expectations

Define what visual review should look for:

- baseline screenshots to preserve
- screens or states that must be compared over time
- density, contrast, hierarchy, and drift checks
- specific mobile and desktop viewports when relevant

Useful tooling prompts:

- Is this a static prototype where a tiny local server plus Playwright captures would be enough?
- Is this an existing web app where Playwright should just reuse the normal dev server?
- Does this UI depend on mutable local data, meaning the capture command should use isolated local state or fixtures?
- Should this project keep milestone archive captures, screenshot regression baselines, or both?
- Is there a fast project-local capture command worth documenting, such as `screenshots:capture` or `test:visual`?

## Review checklist

- Does the screen show the task before decorative framing?
- Is the primary path visually obvious?
- Can the user scan enough state without unnecessary scrolling?
- Does each badge, surface, shadow, or chip communicate something useful?
- Is suggestion or automation UI subordinate to the core workflow when it should be?
- Are copy and contrast specific enough for real use conditions?
- Do transitions improve orientation rather than slow fast actions down?
- If the screen looks like a generic builder output, what product truth is missing?

## Open questions

- unresolved visual tradeoffs
- unresolved density decisions
- unresolved accessibility or trust concerns

## Agent adaptation note

Future project agent:

- treat this file as a starting pattern, not a canonical design answer
- replace generic examples with product-specific guidance before relying on it
- keep only the rules that materially improve the real workflow
- link the final project-specific guardrail doc from the experience model, active phase, or docs index when it becomes part of the working surface
- review current screenshots before and after using this pattern, then fold the result into the normal docs-update and commit process for that project
- if screenshot tooling does not exist yet, suggest the lightest useful harness shape instead of leaving visual review purely subjective

If you keep the reference list below, trim it to what still explains the project's chosen direction.

## Starter references

These sources motivated the template and are useful when a future project wants a fresh anti-slop or density pass:

- Adrian Krebs, [Scoring Show HN submissions for AI design patterns](https://www.adriankrebs.ch/blog/design-slop/)
- Developers Digest, [AI Design Slop: 15 Patterns That Out Your App as Vibe-Coded](https://www.developersdigest.tech/blog/ai-design-slop-and-how-to-spot-it)
- 925Studios, [AI Slop Web Design: Complete Guide to Spotting and Fixing Generic Websites](https://www.925studios.co/blog/ai-slop-web-design-guide)
- Shuffle, [Why Do Most AI-Generated Websites Look the Same?](https://shuffle.dev/blog/2026/01/why-do-most-ai-generated-websites-look-the-same/)
- Matt Strom-Awn, [UI Density](https://mattstromawn.com/writing/ui-density/)
- Denali Design, [Density & Spacing](https://denali.design/design/principles/density-and-spacing)
- Veronika Krauss et al., [Create a Fear of Missing Out - ChatGPT Implements Unsolicited Deceptive Designs in Generated Websites Without Warning](https://eprints.gla.ac.uk/348039/)
- Ziwei Chen et al., [Deception at Scale: Deceptive Designs in 1K LLM-Generated Ecommerce Components](https://researchtrend.ai/papers/2502.13499)
