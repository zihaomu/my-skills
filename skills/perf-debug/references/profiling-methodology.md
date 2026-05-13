# Profiling Methodology

Prefer the smallest measurement that can falsify the current hypothesis.

## Measurement Ladder

1. End-to-end request metrics: throughput, latency distribution, error rate.
2. Stage timing: tokenize, scheduling, prefill, decode, sampling, network, IO.
3. GPU timeline: kernel order, gaps, memcpy, collectives, graph replay.
4. Kernel counters: occupancy, waves, memory bandwidth, cache hit rates,
   register pressure, spills, LDS/shared memory behavior.
5. Source-level inspection: indexing, vectorization, tiling, synchronization,
   masks, boundary handling, numerical path.

## Tools

Use the repo's existing tooling first. Common choices:

- ROCm: `rocprof`, `rocprofv3`, Omniperf, Omnitrace, `rocm-smi`.
- CUDA: Nsight Systems, Nsight Compute, `nvidia-smi`.
- PyTorch: profiler, CUDA/HIP events, framework-level traces.
- Serving: framework metrics, request logs, scheduler traces, benchmark harness.

## Hypothesis Form

Write hypotheses in this shape:

```text
The slowdown is likely <class> because <measurement> changed from <old> to <new>
under identical <workload/env>. The next check is <measurement> and would
disprove this if <expected counterevidence>.
```

Avoid "probably faster" or "should improve" claims without measurable exit
criteria.

