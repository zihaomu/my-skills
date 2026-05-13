# Numerics And Correctness

Kernel speedups are invalid if they silently change model quality or stability.

## Required Tests

- Compare against a trusted reference implementation.
- Include non-multiple shapes, empty or tiny shapes, max supported shape, and
  mixed stride/layout cases.
- Test all relevant dtypes and accumulation modes.
- Include deterministic seed and tolerance policy.

## Tolerance Policy

Define:

- Absolute and relative tolerance.
- Expected dtype and accumulation dtype.
- Whether order-dependent reductions are acceptable.
- Whether NaN/Inf propagation must match exactly.

## Review Traps

- FP16/BF16 accumulation where FP32 is required.
- Different rounding or saturation behavior after quantization changes.
- Fast math changing edge-case behavior.
- Masked values contributing to reductions.
- Atomic update order changing results beyond tolerance.

