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

## Who this is for

This workflow is a strong fit for:

- engineering leads and architects working across multiple repositories or services
- teams that already have completed assessments and need portfolio-level decisions
- standards authors who want evidence-backed candidates instead of opinion-led rules
- engineering managers who need a clear, non-punitive synthesis of recurring risks and improvement opportunities

Do **not** use this workflow when:

- you only have one obvious issue in one repository
- you need a direct repository assessment rather than a synthesis of existing assessments
- your assessment set is incomplete or inconsistent enough that comparison would be misleading
- the goal is performance evaluation, team ranking, or any other personnel judgment

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

## Input quality matters

This workflow is only as strong as the assessment set going into it.

Before you run the skill, make sure:

- each non-empty report includes `Synthesis Input Summary`
- the assessments are reasonably comparable in scope and depth
- major findings are tied to evidence rather than broad impressions
- empty placeholders or unfinished reports have been removed from the working set
- the reports are detailed enough to separate recurring patterns from isolated issues

## Important framing

This skill does **not** assess repositories directly. It works from completed assessment reports.

The outputs are also **not** final standards by default. They are structured decision-support artifacts that help a team decide:

- what should become a standard
- what should become a learning recommendation
- what should remain local remediation
- what should stay on the watchlist until more evidence appears

This workflow should also **not** be used to grade engineers, rank teams, or treat repositories as proxies for individual capability. The goal is engineering enablement: identify recurring patterns, clarify where better standards would help, and highlight where the team would benefit from support, examples, coaching, or training.

If the outputs start sounding like a performance review or an indictment of developer skill, the process is being used incorrectly.

## What good output looks like

Strong synthesis output is:

- **evidence-backed:** conclusions trace back to repeated findings in the assessments
- **narrow enough to act on:** the highest-value standards candidates are clear and limited in number
- **non-punitive:** the tone points toward support, standards, coaching, and remediation, not blame
- **teachable:** standards candidates and learning recommendations are grounded in concrete examples
- **well-classified:** systemic patterns, local remediation, and watch items stay in separate lanes

## Frequently asked questions

### What problem does this solve that a summary doesn't?

A summary tells you what was found. This workflow helps you decide what to **do** about it.

Its value is not just compression. It classifies recurring patterns into standards candidates, learning recommendations, remediation items, and watch items so the organization can choose the right response instead of treating every finding the same way.

### Why use this tool to create engineering standards?

Because good engineering standards are downstream artifacts, not raw review notes.

This skill helps you create standards from repeated evidence across repositories instead of from the loudest single finding. That makes the resulting standards easier to justify, teach, and adopt.

### This seems like boiling the ocean. Isn't there a simpler way?

This is the simpler way **when you already have multiple assessments**.

The skill is not trying to standardize everything. It is a narrowing tool: it helps you decide what deserves a standard, what needs teaching, and what should stay local to one repository. That is usually much less work than asking people to manually compare reports and argue their way to a standard set.

### When should I use this instead of drafting standards directly?

Use direct drafting when you have a single obvious issue or a very small scope.

Use this skill when you have multiple assessment reports and want to avoid inventing standards from incomplete or inconsistent evidence.

### How does it avoid overreacting to isolated findings?

It classifies findings before promoting them into standards.

Repeated, consequential patterns can become standards candidates. Important but local issues stay remediation items. Teachable gaps become learning recommendations. Weak signals remain watch items. That structure is what prevents one noisy repository from turning into a portfolio-wide rule.

### Are the outputs final engineering standards?

No. The standards output is intentionally framed as **standards candidates** so a team can review, refine, and approve them before publication.

### Can engineering standards be used as Copilot skills or agent instructions?

Sometimes, but usually **only after a standard is mature, approved, and already teachable without relying on Copilot**.

If a standard still depends on learning recommendations, examples, coaching, or practice for engineers to apply it well, translating it into a Copilot skill or agent instruction is usually premature. In those cases, Copilot can support learning, but it should not stand in for understanding or judgment.

When a standard is stable and well understood, Copilot can reinforce it through good defaults, review prompts, or repeatable workflows. But Copilot should not replace engineering judgment, and it should not be treated as the authority on design, correctness, tradeoffs, or exceptions.

In short: **standards guide engineers; Copilot can reinforce them later, but it should not be the mechanism that creates understanding.**

### How does it decide what becomes a standard vs a learning recommendation vs remediation?

It classifies findings based on **pattern, scope, and the kind of response most likely to help**.

Repeated, high-consequence patterns can become **standards candidates**. Recurring issues that are better solved through teaching, examples, or coaching become **learning recommendations**. Important but localized issues stay **repository-specific remediation**. Weak signals remain watch items until there is stronger evidence.

### What should we publish first: standards, learning recommendations, or remediation work?

Start with a **small number of standards** when the evidence is strong and the pattern is broad enough to justify a shared expectation.

Publish **learning recommendations alongside those standards** when teams will need examples, coaching, or practice to apply them effectively. Keep **remediation work mostly local** to the repositories where the issue appears, unless the risk is severe enough that leadership needs visibility.

### How do we keep this focused on enablement instead of evaluation?

By treating the workflow as a support tool for engineering systems, not as a judgment tool for people.

This skill is for engineering enablement, not personnel evaluation. It looks for cross-repository patterns so organizations can improve standards, teaching, and support. It should not be used to grade engineers, rank teams, label developers as strong or weak, or turn repository findings into judgments about individual competence.

### How do we know the synthesis is helping over time?

Look for better decisions and fewer repeated portfolio-level patterns, not one magic metric.

The workflow is helping when later assessment rounds show clearer and more teachable standards, more consistent engineering decisions across teams, and fewer recurring cross-repository issues that keep resurfacing in new reviews.

### Does this replace engineering judgment?

No. It improves the quality of the inputs to that judgment.

You still decide what to publish, how opinionated to be, and what to prioritize first. The skill makes those decisions more evidence-based and easier to explain.

## Recommended next read

See [`usage-guide.md`](usage-guide.md) for input expectations, prompt examples, review sequence, and practical guidance on turning the synthesis package into final standards work.
