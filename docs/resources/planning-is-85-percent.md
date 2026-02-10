---
icon: lucide/clock
tags:
  - planning
  - methodology
  - ultrathink
---

# Planning is 85% of the Work

> [@doodlestein](https://x.com/doodlestein/status/2008813776687030781) -- on spending the vast majority of effort on planning, not implementation.

## Key Insight

Emanuel describes spending **85%+ of time and energy on the planning phases.** His methodology for a typical project:

1. **Initial plan creation** using Claude Code with Opus, studying relevant existing code first
2. **Iterative refinement** using ChatGPT Pro with extended reasoning to review the plan and suggest improvements
3. **Multiple review rounds** integrating feedback back into the plan through 3-4 additional cycles

A real example: approximately 3 hours of planning produced a ~3,500-line markdown document.

## Converting Plans to Beads

Once the plan reaches maturity, convert it into beads -- granular task structures with dependencies. Use the prompt:

> "Create a comprehensive and granular set of beads for all this with tasks, subtasks, and dependency structure overlaid, with detailed comments."

The beads then undergo **8-9 refinement rounds**, focusing on optimality, feature completeness, and comprehensive test coverage.

## Why This Ratio

- Planning tokens are cheap; code generation tokens are expensive
- Debugging tokens from bad plans are the most expensive of all
- A well-refined plan lets multiple agents execute in parallel without conflicts
- The plan has already been stress-tested through multiple critique rounds

## Source

[:simple-x: View on X](https://x.com/doodlestein/status/2008813776687030781){ .md-button }
