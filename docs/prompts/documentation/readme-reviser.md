---
icon: lucide/file-edit
tags:
  - documentation
  - readme
  - docs
  - ultrathink
---

# README Reviser

Update docs to reflect current state, not changelog style.

## Prompt

```title="Copy and paste into agent session"
Update the README and other documentation to reflect all of the recent changes
to the project.

Frame all updates as if they were always present (i.e., don't say "we added X"
or "X is now Y" -- just describe the current state).

Make sure to add any new commands, options, or features that have been added.
```

## When to Use

- After completing a feature or significant code change
- When documentation is out of sync with code
- Before releasing a new version
- When onboarding new contributors

## Tips

- "Frame as if always present" is the key instruction -- no changelog language
- Run after every significant feature completion
- Check for removed features that need to be undocumented
- Ensure examples still work with current code
- Pair with [Project Opinion Elicitor](../ideation/project-opinion-elicitor.md) for a holistic review
