# Source Authority

Purpose:
Define which documents set product intent, which documents are derived planning aids, and which materials are archive or provenance only.

Current state:
No project-specific PRD corpus has been imported yet. Use this file immediately after adding source material under `docs/reference/prd-v0/`.

## Recommended authority model

### Primary source of truth

Use these first for product scope, goals, constraints, and tradeoffs:

- the main PRD or product requirements doc
- the scope or non-goals doc
- the canonical process references in `docs/reference/`

### Implementation-boundary docs

Use these to define the first implementation slice:

- a distilled working brief
- a landmine or risk map
- a test matrix
- early architecture or domain-boundary notes

### Background or strategy docs

Useful context, but not equal authority:

- brainstorms
- exports from chats
- market notes
- strategy memos
- exploratory design notes

### Archive or provenance-only docs

Keep these for traceability, not as default implementation inputs:

- raw imports
- copied exports
- screenshots without current planning value
- superseded spec drafts

## Update rule

Once the real source corpus exists:

1. list the exact files in each authority class
2. identify which files a cold-start agent should read first
3. note which derived docs should replace repeated archaeology
4. preserve raw source docs, but do active planning from the distilled set

