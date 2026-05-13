---
name: pr-review
description: Run a pre-merge diff review for correctness, tests, compatibility, docs, CI, and maintainability. Use when the user explicitly asks for a pre-landing review, PR review workflow, or final check before merging. Use domain skills for specialized GPU, ROCm, kernel, or LLM serving findings.
---

# Pre-Landing Review

Use this skill to review a concrete diff before it lands. This is a generic
workflow skill; it should route specialized concerns to the relevant domain
skill when needed.

## Workflow

1. Determine the base branch and changed files.
2. Read [references/review-checklist.md](references/review-checklist.md).
3. Inspect the diff and relevant surrounding code.
4. Use [references/risk-taxonomy.md](references/risk-taxonomy.md) to classify
   issues.
5. Check tests, docs, CI, migrations, generated files, and compatibility.
6. Use [references/output-format.md](references/output-format.md) for the final
   report.

## Review Posture

- Findings first, ordered by severity.
- Every finding needs file/line evidence.
- Prefer actionable fixes over broad advice.
- Do not flag style-only nits unless they affect maintainability or review
  acceptance.
- If no issues are found, say so and list residual test gaps.

## Domain Routing

- Kernel or custom op changes: consider `kernel-review`.
- ROCm/HIP/AMD backend changes: consider `rocm-hip`.
- vLLM/SGLang serving changes: consider `llm-e2e`.
- Upstream open-source PR readiness: consider `upstream-review`.
