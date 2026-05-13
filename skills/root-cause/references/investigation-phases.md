# Investigation Phases

## 1. Frame

- What changed?
- What is the user-visible failure?
- What would success look like?
- Is this deterministic, intermittent, environment-specific, or data-specific?

## 2. Reproduce

Prefer a command, test, request, or minimal script that fails on demand. If
reproduction is impossible, gather logs and state what evidence is missing.

## 3. Trace

Follow the execution path from symptom to likely cause:

- Entry point.
- State/data transformation.
- External calls.
- Concurrency or async boundary.
- Error handling.
- Output path.

## 4. Hypothesize

Use one hypothesis at a time:

```text
Hypothesis: <specific cause>
Evidence for:
Evidence against:
Next check:
Expected result if true:
Expected result if false:
```

## 5. Fix And Verify

After confirmation:

- Apply the smallest root-cause fix.
- Add or update a regression test.
- Re-run the failing scenario.
- Run nearby tests or the repo's standard test command.

