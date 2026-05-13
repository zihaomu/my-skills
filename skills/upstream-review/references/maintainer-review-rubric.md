# Maintainer Review Rubric

## Blockers

- Fails existing tests.
- Changes public API without migration path.
- Breaks another backend.
- Adds unsupported dependency or build requirement.
- Performance claim without reproducible command.
- Correctness test missing for kernel or numerical change.

## High-Value Improvements

- Smaller diff preserving current architecture.
- Clear backend guards.
- Better test parametrization across CUDA/HIP/CPU.
- Documentation for new flags or limitations.
- Benchmark script added or existing benchmark extended.

## Maintainer-Facing Explanation

Good PR summaries answer:

- What problem does this fix?
- Why is this approach the smallest reasonable change?
- What alternatives were considered?
- How was it tested?
- What remains unsupported?

