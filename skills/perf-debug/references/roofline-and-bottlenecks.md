# Roofline And Bottleneck Classification

Classify the limit before optimizing.

## Compute Bound

Evidence:

- High VALU/MFU utilization.
- Low memory pressure relative to peak bandwidth.
- Kernel dominated by math instructions.
- Speed scales with lower precision or tensor-core/MFMA path changes.

Likely fixes: improve data layout for matrix instructions, remove redundant math,
use specialized kernels, adjust tile sizes, fuse only if it raises arithmetic
intensity without hurting occupancy.

## Memory Bound

Evidence:

- Bandwidth near ceiling or cache miss rates high.
- Low arithmetic intensity.
- Strided/scattered access or poor coalescing.
- Register or LDS spills.

Likely fixes: coalesce loads/stores, improve vectorization, change layout, stage
through shared/LDS, reduce reloads, reduce KV/cache traffic, compress or quantize
when numerically acceptable.

## Launch Or Synchronization Bound

Evidence:

- Timeline gaps dominate.
- Many tiny kernels.
- Host-side scheduler overhead visible.
- Barriers or collectives stall progress.

Likely fixes: graph capture, batching, fusion, persistent kernels, async copies,
reducing global barriers, better overlap, less CPU orchestration.

## Communication Bound

Evidence:

- Collectives dominate wall time.
- Scaling efficiency drops as ranks increase.
- Network or interconnect counters saturate.

Likely fixes: reduce all-reduce frequency/volume, overlap communication with
compute, alter parallelism strategy, tune RCCL/NCCL topology, shard differently.

