---
icon: lucide/users
---

# Phase 5: Implement with Agent Swarm

!!! info "Goal"
    Deploy coordinated agents to execute beads systematically.

This is where the planning pays off. With a well-QA'd bead graph, multiple agents can work in parallel without conflicts.

## Prompt: Swarm Marching Orders

Give this to each agent you spin up.

``` title="Marching orders (give to every agent)"
First read ALL of `AGENTS.md` and `README.md` super carefully and understand
ALL of both.

Then:

- investigate the codebase to understand architecture and invariants
- use beads as the source of truth for what to do next
- use `bv --robot-next` / `bv --robot-triage` to select impactful actionable beads
- claim work by marking beads in_progress and keep them updated as you go
- avoid communication purgatory; start shipping work
- respond to any coordination messages promptly (if using an agent mailbox)

Proceed meticulously on the next assigned beads. Use ultrathink where available.
```

## Prompt: Reread AGENTS (Context Recovery)

When an agent's context gets compacted or you suspect drift, re-anchor it.

``` title="Re-anchor prompt"
Reread `AGENTS.md` so it's still fresh in your mind. Use ultrathink.
```

## Agent Coordination Tips

!!! tip "Multi-agent best practices"
    - **Use Agent Mail** (if available) for inter-agent messaging to prevent merge conflicts
    - **Claim before starting** -- each agent should mark beads `in_progress` before working
    - **Communicate blockers and discoveries**, not just status updates
    - **Group commits by bead/feature slice**, not by time
    - **Avoid communication purgatory** -- if an agent is spending more time coordinating than coding, something is wrong

## Typical Agent Allocation

For a medium-to-large project, Emanuel typically deploys:

| Agent type | Count | Role |
|------------|-------|------|
| Claude Code (Opus) | 5-6 | Primary implementation |
| Codex | 2-3 | Parallel implementation |
| Gemini | 1-2 | Review duties |

Scale up or down based on your bead graph size and budget.

---

!!! success "Stop condition"
    All beads are implemented and marked complete.
