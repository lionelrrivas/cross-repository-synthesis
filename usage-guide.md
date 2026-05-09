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

## When not to use this workflow

Do not use this workflow when:

- you need a fresh assessment of source code instead of synthesis of completed assessments
- you only have a single repo issue that is already clear and actionable
- the assessment set is too uneven to compare fairly
- the real goal is personnel evaluation, team comparison, or performance management

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

## Input quality checklist

Before you run the workflow, confirm:

- each non-empty report includes `Synthesis Input Summary`
- the reports are complete enough to support comparison
- findings are tied to evidence, not vague impressions
- placeholder files and obviously unfinished reports are excluded
- the review scope is reasonably comparable across repositories
- the assessment set is large enough to distinguish recurring patterns from one-off issues

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

## How to review a first synthesis

Treat the first synthesis like a calibration exercise, not a final answer.

Use this review pass to check:

1. **Evidence quality:** are the major conclusions traceable to repeated findings in the assessments?
2. **Classification quality:** do standards candidates, learning recommendations, remediation items, and watch items feel like the right buckets?
3. **Scope discipline:** is the proposed standards set narrow enough to act on, or is it turning into a giant backlog?
4. **Teaching value:** do the standards candidates and learning recommendations include examples that would actually help a team improve?
5. **Tone:** does the package read as supportive and actionable rather than punitive or compliance-driven?

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

## How to tell if the output is good

Use this checklist when deciding whether the synthesis package is ready to use:

- major conclusions are supported by repeated evidence
- standards candidates are few enough to review seriously
- learning recommendations address skill gaps that are better solved by teaching than policy
- repository remediation items stay local unless there is clear cross-repository evidence
- the tone is supportive, specific, and non-punitive
- examples are concrete enough to teach from
- leadership-facing summaries are calm, practical, and free of blame

## What to publish first

Start by publishing a **small number of high-confidence standards**, not the whole synthesis package as if every output belongs in the same lane.

A good default sequence is:

1. **Publish standards first** when the pattern is recurring, consequential, and clear enough to become a practical team expectation.
2. **Publish learning recommendations alongside those standards** when teams will need examples, coaching, workshops, or guided practice to apply them well.
3. **Keep remediation work primarily local** to the affected repositories unless leadership needs visibility into a severe or high-risk issue.

This order helps the organization establish shared expectations first, then support adoption, while avoiding the mistake of turning local cleanup work into portfolio-wide policy.

In practice, that usually means:

- publish only the top 1-3 standards candidates from an initial synthesis
- pair each standard with learning support when the skill gap is likely to block adoption
- keep repository-specific remediation in team backlogs, not in the published standards set

The goal is not to publish everything. The goal is to publish the smallest set of guidance that will create the most useful improvement.

## How to know the workflow is helping over time

Do not look for a single success metric. Look for better standards decisions and fewer repeated problems over repeated assessment cycles.

Useful signals include:

- later assessments show fewer recurring cross-repository issues
- standards candidates become clearer, narrower, and easier to teach
- teams use more consistent language in reviews and design discussions
- more issues are addressed through examples, coaching, and learning support before they become standards problems
- leadership discussions spend less time debating whether a pattern is systemic and more time deciding what action to take
- the synthesis output becomes easier to review because the evidence quality and classification quality improve over time

## Frequently asked questions

For higher-level product and trust questions, see the FAQ in [`README.md`](README.md). This section focuses on practical usage decisions.

### Is this overkill for a small team?

It can be, depending on the input.

If the team has only one repo or one obvious engineering problem, go direct. If the team has multiple services, multiple reviewers, or recurring design and reliability concerns across repos, the synthesis step quickly pays for itself.

### Do I need to adopt every standards candidate?

No. The point is to create a high-quality candidate set, not a giant policy dump.

Most teams should start with a small number of high-leverage candidates and leave the rest for later review.

### Can I use this even if I am not ready to publish standards?

Yes. The outputs are still useful for leadership briefings, training plans, and remediation prioritization even before any formal standards are approved.

### What is the biggest mistake to avoid?

Treating assessment reports as if they were already standards.

Assessment reports diagnose. The synthesis classifies. Final standards come after that.
