# Normalization Rules

## Required Summary Section

Every usable assessment report must contain `## Synthesis Input Summary`.

Use that section as the primary input for normalization.

Still verify consistency with:

- repository context
- dimension assessments
- top recurring engineering risk patterns
- likely skill or standards gaps
- candidate engineering standards

If the summary conflicts with the narrative, prefer the detailed assessment and call out the inconsistency.

If a non-empty report is missing that section, stop and tell the user the report is incompatible with this skill's required input format. Do not backfill a summary from narrative-only sections.

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
