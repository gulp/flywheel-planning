---
icon: lucide/git-branch
tags:
  - beads
  - planning
  - task-management
---

# Beads as an Execution Graph

> [@doodlestein](https://x.com/doodlestein/status/2004650413484658735) -- on treating beads as a dependency graph, not a todo list.

## Key Insight

Beads are not a flat task list. They're a **dependency-tracked execution graph** where:

- **Epics** group related work
- **Tasks** are individual units with clear acceptance criteria
- **Subtasks** break tasks into atomic steps
- **Dependencies** define what must complete before something else can start (blocks/related/parent-child/discovered-from)

Each bead must be **self-contained and self-documenting** -- an agent picking it up should have enough context to work without re-reading the entire plan.

## What Good Beads Include

- Relevant background and reasoning
- Constraints the implementation must respect
- Acceptance criteria (how to know when it's done)
- Dependency links to related beads

## The QA Loop

After converting the plan to beads, run repeated QA passes:

- Are dependencies correct?
- Is any important work missing?
- Are beads too large or too small?
- Are tests comprehensive with detailed logging?
- Are there beads for security, performance, and ops concerns?

Stop when changes are mostly reordering/renaming, not missing work.

## Source

[:simple-x: View on X](https://x.com/doodlestein/status/2004650413484658735){ .md-button }
