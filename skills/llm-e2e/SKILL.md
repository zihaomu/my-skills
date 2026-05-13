---
name: llm-e2e
description: Analyze and optimize end-to-end LLM serving systems such as vLLM and SGLang. Use for throughput, TTFT, decode latency, KV cache, scheduling, batching, disaggregated prefill/decode, distributed inference, quantization, or serving benchmarks.
---

# LLM Serving End-To-End Optimization

Use this skill when the unit of success is request-level serving behavior, not a
single kernel in isolation.

## Workflow

1. Define workload and SLO: model, precision, prompt/output distribution,
   concurrency, TTFT, ITL, throughput, tail latency, memory target.
2. Identify framework and backend: vLLM, SGLang, custom engine, attention
   backend, quantization, parallelism, hardware.
3. Load references only as needed:
   - [references/vllm-sglang-perf.md](references/vllm-sglang-perf.md)
   - [references/kv-cache-scheduling.md](references/kv-cache-scheduling.md)
   - [references/distributed-inference.md](references/distributed-inference.md)
   - [references/benchmark-matrix.md](references/benchmark-matrix.md)
   - [references/source-map.md](references/source-map.md)
4. Separate prefill, decode, scheduling, communication, and frontend/API costs.
5. Tie any kernel-level optimization back to request metrics.

## Output

Provide:

- Current bottleneck classification.
- Evidence and missing evidence.
- Optimization candidates ranked by expected request-level impact.
- Benchmark matrix for verification.
- Risks: correctness, quality, memory, admission control, and tail latency.

## Hard Rules

- Do not optimize average throughput while ignoring tail latency if the user is
  running an online serving workload.
- Do not claim a KV-cache change is beneficial without checking memory pressure,
  cache hit behavior, and eviction/admission effects.
- Verify current upstream docs/source for version-specific flags or behavior.
