# Tests And CI Matrix

## Test Classes

- Unit tests for pure logic.
- Kernel correctness tests for numerical behavior.
- Integration tests for backend dispatch and framework wiring.
- Benchmark smoke tests for performance-sensitive paths.
- Regression tests tied to an issue or failing command.

## CI Matrix

State what is covered:

- Backend: CUDA, HIP/ROCm, CPU, TPU/XPU if relevant.
- Python/runtime versions.
- Hardware availability.
- Optional dependencies.
- Distributed vs single-device.

## Manual Validation

When upstream CI lacks hardware, include a manual validation block:

```text
Hardware:
Runtime:
Command:
Before:
After:
Notes:
```

Do not imply CI coverage that does not exist.

