# Template Sources

Last verified: 2026-05-13.

This repository borrows structure, not content, from current public skill
templates.

## Structural Rules

- Codex skills are directories with `SKILL.md` plus optional `scripts/`,
  `references/`, `assets/`, and `agents/openai.yaml`.
- Keep `name` and `description` concise because they are used for skill
  selection before the full skill is read.
- Put detailed and version-sensitive material in `references/` so it is loaded
  only when needed.
- Do not put README files inside individual skill folders.

## Reference Links

- OpenAI Codex skills docs: https://developers.openai.com/codex/skills
- OpenAI skills catalog: https://github.com/openai/skills
- Agent Skills open standard: https://agentskills.io/
- Claude Code skills docs: https://code.claude.com/docs/en/skills
- gstack repository: https://github.com/garrytan/gstack

## Local Policy

Do not vendor gstack. Use only these patterns:

- Evidence-first investigation.
- Review checklists with explicit output formats.
- Learning capture with promotion gates.
- Progressive disclosure via references.

