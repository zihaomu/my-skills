# my-skills

Personal Codex skills for high-performance LLM systems work.

This repository is intentionally narrow. It captures durable engineering
knowledge for end-to-end LLM serving optimization, GPU kernel optimization,
AMD ROCm/HIP development, Triton/TileLang work, and upstream code review.

It has two layers:

- Domain skills: specialized high-performance LLM systems knowledge.
- Workflow skills: explicit, reusable engineering processes adapted from the
  useful parts of gstack without importing its broad role system or runtime
  machinery.

## Layout

```text
skills/
  <skill-name>/
    SKILL.md
    references/
    agents/openai.yaml
knowledge/
  inbox/
  candidates/
  handoffs/
  archive/
scripts/
  install
  validate-skills
  capture-learning
  search-learning
```

## Install

```bash
./scripts/install
```

By default this symlinks each skill under `${CODEX_HOME:-$HOME/.codex}/skills`.
Use `./scripts/install --copy` if you want a detached copy on a machine.

## Knowledge Flow

1. Capture raw learnings into `knowledge/inbox/`.
2. Promote only reusable, sourced, version-bounded items into `knowledge/candidates/`.
3. Curate stable material into a skill reference file.
4. Archive superseded or one-off notes in `knowledge/archive/`.

Run validation before committing:

```bash
./scripts/validate-skills
```

## Skills

Domain skills:

- `perf-debug`
- `kernel-review`
- `rocm-hip`
- `llm-e2e`
- `upstream-review`
- `curator`

Workflow skills:

- `root-cause`
- `pr-review`
- `plan-review`
- `handoff`
- `red-team`

Workflow skills are intentionally configured for explicit invocation in their
`agents/openai.yaml` metadata. Use them when you want the workflow, while domain
skills carry the specialist knowledge.
