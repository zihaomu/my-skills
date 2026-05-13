# Debug Report

Use this format at the end of a root-cause investigation.

```markdown
## Debug Report

Symptom:
Root cause:
Fix:
Evidence:
Regression test:
Verification commands:
Residual risk:
Status: DONE | DONE_WITH_CONCERNS | BLOCKED
```

## Status Definitions

- `DONE`: root cause confirmed, fix applied, verification passed.
- `DONE_WITH_CONCERNS`: root cause likely and fix applied, but some verification
  requires external data, staging, hardware, or time.
- `BLOCKED`: evidence is insufficient or reproduction is unavailable.

