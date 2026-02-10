---
icon: lucide/iteration-cw
tags:
  - planning
  - refinement
  - ultrathink
---

# Plan Refinement Loop

> [@doodlestein](https://x.com/doodlestein/status/2007588870662107197) -- the original tweet describing the iterative plan refinement process.

## Key Insight

If you have a markdown plan for a new piece of software that you're getting ready to start implementing with a coding agent such as Claude Code, before starting the actual implementation work, paste your entire markdown plan into ChatGPT 5.2 Pro with extended reasoning enabled and use this prompt:

```title="Plan critique prompt"
Carefully review this entire plan for me and come up with your best revisions
in terms of better architecture, new features, reliability, security,
performance, usability, etc. For each proposed change, give a detailed analysis
and rationale/justification, and provide git-diff style changes relative to the
original markdown plan.
```

Then take the complete output and paste it into Claude Code (or Codex) to revise the plan file in-place with the feedback.

Repeat this process with fresh ChatGPT conversations after each coding agent revision. After **four or five rounds**, the suggestions reach a steady-state where they become very incremental.

Once refinement is complete, turn the plan into **beads** (epics/tasks/subtasks with dependency structure).

## Why It Works

- Extended reasoning in a web app is cheap relative to code generation tokens
- Diff-based output forces concrete, integratable changes instead of vague advice
- Each round catches things the previous round missed
- Convergence after 4-5 rounds is a reliable signal that the plan is solid

## Source

[:simple-x: View on X](https://x.com/doodlestein/status/2007588870662107197){ .md-button }
