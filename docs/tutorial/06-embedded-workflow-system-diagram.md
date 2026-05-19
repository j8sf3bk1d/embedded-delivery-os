# Embedded Workflow System Diagram

Use this page when you want the shortest visual model of the tutorial's core idea.

## Macro Loop

```text
Recurring project mess
        |
        v
Name the failure mode clearly
        |
        v
Design the stabilizing workflow
        |
        v
Embed it in the repo
artifact | rule | template | review | gate
        |
        v
Route people into it at the moment of need
        |
        v
Preserve it through closeout
status | docs | issues | decisions | next steps
        |
        v
Repo-native operating memory
        |
        v
Less repeated chaos, faster recovery, cleaner handoffs
```

## What "Embed It In The Repo" Usually Means Here

```text
                    Embedded workflow operating system
                                   |
        ---------------------------------------------------------
        |                       |                     |          |
        v                       v                     v          v
   Routing surfaces      Planning/state         Review/gates   Closeout
                                              and checks      preservation

   AGENTS.md            docs/index.md          review docs     lifecycle rules
   change map           source authority       gate triggers   docs refresh
   cold-start path      arcs and phases        coherence       issues register
                                                reviews         decision routing
```

## Read This Diagram Left To Right

1. A recurring mess shows up often enough to deserve a name.
2. The fix becomes a workflow, not just a reminder.
3. The workflow gets embodied in a repo surface.
4. The repo routes people into that surface when the task requires it.
5. Closeout keeps the fix alive after the current session ends.

That is the operating-system move the rest of the tutorial keeps instantiating.

## Best Companion Pages

- [09-why-projects-need-an-embedded-workflow-operating-system.md](09-why-projects-need-an-embedded-workflow-operating-system.md)
- [05-best-of-reading-paths.md](05-best-of-reading-paths.md)
- [02-embedded-workflows-overview.md](02-embedded-workflows-overview.md)
