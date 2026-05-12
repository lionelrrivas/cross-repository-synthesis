# Cross-Repository Engineering Synthesis Skill

Turn completed repository assessment reports into evidence-backed standards candidates, learning recommendations, remediation priorities, and an executive summary.

Use this skill after detailed repo reviews are done and the organization needs to answer a harder question: **what should become a standard, what needs teaching, what should stay local, and what should remain a watch item?**

## When this workflow helps

Use this workflow when:

- you have multiple repository assessment reports to compare
- you want standards grounded in repeated evidence rather than opinion
- you need a portfolio-level view of recurring engineering patterns
- you want outputs that are teachable, reviewable, and easier to socialize

Do **not** use this workflow when:

- you need a fresh assessment of source code
- you only have one obvious issue in one repository
- the assessment set is too uneven to compare fairly
- the real goal is personnel evaluation, team ranking, or performance management

## Why it matters

Repository assessments are strong diagnostic artifacts, but they are a poor final format for organization-wide action.

Without a synthesis step, teams often:

- turn one noisy repository finding into a portfolio-wide rule
- write standards that are too abstract to teach or enforce
- mix systemic patterns with repo-local cleanup work
- lose the connection between evidence, priorities, and action

This workflow narrows the problem. It converts many repo-level findings into a smaller set of practical decisions.

## What you get

The skill produces a synthesis package with:

1. normalized per-repository summaries
2. cross-repository engineering findings synthesis
3. engineering standards candidates
4. learning recommendations
5. repository remediation candidates
6. executive summary

## Small example

You might start with:

- 3 completed repository assessments
- repeated evidence of weak domain boundaries in 2 repositories
- repeated evidence of fragile testing patterns in 2 repositories
- 1 severe but isolated reliability issue in 1 repository

And end with:

- 2 engineering standards candidates
- 1 learning recommendation
- 1 repository-specific remediation item
- 1 executive summary explaining the portfolio-level picture

That is the core value of the workflow: it turns many detailed findings into a smaller, more actionable set of decisions.

## How to get a good first run

Keep the first pass small and comparable:

- start with 3-5 reasonably complete assessment reports
- ensure each non-empty report includes `Synthesis Input Summary`
- exclude placeholder or obviously unfinished reports
- favor assessments with comparable scope and evidence quality
- focus first on the top 1-3 standards candidates only
- keep learning recommendations and remediation items separate from standards work

This keeps the process lightweight while giving leads and standards authors something concrete to review.

## Important framing

This skill does **not** assess repositories directly. It works from completed assessment reports.

Its outputs are **standards candidates**, not final standards. The goal is to help a team decide:

- what should become a standard
- what should become a learning recommendation
- what should remain local remediation
- what should stay on the watchlist until more evidence appears

This workflow is for engineering enablement, not personnel evaluation. It should not be used to grade engineers, rank teams, or treat repository findings as proxies for individual capability.

## Frequently asked questions

### What problem does this solve that a summary doesn't?

A summary tells you what was found. This workflow helps you decide what to **do** about it.

It classifies recurring patterns into standards candidates, learning recommendations, remediation items, and watch items so the organization can choose the right response instead of treating every finding the same way.

### Are the outputs final engineering standards?

No. The standards output is intentionally framed as **standards candidates** so a team can review, refine, and approve them before publication.

### How does it avoid overreacting to isolated findings?

It classifies findings before promoting them into standards.

Repeated, consequential patterns can become standards candidates. Important but local issues stay remediation items. Teachable gaps become learning recommendations. Weak signals remain watch items. That structure is what prevents one noisy repository from turning into a portfolio-wide rule.

### What should we publish first?

Start with a **small number of high-confidence standards** when the evidence is strong and the pattern is broad enough to justify a shared expectation.

Publish **learning recommendations alongside those standards** when teams will need examples, coaching, or practice to apply them well. Keep **remediation work mostly local** unless leadership needs visibility into a severe or high-risk issue.

### Can engineering standards be used as Copilot skills or agent instructions?

Sometimes, but usually **only after a standard is mature, approved, and already teachable without relying on Copilot**.

If a standard still depends on learning recommendations, examples, coaching, or practice for engineers to apply it well, translating it into a Copilot skill or agent instruction is usually premature. Copilot can reinforce a well-understood standard later, but it should not stand in for understanding or judgment.

### Does this replace engineering judgment?

No. It improves the quality of the inputs to that judgment.

You still decide what to publish, how opinionated to be, and what to prioritize first. The workflow makes those decisions more evidence-based and easier to explain.

## Recommended next read

See [`usage-guide.md`](usage-guide.md) for input expectations, the prompt to use, review order, and practical guidance on turning the synthesis package into final standards work.
