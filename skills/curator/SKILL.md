---
name: curator
description: Convert historical engineering experience into clean personal skills. Use when capturing learnings, pruning stale knowledge, promoting notes into skill references, or keeping this my-skills repository pure and portable. Do not use for ordinary coding tasks.
---

# Knowledge Curator

Use this skill to maintain this repository as a portable, high-signal engineering
memory. The job is curation, not accumulation.

## Workflow

1. Capture raw notes into `knowledge/inbox/` with `scripts/capture-learning`.
2. Read [references/learning-schema.md](references/learning-schema.md) before
   editing JSONL learning records.
3. Apply [references/promotion-rules.md](references/promotion-rules.md) before
   promoting anything into a skill.
4. Use [references/capture-workflow.md](references/capture-workflow.md) for
   recurring ingestion from chat history, PR reviews, benchmark logs, and
   postmortems.
5. Use [references/template-sources.md](references/template-sources.md) when
   changing repository structure or skill packaging conventions.
6. Keep `SKILL.md` files concise; put detailed domain knowledge in
   `references/`.
7. Run `scripts/validate-skills` before finishing.

## Curation Policy

- Prefer fewer, sharper skills over broad collections.
- Promote only reusable engineering judgment with source and boundaries.
- Keep framework/version-sensitive claims marked with `last_verified`.
- Archive one-off facts instead of loading them into skill context.
- Do not import gstack wholesale; borrow workflow patterns only.

## Output

When curating, report:

- Accepted learnings and destination files.
- Rejected or archived items with reasons.
- Stale or contradictory knowledge found.
- Validation status.
