# KV Cache And Scheduling

KV cache behavior often dominates long-context serving economics.

## KV Cache Questions

- What is the maximum live token budget?
- Are blocks/pages fragmented?
- What is the cache hit rate for prefix or hierarchical caches?
- What eviction policy applies under pressure?
- Does quantized KV alter quality or kernel path?
- Is cache transfer or recomputation cheaper for this workload?

## Scheduler Questions

- Is batching limited by memory, compute, fairness, or latency target?
- Are prefill and decode competing for the same GPU resources?
- Does chunked prefill reduce TTFT or create decode jitter?
- Are short requests starved by long contexts?
- Does speculative decoding change acceptance rate under real prompts?

## Failure Modes

- Throughput increases while p99 latency regresses.
- Cache hit rate looks high but saved tokens are small.
- Admission policy works on synthetic lengths but fails on production
  distribution.
- Memory headroom disappears at peak concurrency.

