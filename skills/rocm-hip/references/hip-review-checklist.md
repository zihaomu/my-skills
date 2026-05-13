# HIP Review Checklist

## Build

- Confirm ROCm version and compiler.
- Confirm target gfx architectures.
- Check build system paths for hardcoded CUDA assumptions.
- Verify feature guards are narrow and readable.

## Runtime

- Check stream and event ordering.
- Check graph capture support before using it.
- Confirm memory allocation and peer access behavior.
- Validate error handling after async operations.

## Framework Integration

- Ensure dispatch tables include AMD where appropriate.
- Confirm tests are not skipped by backend name.
- Verify fallback behavior is intentional and visible.
- Check packaging/container changes for ROCm dependencies.

## Documentation

Document:

- Supported ROCm versions or tested version range.
- Supported GPU targets.
- Known limitations.
- Required environment variables, if any.

