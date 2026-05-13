# vLLM And SGLang Performance

Use current upstream docs/source when flag names or defaults matter.

## Common Optimization Areas

- Continuous batching and admission control.
- Chunked prefill and prefill/decode overlap.
- Prefix caching, RadixAttention, or equivalent cache reuse mechanisms.
- Paged attention and KV memory layout.
- Speculative decoding.
- Quantization and quantized KV cache.
- Tensor, pipeline, data, and expert parallelism.
- Attention backend selection.
- Graph capture or persistent execution paths.

## Analysis Questions

- Is the workload prefill-heavy or decode-heavy?
- Does the system saturate GPU compute, memory bandwidth, CPU scheduler, or
  network communication?
- Are requests homogeneous or highly variable in sequence length?
- Is the bottleneck at steady-state or during admission bursts?
- Does optimization improve p99 or only mean throughput?

## Evidence

Prefer:

- Request-level metrics with percentiles.
- Stage-level traces.
- Scheduler queue depth and batch composition.
- GPU timeline and memory usage.
- Cache hit/miss and eviction behavior.

