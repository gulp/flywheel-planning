---
icon: lucide/shield-alert
tags:
  - analysis
  - improvement
  - review
  - brainstorming
  - ultrathink
---

# System Weaknesses Analyzer

Identify the weakest parts of the system that need fresh ideas and improvements.

## Prompt

```title="Copy and paste into agent session"
Based on everything you've seen, what are the weakest/worst parts of the system?
What is most needing of fresh ideas and innovative/creative/clever improvements?
```

## When to Use

- After the agent has explored the codebase thoroughly
- When you want to identify areas for improvement
- As a starting point for refactoring discussions
- When prioritizing where to invest improvement effort

## Tips

- Best used after the agent has done substantial work in the session
- Run after [Deep Project Planner](../automation/deep-project-planner.md) so the agent has full context
- Follow up with prompts to actually implement the improvements
- Combine with a TODO list prompt for tracking execution
- Pair with [Idea Wizard](idea-wizard.md) to generate solutions for the weaknesses found
