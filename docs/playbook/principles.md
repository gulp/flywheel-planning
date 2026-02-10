---
icon: lucide/lightbulb
---

# Principles

These are the ideas behind the workflow. Understand these first -- the phases are just the implementation.

## 1. Planning is leverage

High-quality planning compresses implementation time, reduces rework, and improves architecture and UX before code exists. An hour spent refining a plan saves days of agent-generated code churn.

## 2. Iterative refinement beats single-shot

Repeated critique cycles reliably improve robustness, testability, and clarity. No single pass -- no matter how good the model -- catches everything. Four to five rounds is the sweet spot before diminishing returns.

## 3. Diff-based revisions are the key mechanic

Requiring git-diff style edits prevents vague advice and forces concrete, integratable changes. When a reviewer says "improve error handling," that's useless. When they provide a diff, it's actionable.

## 4. Separate plan space from code space

Optimize the plan and beads until they stabilize; only then start expensive swarm execution. Planning tokens are cheap. Code generation tokens are expensive. Debugging tokens from bad plans are the most expensive of all.

## 5. Use the right model for the job

| Work type | Recommended model |
|-----------|-------------------|
| High-volume, deterministic work (classification, filtering, structured extraction) | GPT-5.2 (xhigh-thinking) |
| Creative/strategic reasoning (architecture tradeoffs, UX, synthesis) | Claude Opus |
| Long plan critiques via web app | Extended reasoning (cheap relative to code) |

## 6. Beads are an execution graph, not a todo list

You're converting narrative intent into granular tasks with explicit dependencies so agents can coordinate safely. Each bead should be self-contained -- an agent picking it up should not need to re-read the entire plan.

## 7. Check your beads N times, implement once

Repeated beads review catches missing tasks, wrong dependencies, unclear acceptance criteria, and missing test coverage. This is the "measure twice, cut once" of agentic development.

## 8. Avoid communication purgatory

Coordination is valuable, but progress requires agents to pick actionable beads and ship. If agents spend more time messaging each other than writing code, something is wrong.

## 9. Fresh-eyes review loops work

After agents implement, run repeated "reread what you wrote and fix obvious issues" loops until changes flatline. Each pass catches things the previous one missed because the agent's context has shifted.

---

## What Great Plans Include

Use this as a checklist when drafting or reviewing your plan. A "good" plan has some of these. A "great" plan has all of them.

- [x] **Goals and non-goals** -- prevents scope creep and bikeshedding
- [x] **User stories and success criteria** -- what "done" means from the user's standpoint
- [x] **Architecture and data model** -- components, boundaries, invariants, failure modes
- [x] **Security and privacy model** -- threat model, secrets handling, encryption strategy
- [x] **Performance targets** -- latency, throughput, memory, cost budgets, instrumentation plan
- [x] **Operational plan** -- deploy, migrations, observability, alerts, rollback strategy
- [x] **Testing plan** -- unit + integration + e2e, with logging requirements and failure reproduction
- [x] **Migration/backward-compat plan** -- if evolving an existing system
- [x] **Risk register** -- top risks, mitigations, what must be validated early
