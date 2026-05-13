---
name: root-cause
description: Run a disciplined root-cause workflow for bugs, regressions, flaky behavior, and unexplained failures. Use when the user explicitly asks for root cause analysis, structured debugging, or an investigation workflow. Prefer domain-specific skills for performance or kernel issues and use this skill as the generic debugging backbone.
---

# Root Cause Investigation

Use this skill when fixing the symptom without understanding the cause would be
risky. The workflow is generic; pair it with domain skills such as
`perf-debug`, `kernel-review`, or `rocm-hip` when the failure
is domain-specific.

## Workflow

1. Read [references/investigation-phases.md](references/investigation-phases.md).
2. Capture the symptom, expected behavior, actual behavior, and reproduction
   path.
3. Inspect the relevant code path before proposing a fix.
4. Build one testable hypothesis at a time.
5. Use [references/hypothesis-log.md](references/hypothesis-log.md) to track
   evidence, failed attempts, and discarded theories.
6. Implement the smallest fix that addresses the confirmed root cause.
7. Verify with the original reproduction and a regression test when feasible.
8. Report using [references/debug-report.md](references/debug-report.md).

## Hard Rules

- No fix before a concrete root-cause hypothesis.
- No "should fix it" language; verify or say what remains unverified.
- If three hypotheses fail, stop and reassess architecture, environment, or
  missing evidence.
- Keep edits scoped to the failing subsystem unless the evidence proves a wider
  cause.
