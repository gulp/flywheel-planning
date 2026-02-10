---
icon: lucide/file-text
tags:
  - planning
  - methodology
  - cass
---

# Massive Plan Documents

> [@doodlestein](https://x.com/doodlestein/status/1997777154612797787) -- on the scale and rigor of planning documents for complex agent projects.

## Key Insight

For the CASS memory system project, Emanuel produced a **~5,500-line markdown plan document** before writing any code. The planning document was broken into interconnected components and shared on GitHub for transparency.

## The Scale of Multi-Agent Deployment

The project involved deploying simultaneously:

- At least 5-6 Claude Code Opus agents
- At least 3 Codex Max agents
- Gemini agents for review duties

All agents communicated through MCP Agent Mail, allowing coordination across different platforms and preventing conflicts when multiple agents modify shared code.

## Supporting Tools

- **bv** (Beads Viewer) for directional guidance on what to work on next
- **ubs** for error detection beyond standard linting
- **Agent Mail** for inter-agent communication

## The Takeaway

Don't be afraid of long plans. A 5,500-line plan that's been through multiple refinement rounds is not over-engineering -- it's the foundation that lets a dozen agents execute in parallel without stepping on each other.

## Source

[:simple-x: View on X](https://x.com/doodlestein/status/1997777154612797787){ .md-button }
