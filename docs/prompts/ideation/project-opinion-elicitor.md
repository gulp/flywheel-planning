---
icon: lucide/message-circle-question
tags:
  - feedback
  - assessment
  - honesty
  - ultrathink
---

# Project Opinion Elicitor

Get honest, critical assessment of the project from the agent's perspective

## Prompt

```title="Copy and paste into agent session"
Now tell me what you actually THINK of the project-- is it even a good idea?
Is it useful? Is it well designed and architected? Pragmatic? What could we do
to make it more useful and compelling and intuitive/user-friendly to both humans
AND to AI coding agents?
```

## When to Use

- After the agent has explored the codebase
- When seeking honest feedback on direction
- For reality checks on project value

## Tips

- Run this after the agent has read `AGENTS.md`, `README.md`, and explored the code
- The "to both humans AND AI coding agents" framing is key -- it surfaces usability issues from both perspectives
- Agents often have valuable outside perspective
- Encourages intellectual honesty; great for catching blind spots
- Don't take it personally; use it as signal
