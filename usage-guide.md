# Usage Guide

## Input Structure

```text
cross-repository-synthesis/
  assessments/
    repo-one-assessment.md
    repo-two-assessment.md
    repo-three-assessment.md
```

## Basic Prompt

```text
Use the cross-repository engineering synthesis skill to synthesize the reports in the assessments directory. Produce the full synthesis package.
```

## Preferred Prompt

```text
Use the cross-repository engineering synthesis skill. Every assessment in the assessments directory includes a Synthesis Input Summary section. Use that summary as the primary source, validate it against the rest of each report, then produce the synthesis, standards candidates, learning recommendations, remediation candidates, and executive summary.
```

## Recommended Review Sequence

1. Review `normalized-assessment-summaries.md` first.
2. Confirm repository names, ratings, and extracted risk patterns.
3. Review `cross-repository-engineering-findings-synthesis.md`.
4. Review `engineering-standards-candidates.md`, especially the required code examples and example plans.
5. Review `learning-recommendations.md`, especially the before/after code examples.
6. Only then draft final engineering standards.

## Do Not Skip the Synthesis Step

Do not jump directly from assessment reports to final standards. The synthesis step prevents overreacting to isolated findings and helps the team focus on recurring, high-value improvements.


## Code Example Review

When reviewing standards candidates, check whether each candidate includes a clear example plan:

- Is the fictional domain relatable to the team?
- Does the problem example show the risk clearly?
- Does the preferred example demonstrate the standard without over-engineering?
- Does the testing example show why the preferred design is easier to verify?
- Is the example free of proprietary repository code?

When reviewing learning recommendations, also check whether each recommendation includes a concise before/after example that makes the skill gap easy to teach.
