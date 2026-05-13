# Learning Schema

Raw learnings are JSONL records under `knowledge/inbox/`.

## Fields

Required:

- `ts`: ISO-8601 timestamp.
- `domain`: one of `perf`, `kernel`, `rocm-hip`, `llm-e2e`, `upstream`,
  `workflow`.
- `type`: one of `pattern`, `pitfall`, `preference`, `architecture`,
  `tool`, `benchmark`, `investigation`, `review`.
- `key`: kebab-case identifier.
- `insight`: one sentence.
- `source`: one of `user-stated`, `observed`, `benchmark`, `upstream-doc`,
  `pr-review`, `inferred`.

Recommended:

- `confidence`: integer 1-10.
- `frameworks`: list such as `["rocm", "hip", "triton", "vllm"]`.
- `hardware`: list such as `["mi300x", "gfx942"]`.
- `versions`: list of relevant versions or commits.
- `files`: relevant local or upstream files.
- `last_verified`: date in `YYYY-MM-DD` format.
- `promotion`: `inbox`, `candidate`, `promoted`, `archived`.

## Example

```json
{"ts":"2026-05-13T08:00:00Z","domain":"kernel","type":"pitfall","key":"warp-size-assumption","insight":"Do not assume warp size 32 in HIP kernels targeting AMD wavefront execution; make the assumption explicit or query the backend.","source":"user-stated","confidence":9,"frameworks":["hip"],"hardware":["amd-gpu"],"last_verified":"2026-05-13","promotion":"inbox"}
```
