# Standards Writing Guidance

## Standards Should Be Practical

A useful engineering standard should answer:

- What should developers do?
- Why does it matter?
- How can reviewers recognize compliance?
- What are acceptable exceptions?
- What examples help the team understand the difference?

## Recommended Standard Shape

Use this shape:

1. **Expectation**: the practical rule
2. **Reason**: why the rule exists
3. **Applies to**: contexts where the rule matters
4. **Avoid**: common problematic patterns
5. **Prefer**: better implementation direction
6. **Review checks**: what to look for during PR review
7. **Exceptions**: when deviation is acceptable
8. **Code examples**: problem example, preferred example, and testing example
9. **Learning support**: examples, workshop, or kata

## Tone

Prefer:

- "Prefer constructor injection for Spring-managed collaborators."
- "Domain types should enforce their own invariants when the rule belongs to the concept."
- "Message consumers should have explicit retry, dead-letter, and idempotency semantics where duplicate or lost processing has business impact."

Avoid:

- "Never write bad services."
- "All domain objects must be records."
- "Controllers cannot contain any logic."
- "Developers must stop writing procedural code."

## Good Standards Are Not Slogans

Avoid standards that are too broad to apply during code review, such as:

- "Write clean code"
- "Use SOLID"
- "Avoid complexity"
- "Use good architecture"

Turn them into concrete expectations instead.


## Code Example Guidance

Each final standard should be teachable through code. Prefer examples that are fictional but familiar to the team.

Use three example types for every standard:

1. **Problem example**: demonstrates the common failure mode in a small, recognizable snippet.
2. **Preferred example**: demonstrates the expected implementation direction.
3. **Testing example**: demonstrates how the preferred design becomes easier to verify.

The examples do not need to come from assessed repositories. In most cases, they should not. Fictional examples reduce defensiveness, avoid exposing internal code, and make the teaching point easier to isolate.

Good examples should:

- reflect the team's likely stack, such as Java, Spring Boot, JUnit, Spock, Kafka, REST controllers, services, repositories, or domain types
- teach one standard at a time
- avoid becoming a full application
- show the consequence of the standard, not just cleaner formatting
- make code review expectations visible

Avoid examples that:

- copy proprietary code from a repository assessment
- name real teams or developers
- depend on too much omitted context
- combine multiple standards into one confusing example
- present a framework preference as a universal rule without context
