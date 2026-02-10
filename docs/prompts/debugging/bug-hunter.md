---
icon: lucide/bug
tags:
  - debugging
  - bugs
  - review
  - fresh-eyes
  - exploration
---

# Bug Hunter

Explore the codebase with fresh eyes to find and fix bugs.

## Prompt

``` title="Copy and paste into agent session"
I want you to sort of randomly explore the code files in this project, choosing
code files to deeply investigate and understand and trace their functionality and
execution flows through the related code files which they import or which they
are imported by. Once you understand the purpose of the code in the larger
context of the workflows, I want you to do a super careful, methodical, and
critical check with "fresh eyes" to find any obvious bugs, problems, errors,
issues, silly mistakes, etc. and then systematically and meticulously and
intelligently correct them. Be sure to comply with ALL rules in the AGENTS md
file and ensure that any code you write or revise conforms to the best practice
guides referenced in the AGENTS md file.
```

## When to Use

- After writing a lot of new code
- When you suspect there might be bugs lurking
- As a general code quality check
- To keep agents productively busy exploring and improving code

## Tips

- Great for keeping agents busy with useful work between planned tasks
- Follow up with "OK, now fix ALL of them" for execution
- Works well after the agent has explored different parts of the codebase
- The "randomly explore" framing prevents the agent from only checking familiar paths
