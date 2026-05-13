# Failure Patterns

## Engineering

- Accidental complexity disguised as flexibility.
- Hidden global state.
- Missing rollback path.
- Tests proving mocks instead of behavior.
- Concurrency path not represented in tests.
- Backward compatibility assumed but not checked.

## Performance

- Average throughput improves while tail latency regresses.
- Microbenchmark wins do not map to end-to-end metrics.
- Warm cache benchmark used for cold cache workload.
- Kernel speedup loses request-level performance through scheduling or memory
  pressure.

## Open Source

- Maintainer cannot reproduce the claim.
- Backend-specific fix leaks into generic code.
- CI matrix does not cover the claimed support.
- Docs imply broader support than tested.

