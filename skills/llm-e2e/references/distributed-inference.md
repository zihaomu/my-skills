# Distributed Inference

Use this for multi-GPU or multi-node serving.

## Parallelism Modes

- Tensor parallelism: communication every layer; watch all-reduce cost.
- Pipeline parallelism: bubbles and load imbalance dominate if stages are uneven.
- Data parallelism: simpler scaling but duplicates weights and KV unless routed.
- Expert parallelism: routing balance and all-to-all behavior can dominate.
- Disaggregated prefill/decode: improves specialization but adds transfer,
  routing, and failure complexity.

## Checks

- Confirm topology: PCIe, Infinity Fabric, NVLink, Ethernet, InfiniBand.
- Capture collective timing separately from kernel timing.
- Check rank imbalance.
- Verify request routing preserves cache locality where needed.
- Include failure/retry semantics in production design.

## Reporting

Always report single-GPU baseline, multi-GPU scaling efficiency, and the first
parallelism level where efficiency bends.

