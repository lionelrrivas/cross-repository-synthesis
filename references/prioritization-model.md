# Prioritization Model

Prioritize themes using four dimensions.

## 1. Recurrence

- **High:** appears across many repositories or archetypes
- **Medium:** appears across several repositories or one important archetype family
- **Low:** appears in one or two repositories

## 2. Consequence

- **High:** can affect correctness, data integrity, duplicate processing, lost messages, security, production diagnosis, or customer/user outcomes
- **Medium:** primarily affects maintainability, delivery speed, or test confidence
- **Low:** mostly local readability or cleanup

## 3. Evidence Strength

- **High:** concrete classes, methods, build files, tests, and repeated examples
- **Medium:** clear pattern but limited examples
- **Low:** plausible inference with incomplete evidence

## 4. Learning Leverage

- **High:** improving this skill would help many future stories or repositories
- **Medium:** useful for a subset of work
- **Low:** narrow technical cleanup

## Recommendation Rules

| Pattern | Recommendation |
|---|---|
| High recurrence + high consequence | Draft standard first |
| High recurrence + medium consequence + high learning leverage | Create standard plus learning recommendation |
| Medium recurrence + high consequence | Include as standards candidate or targeted remediation, depending on scope |
| Low recurrence + high consequence | Repository-specific remediation |
| High recurrence + low consequence | Learning recommendation or code review guidance, not necessarily a formal standard |
| Low recurrence + low consequence | Watch item or local cleanup |

## Avoid Over-Standardizing

A finding should not become a formal standard merely because it is interesting or technically correct. A good standard should be recurring, consequential, teachable, and actionable.
