# Product Discovery Process

Use this when a project starts from a live conversation, a pain point, a vague idea, or a loose source pack rather than a clear PRD.

The goal is to turn fuzzy intent into a durable first brief that defines the real outcome, the starting state, the gap between them, and the smallest believable first slice.

Use this alongside:

- `docs/reference/ux-process.md` for user-facing flow design
- `docs/reference/feature-design-process.md` for domain and business-logic shaping
- `docs/system/source-authority.md` for classifying what becomes authoritative

## 1. Start from tension, pain, or imported leverage

Discovery often starts from one of these signals:

- a complaint about a frustrating workflow
- an observed operational bottleneck
- a pattern that likely transfers from another domain
- a tool or service that solves only one painful step in a larger gap

Do not mistake the complaint for the full requirement. Treat it as an entry signal.

## 2. Find the real desired outcome

Ask what the person actually wants to be true when the problem is solved.

Look for:

- the dream outcome they would gladly buy or adopt
- the confidence or trust bar they need before they believe the problem is solved
- what "better" means in practice: faster, clearer, safer, less effortful, more reliable, more visible

If the stated pain point is too narrow, zoom out until the broader desired outcome becomes explicit.

## 3. Define the current state and the gap

Once the desired outcome is clear, define:

- where the actor starts
- what they already know or have
- what blockers, uncertainty, or manual work slow them down
- what meaningful finish line they care about

Represent the gap as a simple sequence:

```txt
Current state -> obstacle or decision -> step -> step -> completion state
```

This gap map is the backbone for both product discovery and later UX work.

## 4. Decompose each step in the gap

For each step, ask:

- what action or decision is required
- what information is required
- what proof, reassurance, or trust signal is required
- what can be automated
- what should remain user-controlled
- what can be collapsed, reordered, or removed

The objective is not to preserve the current workflow. It is to redesign the path to the outcome.

## 5. Use a value lens, not just a feature lens

One useful framing is Alex Hormozi's value equation:

```txt
Value = (Dream Outcome x Perceived Likelihood of Achievement)
        / (Time Delay x Effort & Sacrifice)
```

Use it as a discovery lens:

- increase the size or clarity of the desired outcome
- increase the user's confidence that the outcome will happen
- reduce the time between starting and seeing progress
- reduce the effort, friction, and sacrifice required

This helps prevent feature ideation from drifting into low-value complexity.

Optional external reference:

- Acquisition.com pricing and value checklist:
  `https://www.acquisition.com/hubfs/Offer%20Checklists%20-%20PDF%20Downloads/Pricing-Value-Checklist.pdf?hsLang=`

## 6. Loot broadly for patterns and anti-patterns

Do not limit research to direct competitors in the same domain.

Look at:

- direct competitors solving the same overall problem
- adjacent tools solving only one step especially well
- cross-domain products with comparable trust, speed, review, or handoff problems
- negative examples that create confusion, hidden work, or distrust

Capture both:

- positive patterns worth importing
- anti-patterns worth avoiding

Cross-domain pattern transfer often reveals better moves than same-domain mimicry.

## 7. Convert the discussion into durable source material

Discovery is incomplete until the conversation becomes a durable artifact.

When no formal PRD exists yet:

1. create `docs/reference/prd-v0/10-discovery-brief.md`
2. use `docs/process/templates/discovery-brief-template.md`
3. update `docs/system/source-authority.md` so the brief is classified explicitly
4. keep raw brainstorms, transcripts, or copied notes as background or archive material unless they are intentionally primary

The first brief becomes the seed source-of-truth until a fuller PRD replaces or refines it.

## 8. Exit with a narrow first slice

Before planning implementation, make sure discovery names:

- the primary actor
- the primary desired outcome
- the current state
- the gap map
- the most important trust or evidence requirements
- the smallest meaningful first slice
- explicit non-goals
- open questions that still need research

If these are not clear, continue discovery before moving into implementation planning.

## 9. Hand off into UX and implementation planning

Once the first brief exists:

- use `docs/reference/ux-process.md` to shape the user-facing path
- use `docs/reference/feature-design-process.md` to shape system logic and rules
- create an experience model when multiple surfaces or handoffs matter
- update the active arc and phase so future contributors read the distilled brief first
