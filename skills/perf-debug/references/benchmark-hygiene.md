# Benchmark Hygiene

Use this before trusting performance numbers.

## Minimum Metadata

Capture:

- Hardware: GPU/accelerator model, count, interconnect, CPU, NUMA topology.
- Driver/runtime: ROCm or CUDA version, HIP runtime, PyTorch version, compiler.
- Framework commit/version: vLLM, SGLang, Triton, TileLang, CK, custom repo.
- Workload: model, precision, batch/concurrency, prompt/output lengths, sequence
  distribution, cache state, tokenizer path, dataset.
- Runtime controls: power limit, clocks if pinned, env vars, graph capture,
  quantization, attention backend, tensor/pipeline/data/expert parallelism.
- Measurement protocol: warmup, samples, p50/p90/p99, steady-state window,
  outlier policy.

## Valid Comparisons

A before/after comparison is valid only if all non-experimental dimensions are
fixed. If anything changes, report it as a confounder.

For LLM serving, separate:

- Prefill throughput.
- Decode token throughput.
- Time to first token.
- Inter-token latency.
- Tail latency under concurrency.
- GPU memory headroom and KV cache pressure.

## Red Flags

- Single sample benchmark.
- Mixed warmup and measured iterations.
- Comparing different max sequence lengths or cache hit rates.
- Implicit backend change from environment variables.
- Kernel timing without synchronization.
- Synthetic microbenchmark used to claim end-to-end speedup without mapping it
  back to request-level metrics.

