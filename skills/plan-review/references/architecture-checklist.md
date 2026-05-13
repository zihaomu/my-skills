# Architecture Checklist

## Boundaries

- Are component responsibilities clear?
- Is data ownership explicit?
- Are dependencies directional and understandable?
- Are public APIs stable or intentionally changed?

## Data Flow

Prefer a compact ASCII diagram when the flow is nontrivial:

```text
input -> scheduler -> execution path -> output
              |              |
              v              v
          state/cache     metrics/logs
```

## Complexity

- Is the plan under-engineered for known edge cases?
- Is it over-engineered for speculative future needs?
- Can each component be tested independently?
- What breaks if one dependency is slow, unavailable, or inconsistent?

