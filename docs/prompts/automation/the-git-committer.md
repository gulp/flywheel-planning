---
icon: lucide/git-commit-horizontal
tags:
  - git
  - commit
  - automation
  - workflow
  - ultrathink
---

# The Git Committer

Intelligently commit all changed files in logical groupings with detailed messages.

## Prompt

```title="Copy and paste into agent session"
Now, based on your knowledge of the project, commit all changed files now in a
series of logically connected groupings with super detailed commit messages for
each and then push. Take your time to do it right. Don't edit the code at all.
Don't commit obviously ephemeral files.
```

## When to Use

- After completing a coding session with multiple changes
- When you have many modified files to commit
- When you want clean, well-organized git history

## Tips

- Best used with a separate agent dedicated to git operations
- Agent will analyze diffs and group related changes
- Great for maintaining clean commit history
