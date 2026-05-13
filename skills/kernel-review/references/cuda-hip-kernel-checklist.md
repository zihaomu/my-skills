# CUDA/HIP Kernel Checklist

## Correctness First

- Validate indexing against all boundary shapes, not just multiples of tile size.
- Check aliasing and in-place behavior.
- Confirm synchronization scope: block, warp/wave, device, stream.
- Check atomics for determinism and dtype support.
- Confirm error handling around launches and async copies.

## Launch And Mapping

- Match block size to wave/warp granularity and occupancy limits.
- Avoid hidden assumptions that warp size is always 32 when targeting AMD.
- Check grid mapping for load balance across ragged shapes.
- Make architecture-specific paths explicit and guarded.

## Memory

- Prefer coalesced vectorized global accesses when alignment permits.
- Avoid shared/LDS bank conflicts in staged tiles.
- Minimize redundant global reads, especially KV/cache and scale/zero-point data.
- Check register spills before increasing tile sizes.

## HIP/ROCm Portability

- Verify CUDA APIs and intrinsics have HIP equivalents and the same semantics.
- Treat hipify output as a starting point, not proof of portability.
- Check compilation for each relevant gfx target.
- Watch for implicit CUDA-only library calls and inline PTX.

