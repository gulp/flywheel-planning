---
icon: lucide/terminal
---

# CLI Error Tolerance

Make your CLI forgiving for agents -- honor intent, explain errors clearly.

## Prompt

``` title="Copy and paste into agent session"
One thing that's critical for the robot mode flags in the CLI (the mode intended
for use by AI coding agents like yourself) is that we want to make it easy for
the agents to use the tool; so first off, we want to make the CLI interface and
system as intuitive and easy as possible and explain it super clearly in the CLI
help and in a blurb in AGENTS.md. But beyond that, we want to be maximally
flexible when the intent of a command is clear but there's some minor syntax
issue; basically we'd like to honor all commands where the intent is legible
(although in those cases we might want to precede the response with some note
instructing the agent how to more correctly issue that command in the future).
If we can't really figure out reliably what the agent is trying to do, then we
should always return a super detailed and helpful/useful error message that lets
the agent understand what it did wrong so it can do it the right way next time;
we should give them a couple relevant correct examples in the error message about
how to do what we might reasonably guess they are trying (and failing) to do with
their wrong command.
```

## When to Use

- When building CLI tools that agents will consume
- When improving DX for robot-mode interfaces
- When agents keep failing on syntax edge cases

## Tips

- The key insight: honor intent when clear, educate when ambiguous
- Always include correct examples in error messages
- This applies to any agent-facing interface, not just CLIs
