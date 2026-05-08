# Cross-Repository Engineering Synthesis Skill

Turn repository assessment reports into evidence-backed engineering standards candidates, learning recommendations, remediation priorities, and an executive summary.

This skill is designed for the moment after detailed repo reviews are done and the organization needs to answer a harder question: **what should we actually standardize, teach, fix locally, or watch across the portfolio?**

## The problem it solves

Repository assessments are great diagnostic artifacts, but they are a poor final format for team-wide action.

Without a synthesis step, teams often:

- turn one noisy repo issue into an organization-wide rule
- write standards that are too abstract to teach or enforce
- mix systemic patterns with one-off cleanup work
- lose the connection between evidence, priorities, and action
- spend too much time debating findings that should have been classified first

This skill closes that gap. It converts many repo-level reports into one portfolio-level view that is easier to act on.

## Why use it

- **Evidence-backed standards candidates:** promotes repeated, consequential patterns instead of isolated anecdotes
- **Less overreaction:** separates standards, learning needs, repo-specific remediation, and watch items
- **Better teaching artifacts:** requires code-example plans for standards and before/after examples for learning recommendations
- **Faster alignment:** gives leads, architects, and managers a shared synthesis package instead of scattered reports
- **More practical governance:** keeps standards incremental, reviewable, and grounded in actual repository evidence

## What you get

The skill produces a full synthesis package:

1. normalized per-repository summaries
2. cross-repository engineering findings synthesis
3. engineering standards candidates
4. learning recommendations
5. repository remediation candidates
6. executive summary

## A small example

For example, you might start with:

- 3 completed repository assessments
- repeated evidence of weak domain boundaries in 2 repositories
- repeated evidence of fragile testing patterns in 2 repositories
- 1 severe but isolated reliability issue in 1 repository

And end with:

- 2 engineering standards candidates
- 1 learning recommendation
- 1 repository-specific remediation item
- 1 executive summary that explains the portfolio-level picture

That is the core value of the skill: it turns many detailed findings into a smaller, more actionable set of decisions.

## How it works

1. Put completed repository assessment reports in `assessments/`.
2. Ensure each report includes a `Synthesis Input Summary` section.
3. Run the skill to normalize the reports, identify recurring themes, and classify the findings.
4. Review the generated outputs in sequence before drafting final engineering standards.

## Start small

Treat the first run as a calibration pass, not a mandate to standardize everything.

An easy adoption pattern is:

1. Start with 3-5 assessment reports.
2. Focus on the top 1-3 standards candidates only.
3. Keep learning recommendations and remediation items separate from standards work.
4. Use the first synthesis to align on language, thresholds, and evidence quality.
5. Expand the scope only after the team trusts the workflow.

This keeps the process lightweight while still giving leadership and standards authors something concrete to act on.

## Important framing

This skill does **not** assess repositories directly. It works from completed assessment reports.

The outputs are also **not** final standards by default. They are structured decision-support artifacts that help a team decide:

- what should become a standard
- what should become a learning recommendation
- what should remain local remediation
- what should stay on the watchlist until more evidence appears

This workflow should also **not** be used to grade engineers, rank teams, or treat repositories as proxies for individual capability. The goal is engineering enablement: identify recurring patterns, clarify where better standards would help, and highlight where the team would benefit from support, examples, coaching, or training.

If the outputs start sounding like a performance review or an indictment of developer skill, the process is being used incorrectly.

## Frequently asked questions

### Why use this tool to create engineering standards?

Because good engineering standards are downstream artifacts, not raw review notes.

This skill helps you create standards from repeated evidence across repositories instead of from the loudest single finding. That makes the resulting standards easier to justify, teach, and adopt.

### This seems like boiling the ocean. Isn't there a simpler way?

This is the simpler way **when you already have multiple assessments**.

The skill is not trying to standardize everything. It is a narrowing tool: it helps you decide what deserves a standard, what needs teaching, and what should stay local to one repository. That is usually much less work than asking people to manually compare reports and argue their way to a standard set.

### When should I use this instead of drafting standards directly?

Use direct drafting when you have a single obvious issue or a very small scope.

Use this skill when you have multiple assessment reports and want to avoid inventing standards from incomplete or inconsistent evidence.

### Are the outputs final engineering standards?

No. The standards output is intentionally framed as **standards candidates** so a team can review, refine, and approve them before publication.

### Can this be used to evaluate or grade engineers?

No.

This skill is for engineering enablement, not personnel evaluation. It looks for cross-repository patterns so organizations can improve standards, teaching, and support. It should not be used to rank developers, label teams as strong or weak, or turn repository findings into judgments about individual competence.

### Why not just ask for a summary of all the reports?

A summary is helpful, but it usually stops short of classification and action.

This skill goes further by organizing recurring patterns into standards candidates, learning recommendations, remediation items, and executive guidance. That makes it much more useful for engineering leadership and standards authors.

### Does this replace engineering judgment?

No. It improves the quality of the inputs to that judgment.

You still decide what to publish, how opinionated to be, and what to prioritize first. The skill makes those decisions more evidence-based and easier to explain.

## Recommended next read

See [`usage-guide.md`](usage-guide.md) for input expectations, prompt examples, review sequence, and practical guidance on turning the synthesis package into final standards work.
