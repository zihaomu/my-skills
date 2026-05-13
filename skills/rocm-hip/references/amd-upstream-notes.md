# AMD Upstream Notes

Use this when preparing changes for open-source projects.

## Maintainer-Friendly Patch Shape

- Keep backend-specific code localized.
- Preserve existing NVIDIA and CPU behavior.
- Add AMD tests or extend backend-parametrized tests.
- Include a small reproduction or benchmark when fixing performance.
- Explain why a guard is target-specific rather than general.

## Review Risks

- Adding AMD-only branches that duplicate too much logic.
- Silently weakening tests for all backends.
- Introducing env-var requirements without documentation.
- Claiming support without CI coverage.
- Changing public APIs to solve a backend-local issue.

## Evidence To Include

- Hardware and ROCm version.
- Failing command before the patch.
- Passing command after the patch.
- Relevant profiler or log evidence for performance fixes.
- Compatibility note for unsupported targets.

