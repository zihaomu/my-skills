# Benchmark Matrix

Use a matrix that matches the product question.

## Dimensions

- Model and precision.
- Prompt length distribution.
- Output length distribution.
- Concurrency or request rate.
- Cache state: cold, warm, prefix-hit, mixed.
- Parallelism configuration.
- Quantization and attention backend.
- Hardware and interconnect.

## Metrics

- Tokens/sec total.
- Prefill tokens/sec.
- Decode tokens/sec.
- Time to first token.
- Inter-token latency.
- p50/p90/p99 request latency.
- GPU memory peak and steady state.
- Error rate and rejected requests.

## Guardrail

Every benchmark result should state what decision it supports. If it does not
support a decision, do not let it drive code changes.

