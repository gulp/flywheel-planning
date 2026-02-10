---
icon: lucide/copy
---

# Prompt Pack

All prompts in one place, ready to copy-paste. Replace placeholders like `<PROJECT_NAME>`, `<PLAN_FILE_PATH>`, etc.

---

## 1. Plan Drafting (Phase 1)

``` title="Plan drafting prompt"
You are a senior architect and staff engineer. We are starting a greenfield project:

Project: <PROJECT_NAME>
Users: <TARGET_USERS>
Problem: <PROBLEM_STATEMENT>
Constraints: <CONSTRAINTS>
Environment: <LANGUAGE/STACK/PLATFORM>

Write a single, extremely detailed markdown plan we can implement with coding agents.

Requirements:

- Start with Goals / Non-goals.
- Include a clear architecture section: components, boundaries, invariants, data flow.
- Include data model / schemas (as needed).
- Include security & privacy model (threats, mitigations, secrets handling).
- Include performance targets (with concrete numbers) and an instrumentation plan.
- Include error handling, retries, and "no silent fallback" philosophy.
- Include a test plan: unit + integration + e2e (with detailed logging expectations).
- Include rollout plan: feature flags, migrations, backwards compatibility (if relevant).
- Include a task breakdown section that could be converted into a dependency graph.

Be explicit and operational. Avoid vague advice.
Assume this plan will be executed by multiple parallel agents.
```

---

## 2. Plan Critique (Phase 2 -- Round Type A)

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

---

## 3. Multi-Model Merge (Phase 2 -- Round Type B)

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

---

## 4. Integrate Critique (Phase 2 -- Apply Feedback)

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

---

## 5. Plan to Beads (Phase 3)

``` title="Plan-to-beads conversion prompt"
Reread `AGENTS.md` so it's fresh in your mind.

Now read ALL of `<PLAN_FILE_PATH>`.

Please take ALL of that and elaborate on it more and then create a comprehensive
and granular set of beads for all this with:

- epics + tasks + subtasks (as needed)
- dependency structure overlaid (blocks/related/parent-child/discovered-from)
- detailed comments so the beads are self-contained and self-documenting

Include relevant background, reasoning/justification, constraints, and acceptance
criteria so we never need to refer back to `<PLAN_FILE_PATH>`.

Also include beads for:

- comprehensive unit tests (meaningful coverage, not shallow mocks)
- e2e/integration scripts with great, detailed logging
- observability/alerts for silent-failure risk areas

Use only the `bd` tool to create and modify beads and add dependencies. Be exhaustive.
```

---

## 6. Beads QA (Phase 4 -- Repeat N Times)

``` title="Beads QA prompt"
Reread `AGENTS.md` so it's still fresh in your mind.

We recently transformed a markdown plan into beads. I want you to very carefully
review and analyze these beads using `bd` and `bv` (robot flags only).

Check over each bead super carefully:

- does it make sense?
- is it optimally scoped?
- are dependencies correct?
- is any important work missing?
- are tests (unit + e2e) comprehensive enough, with detailed logging?
- are we missing security, performance, or ops beads?

DO NOT OVERSIMPLIFY THINGS.
DO NOT LOSE ANY FEATURES OR FUNCTIONALITY.

If improvements are needed, revise the beads accordingly using only `bd`.
```

---

## 7. Swarm Marching Orders (Phase 5)

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

---

## 8. Fresh-Eyes Self-Review (Phase 6)

``` title="Self-review prompt"
Great. Now carefully read over all of the new code you just wrote and any
existing code you modified.

With fresh eyes, look for:

- obvious bugs
- incorrect edge cases
- mismatched types / error handling gaps
- unclear naming / confusing flows
- missing tests
- silent failure modes
- performance footguns

Carefully fix anything you uncover. Be meticulous.
```

---

## 9. Reread AGENTS (Context Recovery)

``` title="Re-anchor prompt"
Reread `AGENTS.md` so it's still fresh in your mind. Use ultrathink.
```

---

## 10. Cross-Agent Review (Phase 6)

``` title="Cross-agent review prompt"
Now review code written by other agents across the project (not just the
latest commit).

Look for:

- bugs, edge cases, and inconsistencies
- security/privacy issues
- reliability issues (retries, timeouts, idempotency)
- performance regressions
- unclear or brittle architecture
- missing or low-quality tests

Diagnose root causes using first-principles reasoning and then fix issues you find.
```

---

## 11. Commit and Push

``` title="Commit prompt"
Based on your knowledge of the project, commit all changed files now in a series
of logically connected groupings with detailed commit messages for each,
and then push.

Constraints:

- Don't edit code at all in this step.
- Don't commit ephemeral files or secrets.
- Follow repo conventions and hooks.
```
