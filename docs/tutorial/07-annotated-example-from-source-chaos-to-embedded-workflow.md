# Annotated Example: From Source-Document Chaos To Embedded Workflow

This walkthrough shows one concrete example of the macro framework in action.

The goal is not to explain every possible process mechanic. The goal is to show how one recurring mess gets converted into a stable repo workflow.

This example uses source-document chaos because it shows the full operating-system move clearly:

- recurring mess
- named framework
- embedded artifacts
- routing at the point of need
- preservation through closeout

## The Starting Mess

Imagine a project starts with:

- a PRD
- a copied chat export
- a strategy memo
- a brainstorm doc
- a few screenshots

Everyone agrees all of it is "relevant."

Then the team starts work.

Very quickly, the project gets hit by familiar confusion:

- one person treats the PRD as primary
- another treats the latest brainstorm as the real direction
- another remembers a chat clarification and implements from that
- someone else reads all of it and still cannot tell what actually controls scope

This is not a knowledge problem first.

It is a workflow problem.

## Step 1: Name The Failure Mode

The recurring mess gets a name:

- source-document chaos
- or, in the lesson language, missing source authority

That naming move matters because it stops the team from treating every future recurrence as a one-off misunderstanding.

Once the failure mode is named, the project can ask a better question:

- what workflow would prevent this from recurring?

## Step 2: Design The Stabilizing Workflow

The stabilizing workflow here is simple:

1. preserve raw source material without treating it all as equal authority
2. classify the source set into authority levels
3. produce a working distillation for the implementation slice
4. route future contributors through the distilled set first

That is the strategy layer.

Notice what changed:

- the fix is no longer "read more carefully"
- the fix is now a sequence the repo can support

## Step 3: Embed The Workflow In Repo Artifacts

In this repo, the workflow becomes several concrete surfaces.

### Raw intake has a home

The imported materials live under:

- [docs/reference/prd-v0/README.md](../reference/prd-v0/README.md)

That keeps the source corpus preserved without making it the default working surface forever.

### Authority mapping becomes explicit

The project classifies the sources in:

- [docs/system/source-authority.md](../system/source-authority.md)

That is where the repo says:

- what is primary
- what is derived
- what is background
- what is archive-only

### Distillation becomes expected

The repo provides templates for:

- [docs/process/templates/source-authority-template.md](../process/templates/source-authority-template.md)
- [docs/process/templates/distillation-template.md](../process/templates/distillation-template.md)

That means the workflow is no longer an oral tradition. The repo expects an authority map and a working brief.

## Step 4: Route People Into The Workflow

Now the important question is:

- how does the repo make people use this instead of ignoring it?

That is where routing surfaces come in.

### Always-on routing

[AGENTS.md](../AGENTS.md) says PRD intake and source reconciliation should read source authority first.

That prevents the workflow from being "technically documented but operationally optional."

### Task-shaped routing

[docs/process/change-map.md](../process/change-map.md) reinforces the distinction between reference material and active implementation inputs.

That means the workflow activates at the moment of need, not only during a one-time setup session.

## Step 5: Change The Working Behavior

Once the workflow is embedded and routed, work begins differently.

Before:

- every contributor rereads the raw corpus
- scope drifts because context and authority are mixed together
- the latest remembered note can quietly override the real product intent

After:

- contributors start from the authority map
- the working distillation defines the implementation slice
- raw documents remain available without silently steering the work

This is the key transition:

- the project stops depending on memory
- the repo starts carrying the coordination burden

## Step 6: Preserve It Through Closeout

The workflow is not truly embedded until it survives interruption.

That means when the source set changes, the project has to refresh:

- the authority map
- the working distillation
- the current-state docs that point to them

This is where the broader operating system matters.

The source-authority mechanic survives because it is surrounded by:

- routing in `AGENTS.md`
- current-state visibility in `docs/index.md`
- closeout expectations in lifecycle and phase docs

Without those preservation moves, even a good source-authority doc would decay back into one forgotten artifact.

## What This Example Proves

This one walkthrough shows the full macro loop:

1. recurring mess:
   too many docs compete for authority
2. named failure mode:
   source-document chaos
3. stabilizing workflow:
   classify, distill, route
4. embedded artifacts:
   intake area, source-authority doc, distillation template
5. routing:
   `AGENTS.md` and change-map guidance
6. preservation:
   current-state and closeout discipline

That is the same operating-system move the rest of the tutorial keeps repeating in other domains.

## Best Companion Pages

- [06-embedded-workflow-system-diagram.md](06-embedded-workflow-system-diagram.md)
- [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)
- [12-why-source-authority-must-exist-before-implementation.md](12-why-source-authority-must-exist-before-implementation.md)
