# Regression Triage

Use this when a workload was faster before.

## Diff The World

Check these in order:

1. Code diff in the hot path.
2. Dependency and compiler changes.
3. Backend selection and env vars.
4. Shape distribution and prompt/output lengths.
5. Hardware, clocks, power, thermal behavior.
6. Scheduler or batching behavior.
7. Kernel dispatch sequence and timeline gaps.

## Bisect Strategy

- Prefer benchmark commands that run under 5 minutes and fail loudly.
- Pin inputs and seeds.
- Save raw logs and profiler artifacts outside the source tree unless the user
  asks to commit them.
- When a commit is identified, inspect both code and generated kernel behavior.

## Reporting

Report:

- First bad commit or narrowest known range.
- The metric delta and confidence.
- The changed subsystem.
- The smallest revert or forward fix candidate.
- Tests or perf guardrails that would have caught it.

