# CI Matrix

For AMD work, tests should make backend support explicit.

## Matrix Dimensions

- ROCm version or container tag.
- GPU target, when available.
- Python and framework version.
- Build mode: source build, wheel, editable install, container.
- Test category: unit, integration, kernel correctness, benchmark smoke.

## Minimum For Upstream PRs

- One correctness path on AMD.
- One path proving existing CUDA/CPU behavior is unchanged, when the repo
  supports those backends.
- A skip reason for unsupported hardware or missing CI capacity.
- A manual validation section if public CI cannot run AMD hardware.

## Perf CI

Use perf CI sparingly. Prefer stable smoke thresholds and store raw numbers in
the PR body or artifact. Avoid strict thresholds on noisy shared machines unless
the environment is controlled.

