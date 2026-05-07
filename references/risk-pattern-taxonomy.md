# Risk Pattern Taxonomy

Use these categories to group assessment findings across repositories.

## Architecture and Boundaries

- `controller-business-logic`
- `controller-owned-serialization`
- `service-responsibility-collapse`
- `god-service-or-listener`
- `collapsed-processing-layer`
- `framework-bypass`
- `custom-lifecycle-management`

## Domain and Design

- `anemic-domain-model`
- `behavior-displaced-to-service`
- `externalized-validation`
- `missing-invariant-enforcement`
- `manual-copy-pipeline`
- `stringly-typed-rules`
- `mutable-data-bag`

## Reliability and Operations

- `weak-error-semantics`
- `swallowed-exception`
- `silent-default`
- `http-200-for-error`
- `lost-root-cause`
- `message-processing-reliability-gap`
- `missing-dlq-semantics`
- `idempotency-gap`
- `static-mutable-state`
- `thread-safety-risk`

## Testability

- `field-injection`
- `reflection-based-tests`
- `private-method-testing`
- `static-context-coupling`
- `new-collaborator-inside-method`
- `tests-compensating-for-design`
- `test-platform-mismatch`
- `shallow-core-path-coverage`

## Complexity and Tooling

- `complexity-suppression`
- `broad-quality-exclusions`
- `dead-code-or-commented-code`
- `duplicated-business-logic`
- `runtime-interpreter`
- `type-system-bypass`
- `threadlocal-hidden-state`

## How to Use the Taxonomy

Group findings by pattern and consequence.

For example:

- `silent exception swallowing`, `null returns on exception paths`, and `HTTP 200 returned for errors` should likely roll up into `weak-error-semantics`.
- `anemic model`, `external validation`, and `helper methods reading like domain behavior` should likely roll up into `domain modeling and invariant enforcement`.
- `field injection`, `ReflectionTestUtils`, and collaborators created with `new` inside methods should likely roll up into `design-for-testability`.
