# Challenge Rubric

Ask:

- What must be true for this plan to work?
- Which assumption has the highest blast radius if wrong?
- What evidence is missing?
- What simpler alternative was not considered?
- What does this optimize at the expense of?
- What would fail first under scale, concurrency, unusual input, or unsupported
  backend?
- What would a maintainer, SRE, or future debugger object to?

## Confidence

Label every challenge:

- `Confirmed`: directly supported by code, tests, benchmark, or docs.
- `Likely`: strong evidence but not fully proven.
- `Speculative`: worth checking, not a finding.

