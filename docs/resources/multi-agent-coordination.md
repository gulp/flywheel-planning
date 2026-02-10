---
icon: lucide/users
tags:
  - agents
  - coordination
  - agent-mail
---

# Multi-Agent Coordination

> [@doodlestein](https://x.com/doodlestein/status/2008683457715548549) -- on coordinating multiple agents via Agent Mail and beads.

## Key Insight

Multiple coding agents work simultaneously on different beads, coordinating through **MCP Agent Mail** -- a Gmail-like messaging interface enabling agent-to-agent communication and human oversight.

Agents receive standardized marching orders:

1. Read `AGENTS.md` and `README.md`
2. Investigate codebase architecture
3. Register and coordinate via Agent Mail
4. Pick next actionable beads using `bv --robot-next` / `bv --robot-triage`
5. Implement systematically, marking beads status and communicating progress

## Avoiding Communication Purgatory

The biggest anti-pattern in multi-agent work is **communication purgatory** -- agents endlessly messaging each other without shipping code. The fix:

- Be proactive about starting tasks
- Inform fellow agents when you start work, don't ask for permission
- Mark beads appropriately so others can see what's claimed
- Acknowledge communications promptly but don't block on responses

## Agent Mix

For a typical project, Emanuel deploys:

- 5-6 Claude Code (Opus) agents for primary implementation
- 2-3 Codex agents for parallel implementation
- 1-2 Gemini agents for review duties

## Source

[:simple-x: View on X](https://x.com/doodlestein/status/2008683457715548549){ .md-button }
