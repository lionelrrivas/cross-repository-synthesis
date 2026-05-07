# Normalization Rules

## Current-Format Reports

When a report contains `## Synthesis Input Summary`, use that section as the primary input.

Still verify consistency with:

- repository context
- dimension assessments
- top recurring engineering risk patterns
- likely skill or standards gaps
- candidate engineering standards

If the summary conflicts with the narrative, prefer the detailed assessment and call out the inconsistency.

## Legacy-Format Reports

When a report does not contain a `Synthesis Input Summary`, infer the normalized summary from these sections:

1. `Repository Context`
2. `Dimension Assessments`
3. `Top Recurring Engineering Risk Patterns`
4. `Likely Underlying Skill or Standards Gaps`
5. `Recommended Candidate Examples for Engineering Standards`
6. `Final Notes`

## Normalization Confidence

Use `High` when:

- all dimension ratings are present
- top risk patterns are explicit
- skill gaps and standard candidates are present
- evidence is concrete

Use `Medium` when:

- dimension ratings are present
- risk patterns are present
- some standard or learning signals must be inferred

Use `Low` when:

- report sections are missing
- evidence is vague
- ratings or repository identity are incomplete

## Risk Tagging Guidance

Risk tags should describe the engineering pattern, not the exact wording in one report.

Prefer:

- `anemic-domain-model`
- `behavior-displaced-to-service`
- `controller-business-logic`
- `god-service-or-listener`
- `weak-error-semantics`
- `swallowed-exception`
- `field-injection`
- `reflection-based-tests`
- `static-mutable-state`
- `runtime-interpreter`
- `type-system-bypass`
- `manual-copy-pipeline`
- `broad-quality-exclusions`
- `complexity-suppression`
- `message-processing-reliability-gap`
- `idempotency-gap`

Avoid overly specific tags such as class names unless the issue is truly unique.
