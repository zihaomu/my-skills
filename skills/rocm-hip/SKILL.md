---
name: rocm-hip
description: Work on AMD ROCm, HIP, RCCL, and AMD backend support in open-source ML systems. Use when porting CUDA to HIP, reviewing ROCm compatibility, debugging AMD GPU behavior, writing upstream AMD backend patches, or checking gfx target and CI coverage.
---

# AMD ROCm And HIP

Use this skill for AMD GPU and ROCm ecosystem work. Be precise about ROCm
version, gfx target, compiler, framework commit, and whether the issue is
runtime, compiler, library, or kernel-level.

## Workflow

1. Identify the target stack: ROCm/HIP version, gfx target, PyTorch/runtime,
   framework, driver, and OS/container.
2. For CUDA-to-HIP work, read [references/rocm-portability.md](references/rocm-portability.md).
3. For code review, read [references/hip-review-checklist.md](references/hip-review-checklist.md).
4. For upstream contribution shape, read [references/amd-upstream-notes.md](references/amd-upstream-notes.md).
5. For tests, read [references/ci-matrix.md](references/ci-matrix.md).
6. Use [references/source-map.md](references/source-map.md) and verify current
   official docs or upstream code when version-specific behavior
   matters.

## Default Review Posture

- Prefer portable HIP and framework abstractions unless a target-specific path is
  required for performance.
- Keep AMD-specific behavior guarded and documented.
- Do not accept "hipify compiles" as proof that a patch is correct.
- Always ask whether NVIDIA behavior must remain bitwise, numerically, or only
  functionally equivalent.

## Output

Return a concise compatibility assessment:

- Supported AMD targets and untested targets.
- CUDA assumptions found.
- Required HIP/ROCm changes.
- CI or benchmark gaps.
- Upstream risk and maintainer-facing explanation.
