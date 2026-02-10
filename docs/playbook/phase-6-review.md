---
icon: lucide/eye
---

# Phase 6: Fresh-Eyes Review

!!! info "Goal"
    Repeatedly review implemented code until review passes produce no substantive diffs.

## Prompt: Self-Review

Run this after each chunk of implementation. The agent re-reads its own code with fresh eyes.

``` title="Self-review prompt (run after each implementation chunk)"
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

## Prompt: Cross-Agent Review

Have agents review each other's work -- not just the latest commit, but code across the project.

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

## Prompt: Commit and Push

Use **only** when you're ready to package work. Group commits by bead/feature slice.

``` title="Commit prompt (use only when ready)"
Based on your knowledge of the project, commit all changed files now in a series
of logically connected groupings with detailed commit messages for each,
and then push.

Constraints:

- Don't edit code at all in this step.
- Don't commit ephemeral files or secrets.
- Follow repo conventions and hooks.
```

!!! tip "Why fresh-eyes loops work"
    Each review pass catches things the previous one missed because the agent's mental model has shifted. The first pass catches obvious bugs. The second catches architectural inconsistencies. The third catches edge cases. By the fourth or fifth pass, you're getting clean results.

---

!!! success "Stop condition"
    Repeated fresh-eyes passes produce **no substantive diffs.** The code has converged.
