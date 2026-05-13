---
name: plan-review
description: Review an engineering plan before implementation for scope, architecture, data flow, failure modes, test strategy, rollout, and performance risk. Use when the user explicitly asks for plan review, architecture review, design review for implementation, or wants to lock a plan before coding.
---

# Engineering Plan Review

Use this skill before implementation starts. The goal is to catch expensive
mistakes while the plan is still cheap to change.

## Workflow

1. Read the user's plan or design doc.
2. Read [references/scope-challenge.md](references/scope-challenge.md).
3. Review architecture and data flow with
   [references/architecture-checklist.md](references/architecture-checklist.md).
4. Review tests with [references/test-strategy.md](references/test-strategy.md).
5. Review failure modes and rollout with
   [references/failure-modes.md](references/failure-modes.md).
6. Produce the final review with [references/output-format.md](references/output-format.md).

## Operating Rules

- Do not edit code while reviewing a plan.
- Identify what already exists before proposing new components.
- Challenge unnecessary scope, but do not re-argue after the user accepts a
  larger scope.
- Prefer explicit, testable plans over clever abstractions.
- Include a "not in scope" section for deliberate deferrals.

## Domain Routing

For plans involving GPU kernels, ROCm/HIP, vLLM, SGLang, Triton, or TileLang,
combine this workflow with the relevant domain skill.
