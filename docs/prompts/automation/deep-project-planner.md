---
icon: lucide/scan-search
---

# Deep Project Planner

Bootstrap an agent's understanding of the entire project before tasking it.

## Prompt

``` title="Copy and paste into agent session"
First read ALL of the AGENTS.md file and README.md file super carefully and
understand ALL of both! Then use your code investigation agent mode to fully
understand the code, and technical architecture and purpose of the project.
```

## When to Use

- At the start of every new agent session
- Before giving any implementation or review tasks
- After context compaction when agent may have lost project understanding

## Tips

- This is a prerequisite prompt -- run it before any other task prompt
- The agent will explore the codebase on its own and build a mental model
- Follow up with a specific task prompt once exploration is complete
