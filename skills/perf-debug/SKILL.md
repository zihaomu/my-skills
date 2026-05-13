---
name: perf-debug
description: Investigate GPU/HPC and LLM performance regressions with evidence-first profiling. Use when debugging throughput, latency, occupancy, memory bandwidth, kernel timing, benchmark noise, or end-to-end performance regressions. Do not use for general code review or non-performance bugs.
---

# HPC Performance Investigation

Use this skill when the task is to explain or fix performance behavior, not just
change code. Treat profiler evidence, benchmark hygiene, and reproducible
measurements as the source of truth.

## Workflow

1. State the performance question in one sentence: target metric, workload,
   hardware, backend, and baseline.
2. Read [references/benchmark-hygiene.md](references/benchmark-hygiene.md) before
   trusting any number.
3. Read [references/profiling-methodology.md](references/profiling-methodology.md)
   to choose the next measurement.
4. Use [references/roofline-and-bottlenecks.md](references/roofline-and-bottlenecks.md)
   when classifying compute, memory, launch, synchronization, or communication
   limits.
5. Use [references/regression-triage.md](references/regression-triage.md) when
   comparing against a previous commit, branch, release, hardware target, or
   framework version.
6. Only propose a fix after the bottleneck hypothesis has direct evidence.

## Required Output

- Baseline and new measurements, including exact command and environment.
- Bottleneck hypothesis with the profiler evidence that supports it.
- Change proposal ranked by expected impact and implementation risk.
- Verification plan that would falsify the hypothesis if it is wrong.

## Hard Rules

- Do not infer a kernel bottleneck from wall-clock timing alone.
- Do not compare numbers across different clocks, power limits, batch shapes,
  model weights, precision modes, compiler flags, or warmup settings.
- If the user asks for "latest" behavior in ROCm, Triton, vLLM, SGLang, CUDA, or
  TileLang, verify current upstream docs or source before relying on memory.
