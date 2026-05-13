# Memory Pipeline

Use this when optimizing data movement.

## Questions

- What is the unit of reuse: element, vector, tile, row, block, page, KV segment?
- Is data reused enough to justify staging?
- Are loads coalesced at the hardware transaction level?
- Are stores coalesced and write-combined?
- Does the kernel overlap copy and compute or serialize them?
- Does the layout force gather/scatter in the hot path?

## Pipeline Smells

- Timeline shows long memory stalls but low arithmetic utilization.
- Repeated loads of scale, metadata, or KV pages.
- LDS/shared memory usage increases but bandwidth does not improve.
- Register pressure rises after adding staging.
- Fusion reduces launches but worsens cache locality or occupancy.

## Verification

Use profiler counters where available. A memory optimization should show at least
one of:

- Lower bytes moved for the same output.
- Better cache hit rate.
- Higher achieved bandwidth with same correctness.
- Fewer timeline gaps or fewer dependent memory stalls.

