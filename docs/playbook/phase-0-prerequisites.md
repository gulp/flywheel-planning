---
icon: lucide/settings
---

# Phase 0: Prerequisites

!!! info "Goal"
    Environment is ready for agent-driven development.

Before you start planning, make sure the scaffolding is in place.

## Checklist

- [ ] Your repo has an `AGENTS.md` explaining tool rules, model selection, and safety constraints
- [ ] Beads is initialized (or will be initialized) for the project
- [ ] You've decided where your canonical plan lives (e.g., `PLAN.md` in repo root)
- [ ] Agent coordination tooling is available (Agent Mail, if using multi-agent)
- [ ] You have access to a strong reasoning model for plan critique (web app with extended thinking)

## About AGENTS.md

`AGENTS.md` is the instruction manual agents read before doing anything. It should include:

- **Tool rules** -- which tools agents can use and how
- **Model selection guidance** -- which model to use for which task type
- **Safety constraints** -- what agents must never do (force push, delete prod data, etc.)
- **Repository conventions** -- commit message format, branch naming, test requirements
- **Coordination rules** -- how agents claim work and communicate (if multi-agent)

## About Beads

Beads is the task management system. Think of it as a dependency-aware task graph where:

- **Epics** contain related groups of work
- **Tasks** are individual units of work
- **Subtasks** break tasks into smaller steps
- **Dependencies** define what must complete before something else can start

Each bead is self-documenting: it includes enough context that an agent can pick it up and work without re-reading the entire plan.

## Setting Up the Flywheel

The easiest way to get all tooling configured is the [Agentic Coding Flywheel Setup](https://github.com/Dicklesworthstone/agentic_coding_flywheel_setup), which transforms a fresh VPS into a fully-armed agentic coding environment. The setup wizard is available at [agent-flywheel.com](https://agent-flywheel.com/).

---

!!! success "Stop condition"
    All checklist items are complete. You're ready to start planning.
