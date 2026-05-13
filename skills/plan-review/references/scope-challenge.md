# Scope Challenge

Answer these before endorsing a plan:

- What existing code already solves part of the problem?
- What is the minimum change that achieves the goal?
- Which pieces are required now versus deferrable?
- Is the plan mixing structural refactor and behavior change?
- Does the plan introduce new infrastructure when an existing primitive would
  work?
- What would be removed if the deadline were tomorrow?

## Smells

- More new abstractions than new behavior.
- Parallel implementation of an existing mechanism.
- No explicit owner for tests, CI, docs, or rollout.
- Ambiguous success metric.
- Performance claim without a benchmark plan.

