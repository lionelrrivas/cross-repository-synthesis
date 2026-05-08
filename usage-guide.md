# Usage Guide

## What this guide helps you do

Use this guide when you want to turn a set of repository assessment reports into a practical synthesis package that supports:

- engineering standards drafting
- team learning plans
- repository-specific remediation planning
- executive communication about recurring engineering risks

This workflow is especially useful when detailed repo reviews already exist, but the organization still needs a clear answer to: **what is systemic, what is teachable, and what should stay local?**

## Enablement guardrails

Use this workflow for engineering support and improvement, not for judging people.

Do **not** use the outputs to:

- grade engineers
- rank teams
- make performance arguments about individual developers
- treat repository findings as proof of someone's capability or lack of capability

Repository assessments and synthesis outputs are engineering evidence, not HR artifacts. They should help teams decide where standards, examples, coaching, and targeted remediation would reduce risk and improve delivery.

## When to use this workflow

Use the skill when:

- you have multiple repository assessment reports to compare
- you want standards to be grounded in repeated evidence, not opinion
- you need a portfolio-level view of engineering patterns
- you want outputs that are teachable, reviewable, and easier to socialize

If you only need a lightweight standard for one obvious issue in one codebase, drafting it directly may be faster.

## Input structure

```text
cross-repository-synthesis/
  assessments/
    repo-one-assessment.md
    repo-two-assessment.md
    repo-three-assessment.md
```

## Input requirements

Each non-empty assessment report should include a `Synthesis Input Summary` section.

That summary is the normalized starting point for the synthesis. The skill uses it as the primary source, then validates it against the rest of the report.

If a report is non-empty but missing that section, fix the report first instead of asking the skill to infer the missing structure.

## Prompt options

### Basic prompt

```text
Use the cross-repository engineering synthesis skill to synthesize the reports in the assessments directory. Produce the full synthesis package.
```

### Preferred prompt

```text
Use the cross-repository engineering synthesis skill. Every assessment in the assessments directory includes a Synthesis Input Summary section. Use that summary as the primary source, validate it against the rest of each report, then produce the synthesis, standards candidates, learning recommendations, remediation candidates, and executive summary.
```

## What the skill produces

The synthesis package includes:

1. `normalized-assessment-summaries.md`
2. `cross-repository-engineering-findings-synthesis.md`
3. `engineering-standards-candidates.md`
4. `learning-recommendations.md`
5. `repository-remediation-candidates.md`
6. `synthesis-executive-summary.md`

## A small example

Here is a realistic small first pass:

- input: 3 repository assessments
- recurring pattern: domain logic spread across services in 2 repositories
- recurring pattern: tests that miss important behavior in 2 repositories
- isolated issue: one severe batch-processing failure mode in 1 repository

Likely output:

1. 2 standards candidates
2. 1 learning recommendation
3. 1 repository-specific remediation item
4. 1 executive summary for leadership

This is the intended shape of the workflow: reduce many repo-level findings into a smaller set of actions that are easier to review, teach, and prioritize.

## Recommended review sequence

1. Review `normalized-assessment-summaries.md` first.
2. Confirm repository names, ratings, top risks, and extracted pattern tags.
3. Review `cross-repository-engineering-findings-synthesis.md`.
4. Review `engineering-standards-candidates.md`, especially the problem, expectation, and code-example plan for each candidate.
5. Review `learning-recommendations.md`, especially the before/after examples and suggested learning formats.
6. Review `repository-remediation-candidates.md` to keep local cleanup separate from org-wide standards.
7. Review `synthesis-executive-summary.md` for leadership framing.
8. Only then draft final engineering standards.

## Why the synthesis step matters

Do not jump directly from raw assessments to final standards.

The synthesis step is what prevents:

- isolated findings from becoming team-wide rules
- systemic issues from being dismissed as repo-local quirks
- skill gaps from being mislabeled as governance problems
- one-off cleanup from polluting the standards backlog

In practice, this is the step that makes the whole process feel smaller and more manageable, not larger.

It also helps keep the conversation pointed at system improvement instead of individual blame. Repeated patterns should lead to better guidance and better support, not harsher judgments about the people working in the codebase.

## How to keep the scope sane

If you worry that this process feels too heavy, use these constraints:

1. Start with the highest-priority standards candidates only.
2. Promote a pattern to a standard only when it is recurring and consequential.
3. Turn skill gaps into learning recommendations instead of standards whenever teaching is the better intervention.
4. Keep repository-specific problems in remediation candidates unless there is strong cross-repository evidence.
5. Treat watch items as inputs for later review, not as immediate work.

This keeps the output focused on the few changes most likely to improve engineering quality across the portfolio.

## Start small adoption pattern

If this is your first time using the workflow, do not start with every assessment you have.

Use this rollout pattern instead:

1. Start with 3-5 assessments that are reasonably complete and comparable.
2. Run the synthesis once as a calibration exercise.
3. Promote only 1-3 high-confidence standards candidates into active drafting.
4. Leave the rest as learning recommendations, remediation items, or watch items.
5. Review whether the output feels evidence-backed, teachable, and narrow enough to act on.
6. Only then expand to a larger portfolio slice.

This approach reduces churn, keeps review manageable, and builds trust in the workflow before you scale it up.

## Code example review

When reviewing standards candidates, check whether each candidate includes a clear example plan:

- Is the fictional domain relatable to the team?
- Does the problem example make the risk obvious?
- Does the preferred example show a practical improvement rather than an idealized rewrite?
- Does the testing example show why the preferred design is easier to verify?
- Is the example free of proprietary repository code?

When reviewing learning recommendations, confirm that each recommendation includes a concise before/after example that makes the skill gap teachable.

## Frequently asked questions

### Why use this tool to create engineering standards?

Because standards are hard to defend when they are derived directly from one repo, one incident, or one reviewer preference.

This workflow creates a stronger chain from evidence to action. It helps teams standardize the patterns that actually recur, while keeping training needs and local cleanup in the right lanes.

### Isn't there a simpler way to create engineering standards?

Yes: if your scope is small, write the standard directly.

But once you already have multiple assessments, manual comparison is usually the more complicated path. This workflow is the simpler way to turn a pile of diagnostics into a prioritized, reviewable standards backlog.

### Is this overkill for a small team?

It can be, depending on the input.

If the team has only one repo or one obvious engineering problem, go direct. If the team has multiple services, multiple reviewers, or recurring design and reliability concerns across repos, the synthesis step quickly pays for itself.

### Do I need to adopt every standards candidate?

No. The point is to create a high-quality candidate set, not a giant policy dump.

Most teams should start with a small number of high-leverage candidates and leave the rest for later review.

### Can I use this to grade engineers or compare teams?

No.

That would be the wrong use of the workflow. The synthesis package is meant to support engineering enablement: better standards, better teaching material, and better prioritization. It is not designed to measure individual skill or serve as a performance-management tool.

### Can I use this even if I am not ready to publish standards?

Yes. The outputs are still useful for leadership briefings, training plans, and remediation prioritization even before any formal standards are approved.

### What is the biggest mistake to avoid?

Treating assessment reports as if they were already standards.

Assessment reports diagnose. The synthesis classifies. Final standards come after that.
