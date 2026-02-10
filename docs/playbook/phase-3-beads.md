---
icon: lucide/git-branch
---

# Phase 3: Convert Plan to Beads

!!! info "Goal"
    Transform the stable plan into a granular execution graph with epics, tasks, subtasks, and explicit dependencies.

Beads should be **self-contained and self-documenting.** An agent working on a bead should not need to constantly refer back to the plan.

## What Makes Good Beads

Each bead should include:

- **Clear scope** -- what exactly needs to be done
- **Acceptance criteria** -- how to know when it's done
- **Context and rationale** -- why this task exists
- **Dependencies** -- what must complete first (blocks/related/parent-child)
- **Constraints** -- guardrails the implementation must respect

Don't forget beads for:

- Comprehensive unit tests (meaningful coverage, not shallow mocks)
- End-to-end / integration scripts with detailed logging
- Observability and alerts for silent-failure risk areas

## Prompt: Plan-to-Beads Conversion

``` title="Plan-to-beads prompt"
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

!!! success "Stop condition"
    All plan sections have been converted to beads with dependencies. No plan content is left unrepresented.
