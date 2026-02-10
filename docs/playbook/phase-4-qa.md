---
icon: lucide/search-check
---

# Phase 4: QA the Beads

!!! info "Goal"
    Run repeated review passes over the beads until revisions flatline.

This is the "check your beads N times, implement once" principle. Each pass should catch missing tasks, wrong dependencies, unclear acceptance criteria, and missing test coverage.

## Prompt: Beads QA

Run this prompt repeatedly. Each pass will find fewer issues until the graph stabilizes.

``` title="Beads QA prompt (repeat until stable)"
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

## Recommended Pass Focus

| Pass | Focus |
|------|-------|
| 1 | **Completeness** -- are all plan items represented? |
| 2 | **Dependencies** -- are orderings correct? Missing links? |
| 3 | **Scope** -- are beads too large or too small? |
| 4 | **Tests** -- is coverage comprehensive with detailed logging? |
| 5 | **Security/ops** -- are there beads for threats, alerts, monitoring? |

!!! warning "Don't oversimplify"
    The two most important guardrails in QA are **DO NOT OVERSIMPLIFY** and **DO NOT LOSE FEATURES**. Agents under-scoping beads during QA is the most common failure mode. Watch for it.

---

!!! success "Stop condition"
    Beads changes are mostly reordering or renaming, not missing work or wrong dependencies. The graph has **converged.**
