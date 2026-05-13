# Promotion Rules

Promote knowledge only when it is useful across future machines and projects.

## Accept

- A reusable debugging method.
- A kernel review pitfall that has caused real bugs or regressions.
- A framework-specific behavior with version/source evidence.
- A benchmark protocol that prevents bad decisions.
- A maintainer preference learned from upstream review.

## Reject Or Archive

- One-off project facts.
- Private credentials, customer data, or proprietary logs.
- Unsourced claims that could be stale.
- Broad AI workflow advice unrelated to the user's domain.
- Anything already obvious to a strong general coding agent.

## Promotion Checklist

Before editing a skill reference:

1. Confirm domain fit.
2. Confirm source and confidence.
3. Add version/hardware boundaries if applicable.
4. Compress to the smallest useful rule.
5. Link it from exactly one `SKILL.md` unless truly cross-domain.
6. Run validation.

## Staleness Policy

Any item about ROCm, HIP, Triton, TileLang, vLLM, SGLang, PyTorch, CUDA, or
compiler behavior needs `last_verified`. If it is older than 90 days and the
task depends on exact behavior, verify upstream docs or source again before
using it as a rule.

