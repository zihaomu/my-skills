# Failure Modes

For each important path, ask:

- What happens if input is malformed?
- What happens if the dependency is slow or unavailable?
- What happens under high concurrency or memory pressure?
- What happens on unsupported hardware/backend/version?
- How does rollback work?
- How will the team detect the failure?

## Rollout

Prefer plans that include:

- Feature flag or guarded path when risk is high.
- Compatibility strategy.
- Migration path.
- Metrics and logs.
- Rollback command or revert plan.

