# Risk Taxonomy

## Severity

- `CRITICAL`: data loss, security issue, correctness break, crash, or likely
  production outage.
- `HIGH`: real bug or compatibility regression with clear user impact.
- `MEDIUM`: missing edge case, test gap, maintainability issue, or operational
  risk.
- `LOW`: clarity or cleanup that improves review quality but is not blocking.

## Confidence

Use confidence when evidence is incomplete:

- `High`: directly proven by code or test behavior.
- `Medium`: strong pattern with supporting code evidence.
- `Low`: plausible but needs confirmation; do not present as fact.

Suppress low-confidence items from blockers unless the blast radius is severe.

