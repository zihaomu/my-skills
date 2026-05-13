# Capture Workflow

## From A Conversation

1. Extract only reusable engineering judgment.
2. Record source as `user-stated` if the user explicitly said it.
3. Record source as `observed` only if the session produced evidence.
4. Put uncertain claims in inbox with lower confidence; do not promote them.

## From A PR Review

Capture:

- Repeated maintainer feedback.
- Backend compatibility pitfalls.
- Tests that maintainers required.
- Benchmark evidence that changed the decision.

Do not capture:

- File-specific TODOs.
- Transient CI failures.
- Review style preferences unrelated to engineering correctness.

## From Benchmark Logs

Capture only the protocol or generalizable conclusion. Keep raw logs outside the
skill unless they are small and directly useful.

## Commands

```bash
./scripts/capture-learning \
  --domain kernel \
  --type pitfall \
  --key warp-size-assumption \
  --source user-stated \
  --confidence 9 \
  --framework hip \
  --hardware amd-gpu \
  --insight "Do not assume warp size 32 in HIP kernels targeting AMD wavefront execution."
```

```bash
./scripts/search-learning warp-size
```

