---
icon: lucide/eye
tags:
  - review
  - quality
  - cross-agent
  - ultrathink
---

# Peer Code Reviewer

Review code written by other agents across the project.

## Prompt

```title="Copy and paste into agent session"
Ok can you now turn your attention to reviewing the code written by your fellow
agents and checking for any issues, bugs, errors, problems, inefficiencies,
security problems, reliability issues, etc. and carefully diagnose their
underlying root causes using first-principle analysis and then fix or revise them
if necessary? Don't restrict yourself to the latest commits, cast a wider net
and go super deep!
```

## When to Use

- After a multi-agent implementation session
- When you want cross-pollination of code review across agent work
- During Phase 6 fresh-eyes review loops

## Tips

- "Don't restrict yourself to the latest commits" is key -- it forces a broad review
- "First-principle analysis" pushes the agent past surface-level observations
- Run this with a different model than the one that wrote the code for true "fresh eyes"
