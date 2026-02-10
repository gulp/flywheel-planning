---
icon: lucide/replace
---

# Stub Eliminator

Hunt down every placeholder and replace it with real, working code.

## Prompt

``` title="Copy and paste into agent session"
I need you to look for stubs, placeholders, mocks, of ANY KIND. These ALL must
be replaced with FULLY FLESHED OUT, working, correct, performant, idiomatic code
as per the beads. Do this meticulously and carefully!
```

## When to Use

- After initial scaffolding is in place
- When you suspect agents left `TODO` or placeholder implementations
- Before final review passes

## Tips

- Run this after the main implementation phase
- Agents often leave stubs during initial passes -- this prompt catches them all
- Follow up with [Bug Hunter](../debugging/bug-hunter.md) to verify the replacements work correctly
