# Hypothesis Log

Use a log when an investigation has more than one plausible cause.

```markdown
## Hypotheses

| # | Hypothesis | Evidence | Test | Result | Status |
| --- | --- | --- | --- | --- | --- |
| 1 |  |  |  |  | open |
```

Statuses:

- `open`: not tested yet.
- `supported`: evidence points toward it.
- `rejected`: direct evidence disproves it.
- `confirmed`: enough evidence to justify a fix.

## Failed Attempts

Record failed attempts only when they prevent repeat work:

```markdown
- Tried <action>; result was <result>; this rules out <hypothesis>.
```

Do not log noise, guesses, or one-time command failures.

