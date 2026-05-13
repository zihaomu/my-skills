# ROCm Portability

## Porting Checklist

- Replace CUDA runtime APIs with HIP equivalents and verify semantic differences.
- Remove inline PTX or isolate it behind backend-specific paths.
- Audit warp-size assumptions.
- Check library calls: cuBLAS/cuDNN/NCCL/CUTLASS paths may need rocBLAS/MIOpen/RCCL
  or framework-level alternatives.
- Verify stream, event, graph, and memory-management behavior on ROCm.
- Confirm build flags and target architectures.

## Manual Review After Hipify

Hipify handles many syntactic conversions, but manual work remains:

- Unsupported APIs or libraries.
- Performance assumptions tuned for NVIDIA hardware.
- Inline assembly and vendor intrinsics.
- Different compiler diagnostics or template instantiation behavior.
- Tests that skip AMD by accident.

## Performance Portability

Performance portability is a separate goal from source portability. A working HIP
kernel can still be slow because tile sizes, wave behavior, LDS use, or memory
coalescing differ from the original CUDA assumptions.

