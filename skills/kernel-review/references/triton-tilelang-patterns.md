# Triton And TileLang Patterns

## Triton Review

- Confirm `BLOCK_*` sizes match the memory layout and target backend.
- Check masks on every load/store that can cross shape boundaries.
- Validate pointer arithmetic with strides, especially non-contiguous tensors.
- Inspect generated code or compiler diagnostics when performance is surprising.
- Do not assume a CUDA-tuned tile is good on AMD.

## TileLang Review

- Make tile layout, memory hierarchy, and synchronization explicit.
- Validate how the schedule maps to target hardware.
- Keep transformations traceable to the original mathematical operation.
- Confirm generated kernels have the intended boundary behavior.

## Common Footguns

- Over-large tiles that reduce occupancy more than they improve reuse.
- Masked loads that hide excessive out-of-bound work.
- Benchmarking only power-of-two or perfectly aligned shapes.
- Missing numerical tolerance tests after changing accumulation order.
- Framework fallback path silently replacing the custom kernel.

