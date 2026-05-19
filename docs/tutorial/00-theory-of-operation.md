# Theory Of Operation

This repo treats development process like a lightweight operating system.

The core idea is simple:

- repeated coordination failures should become named workflows
- hidden expectations should become repo-native artifacts
- agent and human work should read from the same operating memory
- process should be embedded in the work surface, not held in chat memory or tribal habit

## The Problem

Most software delivery process is either:

- too implicit to survive context loss, or
- too ceremonial to survive real delivery pressure

That creates a predictable loop:

1. a team rediscovers the same failure mode
2. someone invents a local fix in chat or habit
3. the fix is not captured where future work begins
4. the same drift happens again

This repo is an attempt to break that loop.

## The Core Mechanic

When a failure mode repeats, convert it into one or more of these:

- a routing rule
- a planning artifact
- a review trigger
- a closeout checklist
- a source-of-truth doc

The point is not to document everything. The point is to capture the coordination moves that are too expensive to keep rediscovering.

## Design Principles

- progressive disclosure over giant manuals
- explicit triggers over vague best practices
- path-dependent reading instead of "read the whole repo"
- closeout hygiene so docs stay operational memory, not dead archive
- templates that encode judgment prompts, not bureaucracy

## What Makes It Different

This is not just a docs scaffold.

The repo tries to encode:

- when planning must happen
- when UX needs a stronger workflow model
- when reviews should trigger
- where findings should go
- what must be refreshed before a phase can really be called done

## Proof Standard

The process is only real if it changes behavior.

The question is not "is this a neat framework?"

The question is:

- does it prevent known failure modes?
- does it survive context compression?
- does it help a new contributor or agent recover quickly?
- does it reduce how much process has to be re-explained in chat?
