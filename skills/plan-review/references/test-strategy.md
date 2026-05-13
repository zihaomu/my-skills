# Test Strategy

## Required Test Plan

State:

- Unit tests.
- Integration tests.
- End-to-end or benchmark tests.
- Regression tests for known failures.
- Manual validation when hardware or external services are required.

## Test Quality Questions

- Would the test fail without the implementation?
- Does it cover boundary shapes, error paths, and concurrency where relevant?
- Is there a correctness oracle?
- Are performance thresholds stable enough for CI?
- Are hardware-specific paths covered or documented as manual validation?

