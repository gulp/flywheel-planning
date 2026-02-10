---
icon: lucide/iteration-cw
---

# Phase 2: Refine the Plan

!!! info "Goal"
    Iterate the plan through **4-5 critique rounds** until improvements become incremental.

This is where most of the value is created. Emanuel reports spending **85%+ of time and energy on planning phases.** Each round should produce concrete diff-style changes, not vague suggestions.

## Round Type A: Single-Model Critique

Paste the entire plan into a reasoning model and request structured feedback.

``` title="Single-model critique prompt"
Carefully review this entire plan for me and come up with your best revisions
in terms of:

- better architecture
- missing or improved features
- reliability and failure handling
- security and privacy
- performance and scalability
- clarity and implementability for coding agents
- testing depth (unit + e2e)
- operational robustness (observability, alerts, rollbacks)

For each proposed change:

1. Give a detailed analysis and rationale/justification.
2. Provide git-diff style changes relative to the original markdown plan shown below.

<PASTE THE COMPLETE PLAN HERE>
```

## Round Type B: Multi-Model Merge

If you ran the critique through multiple models (e.g., GPT-5.2 Pro and Claude Opus), merge the best ideas into one coherent design.

``` title="Multi-model merge prompt"
I asked multiple models to produce competing plan reviews (or competing plans).
You'll see them below.

I want you to:

- analyze them with an open mind
- be intellectually honest about what they do better than the current plan
- propose the best possible revisions to the current plan that blend the best
  ideas into one coherent design

Output:

1. A short synthesis of the strongest ideas worth integrating.
2. A git-diff style patch against the current plan.

Current plan:
<PASTE CURRENT PLAN HERE>

Competing outputs:
<PASTE OTHER MODEL OUTPUTS HERE>
```

## Integration: Apply Feedback to the Plan

After each critique round, have a coding agent integrate the changes in-place.

``` title="Integration prompt (give to coding agent)"
Read `AGENTS.md` and keep all tool rules in mind.

Now integrate the following review feedback into `<PLAN_FILE_PATH>` in-place.
Be meticulous: keep the plan cohesive, consistent, and remove contradictions.

At the end, list:

- changes you strongly agree with
- changes you somewhat agree with
- changes you disagree with (and why)

<PASTE THE COMPLETE REVIEW OUTPUT HERE>
```

## Recommended Cadence

| Round | Focus |
|-------|-------|
| 1 | Architecture, data model, component boundaries |
| 2 | Security, failure modes, edge cases |
| 3 | Performance, scalability, operational concerns |
| 4 | Testing depth, observability, developer experience |
| 5 | Final pass: clarity, consistency, agent-operability |

!!! tip "Why diff-based?"
    Requiring git-diff style output prevents the reviewer from giving vague advice like "consider improving error handling." Instead, they must produce a concrete patch that can be applied directly to the plan. This is the single most important mechanic in the refinement loop.

---

!!! success "Stop condition"
    You're seeing only minor wording tweaks and no meaningful architectural, testing, or operational improvements. The plan has **converged.**
