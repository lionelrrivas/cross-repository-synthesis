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

## Preferred Prompt for Legacy Reports

```text
Use the cross-repository engineering synthesis skill. The reports are legacy-format repository assessments and may not include the Synthesis Input Summary section. Normalize them first, then produce the synthesis, standards candidates, learning recommendations, remediation candidates, and executive summary.
```

## Preferred Prompt for Mixed Reports

```text
Use the cross-repository engineering synthesis skill. Some reports include the Synthesis Input Summary section and some are legacy reports. Use the summary section when present, infer equivalent normalized fields from the narrative when absent, and mark normalization confidence for each repository.
```

## Recommended Review Sequence

1. Review `normalized-assessment-summaries.md` first.
2. Confirm repository names, ratings, and extracted risk patterns.
3. Review `cross-repository-engineering-findings-synthesis.md`.
4. Review `engineering-standards-candidates.md`, especially the code-example readiness and example plans.
5. Review `learning-recommendations.md`.
6. Only then draft final engineering standards.

## Do Not Skip the Synthesis Step

Do not jump directly from assessment reports to final standards. The synthesis step prevents overreacting to isolated findings and helps the team focus on recurring, high-value improvements.


## Code Example Review

When reviewing standards candidates, check whether each high-priority candidate includes a clear example plan:

- Is the fictional domain relatable to the team?
- Does the problem example show the risk clearly?
- Does the preferred example demonstrate the standard without over-engineering?
- Does the testing example show why the preferred design is easier to verify?
- Is the example free of proprietary repository code?
