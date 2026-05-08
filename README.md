# Cross-Repository Engineering Synthesis Skill

This skill synthesizes multiple repository assessment reports into engineering findings, standards candidates, and learning recommendations.

It expects repository assessment reports that include a `Synthesis Input Summary` section.

## Recommended Use

Place assessment reports in an `assessments/` directory, then run the skill to produce:

- cross-repository engineering findings synthesis
- normalized per-repository summaries
- engineering standards candidates with required code examples
- learning recommendations with before/after code examples
- repository-specific remediation candidates
- executive summary

## Important Framing

Repository assessment reports are diagnostic evidence. They are not engineering standards and should not be treated as a performance review.

The synthesis step exists to decide which findings should become practical standards, learning recommendations, targeted remediation items, or watch items.

## Why This Skill Exists

Raw assessment reports are intentionally detailed. They help reviewers see design, architecture, reliability, testability, and complexity issues in context. That level of detail is useful for diagnosis but too much for team-wide standards.

This skill creates the bridge between detailed diagnosis and practical team guidance.
