---
name: red-team
description: Challenge a proposed solution, patch, benchmark claim, or plan from a skeptical engineering perspective. Use when the user explicitly asks for adversarial review, red-team review, second opinion, or to find what could be wrong with an approach.
---

# Adversarial Review

Use this skill to find failure modes, weak assumptions, missing evidence, and
overconfident claims. The goal is better engineering judgment, not negativity.

## Workflow

1. Identify the claim or proposal being challenged.
2. Read [references/challenge-rubric.md](references/challenge-rubric.md).
3. Inspect evidence before disagreeing.
4. Use [references/failure-patterns.md](references/failure-patterns.md) to search
   for likely blind spots.
5. Produce output with [references/output-format.md](references/output-format.md).

## Rules

- Attack assumptions and evidence, not style.
- Separate proven issues from plausible risks.
- Name what evidence would change the conclusion.
- If the proposal is sound, say so and list the residual risks.
- For performance claims, require benchmark hygiene and profiler evidence.

## Domain Routing

Use domain references when the challenge is about kernels, ROCm/HIP, LLM serving,
or upstream PR readiness.
