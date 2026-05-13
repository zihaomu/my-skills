---
name: kernel-review
description: Review and improve CUDA, HIP, Triton, and TileLang kernels for performance and correctness. Use when inspecting GPU kernels, custom ops, memory tiling, occupancy, numerics, launch configuration, or backend portability. Do not use for non-kernel application code.
---

# Kernel Optimization Review

Use this skill for kernel-level work. Keep the review grounded in target hardware,
compiler behavior, generated code, and numerical correctness.

## Workflow

1. Identify kernel language, target hardware, datatype path, tensor shapes, and
   correctness oracle.
2. Load the smallest relevant references:
   - CUDA/HIP: [references/cuda-hip-kernel-checklist.md](references/cuda-hip-kernel-checklist.md)
   - Triton/TileLang: [references/triton-tilelang-patterns.md](references/triton-tilelang-patterns.md)
   - Memory pipeline: [references/memory-pipeline.md](references/memory-pipeline.md)
   - Numerics: [references/numerics-and-correctness.md](references/numerics-and-correctness.md)
   - Current docs map: [references/source-map.md](references/source-map.md)
3. Inspect the existing implementation before proposing a rewrite.
4. Separate correctness changes from performance changes when possible.
5. Demand a microbenchmark and a correctness test for every meaningful kernel
   change.

## Review Axes

- Mapping: block/grid, CTA/warp/wave, tensor tile, boundary masks.
- Data movement: global coalescing, vectorization, shared/LDS use, async staging.
- Compute: instruction selection, tensor-core/MFMA path, loop unrolling.
- Resources: occupancy, registers, spills, shared/LDS pressure.
- Numerics: accumulation dtype, order sensitivity, edge cases, tolerance.
- Portability: CUDA/HIP semantic differences, architecture-specific assumptions.

## Output Format

Lead with findings ordered by impact. For each finding include:

- Location.
- Evidence.
- Risk.
- Suggested fix.
- Test or benchmark required.
