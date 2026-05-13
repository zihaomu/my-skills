---
name: upstream-review
description: Review or prepare upstream open-source PRs for ML systems, GPU kernels, ROCm/HIP, vLLM, SGLang, Triton, TileLang, and related infrastructure. Use when checking maintainer readiness, patch scope, test evidence, CI matrix, benchmark claims, or review comments.
---

# Upstream PR Review

Use this skill when the outcome is an upstreamable patch, review, or maintainer
response.

## Workflow

1. Identify target project, contribution type, and maintainer constraints.
2. Read [references/maintainer-review-rubric.md](references/maintainer-review-rubric.md).
3. Read [references/tests-and-ci-matrix.md](references/tests-and-ci-matrix.md).
4. Use [references/review-output.md](references/review-output.md) for the final
   structure.
5. Inspect the diff before making claims.
6. Check upstream docs/source when API, flag, or backend behavior may have
   changed.

## Review Posture

- Minimize patch scope.
- Preserve existing behavior for other backends.
- Prefer tests that prove the exact bug or performance path.
- Make benchmark claims reproducible.
- Do not hide backend-specific limitations.

## Output

Lead with blockers, then maintainer-facing improvements, then optional polish.
