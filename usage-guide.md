# Usage Guide

Use this guide when you are ready to run the workflow, review the output, and decide what to publish first.

For higher-level positioning and trust questions, see [`README.md`](README.md).

## Before you run

Confirm that:

- you have multiple completed repository assessment reports
- each non-empty report includes `Synthesis Input Summary`
- the reports are reasonably comparable in scope and depth
- major findings are tied to evidence rather than broad impressions
- placeholder or obviously unfinished reports are excluded

If a non-empty report is missing `Synthesis Input Summary`, fix the report first instead of asking the skill to infer the missing structure.

## Input structure

```text
cross-repository-synthesis/
  assessments/
    repo-one-assessment.md
    repo-two-assessment.md
    repo-three-assessment.md
```

## Recommended prompt

```text
Use the cross-repository engineering synthesis skill. Every assessment in the assessments directory includes a Synthesis Input Summary section. Use that summary as the primary source, validate it against the rest of each report, then produce the synthesis, standards candidates, learning recommendations, remediation candidates, and executive summary.
```

## Output files

The synthesis package includes:

1. `normalized-assessment-summaries.md`
2. `cross-repository-engineering-findings-synthesis.md`
3. `engineering-standards-candidates.md`
4. `learning-recommendations.md`
5. `repository-remediation-candidates.md`
6. `synthesis-executive-summary.md`

## Recommended review order

1. Review `normalized-assessment-summaries.md` first.
2. Confirm repository names, ratings, top risks, and extracted pattern tags.
3. Review `cross-repository-engineering-findings-synthesis.md`.
4. Review `engineering-standards-candidates.md`.
5. Review `learning-recommendations.md`.
6. Review `repository-remediation-candidates.md`.
7. Review `synthesis-executive-summary.md`.
8. Only then draft final engineering standards.

## What to check during review

Use this checklist:

- **Evidence quality:** major conclusions trace back to repeated findings in the assessments
- **Classification quality:** standards candidates, learning recommendations, remediation items, and watch items feel like the right buckets
- **Scope discipline:** the proposed standards set is narrow enough to act on
- **Teaching value:** standards candidates and learning recommendations include examples that would actually help a team improve
- **Tone:** the package reads as supportive and actionable rather than punitive
- **Leadership framing:** the executive summary stays calm, practical, and free of blame

When reviewing standards candidates, check that each one includes a clear code-example plan:

- a recognizable problem example
- a practical preferred example
- a testing example that shows why the preferred design is easier to verify

When reviewing learning recommendations, check that each one includes a concise before/after example that makes the skill gap teachable.

## First-run scope rules

Treat the first synthesis as a calibration exercise, not a mandate to standardize everything.

Use these constraints:

1. Start with 3-5 assessment reports.
2. Promote only 1-3 high-confidence standards candidates into active drafting.
3. Turn skill gaps into learning recommendations when teaching is the better intervention.
4. Keep repository-specific problems in remediation candidates unless there is strong cross-repository evidence.
5. Leave weak signals as watch items for later review.

This keeps the output focused on the few changes most likely to improve engineering quality across the portfolio.

## Publishing guidance

Start by publishing a **small number of high-confidence standards**, not the whole synthesis package as if every output belongs in the same lane.

A good default sequence is:

1. Publish standards first when the pattern is recurring, consequential, and clear enough to become a practical team expectation.
2. Publish learning recommendations alongside those standards when teams will need examples, coaching, workshops, or guided practice to apply them well.
3. Keep remediation work primarily local to the affected repositories unless leadership needs visibility into a severe or high-risk issue.

In practice, that usually means:

- publish only the top 1-3 standards candidates from an initial synthesis
- pair each standard with learning support when the skill gap is likely to block adoption
- keep repository-specific remediation in team backlogs, not in the published standards set

## If the output feels wrong

Usually the problem is one of these:

- **Too many standards candidates:** narrow the set to the most repeated and consequential patterns.
- **Weak evidence:** downgrade the item to a watch item or local remediation.
- **Abstract guidance:** improve the examples before treating the item as publishable.
- **Punitive tone:** rewrite toward support, coaching, and practical expectations.
- **Mixed lanes:** separate standards, learning recommendations, and remediation more aggressively.

## What good adoption looks like

Over time, you should see:

- fewer recurring cross-repository issues in later assessments
- clearer and more teachable standards candidates
- more consistent language in reviews and design discussions
- more problems addressed through examples, coaching, and learning support before they become standards issues

The goal is not to publish everything. The goal is to publish the smallest set of guidance that creates the most useful improvement.
