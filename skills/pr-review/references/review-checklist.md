# Review Checklist

## Correctness

- Does the diff implement the intended behavior?
- Are edge cases covered?
- Are error paths and cleanup paths correct?
- Are concurrency, async, caching, and state transitions safe?

## Compatibility

- Does the change preserve public API behavior?
- Are backend-specific changes properly guarded?
- Are migrations, config changes, or env vars documented?
- Does the change work across supported platforms?

## Tests

- Is there a regression test for bug fixes?
- Are tests at the right level: unit, integration, kernel correctness, or e2e?
- Do tests fail without the change?
- Are flaky or slow tests isolated?

## Operations

- Are logs, metrics, or failure modes adequate?
- Are docs updated when behavior changes?
- Are generated files or lockfiles intentional?
- Does CI cover the relevant path?

