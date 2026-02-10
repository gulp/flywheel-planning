---
icon: lucide/skull
tags:
  - planning
  - risk
  - premortem
  - ultrathink
---

# Premortem Planner

Imagine failure 6 months out and revise the plan to prevent it

## Prompt

```title="Copy and paste into agent session"
Before we proceed, I want you to do a "premortem" on this plan. Imagine we're
6 months in the future and this approach has completely failed. What went wrong?
What assumptions did we make that turned out to be false? What edge cases did we
miss? What integration issues did we overlook? What would users hate about it?
Now, with that pessimistic scenario fresh in your mind, revise the plan to
address the most likely failure modes.
```

## When to Use

- Before committing to a major implementation
- When planning risky or complex features
- To challenge assumptions before they become problems
- After drafting a plan but before converting to beads

## Tips

- Forces consideration of failure modes upfront
- Catches integration issues before they're expensive to fix
- Especially valuable for user-facing features
- The pessimistic framing unlocks failure modes that optimistic planning misses
- Pair with Phase 2 plan refinement for maximum coverage
