---
name: cross-repository-engineering-synthesis
description: Synthesize multiple repository assessment reports into portfolio-level engineering findings, standards candidates, and learning recommendations. Use this skill whenever the user has assessment reports, code review findings, or diagnostic reports covering multiple repositories or services and wants to understand recurring patterns, produce team training recommendations, draft engineering standards, or create an executive summary of engineering health across a portfolio. Trigger for phrases like "what patterns show up across our repos", "turn these assessments into standards", "what should the team learn from these reviews", "synthesize our engineering findings", "what keeps coming up across our services", or any request to consolidate findings from multiple repo reviews into actionable guidance — even if the user doesn't say "cross-repository" or "synthesis". Also trigger when the user mentions normalizing legacy-format assessment reports or wants to identify remediation priorities across a set of repositories.
version: 2
---

# Cross-Repository Engineering Synthesis Skill

## Purpose

Use this skill to synthesize multiple repository assessment reports into portfolio-level engineering findings, standards candidates, and learning recommendations.

This skill does **not** assess source repositories directly. It consumes completed repository assessment reports as evidence. The goal is to identify recurring engineering patterns across repositories and convert those patterns into practical, teachable, evidence-backed guidance.

Version 2 adds explicit support for standards candidates that include relatable code examples. Standards candidates should not remain abstract. When a finding is strong enough to become a standards candidate, the skill should also describe how that standard can be taught with simplified code.

## Core Principle

A repository assessment report is diagnostic evidence. It is not an engineering standard.

The synthesis step determines which findings are:

- systemic enough to become engineering standards candidates
- skill-driven enough to become learning recommendations
- severe but isolated enough to become targeted remediation items
- low-priority enough to remain local cleanup

Do not convert every finding into a standard.

When a finding does become a standards candidate, treat it as both a governance artifact and a teaching artifact. The standard should help reviewers recognize the issue, and it should help developers understand what better implementation looks like.

## Expected Input

An `assessments/` directory containing Markdown repository assessment reports.

The skill supports two report formats:

1. **Current format** reports that include a `Synthesis Input Summary` section.
2. **Legacy format** reports that do not include the summary section but do include narrative assessment sections such as repository context, dimension ratings, top recurring engineering risk patterns, likely skill or standards gaps, and candidate engineering standard examples.

Ignore empty placeholder files.

## Required Output

Save all output files into a `synthesis-output/` directory alongside the `assessments/` directory (i.e., as a sibling, not inside it). Create the directory if it does not exist. If the user specifies a different output location, use that instead.

Produce a cross-repository synthesis package containing the following files. Use the corresponding template from `templates/` for each unless the user asks for a different format.

1. `synthesis-output/cross-repository-engineering-findings-synthesis.md` → use [`templates/cross-repository-synthesis-template.md`](templates/cross-repository-synthesis-template.md)
2. `synthesis-output/normalized-assessment-summaries.md` → use [`templates/normalized-assessment-summaries-template.md`](templates/normalized-assessment-summaries-template.md)
3. `synthesis-output/engineering-standards-candidates.md` → use [`templates/engineering-standards-candidates-template.md`](templates/engineering-standards-candidates-template.md)
4. `synthesis-output/learning-recommendations.md` → use [`templates/learning-recommendations-template.md`](templates/learning-recommendations-template.md)
5. `synthesis-output/repository-remediation-candidates.md` → use [`templates/repository-remediation-candidates-template.md`](templates/repository-remediation-candidates-template.md)
6. `synthesis-output/synthesis-executive-summary.md` → use [`templates/synthesis-executive-summary-template.md`](templates/synthesis-executive-summary-template.md)

After saving, print the path to each file so the user knows exactly where to find them.

## Reference Files

These files provide detailed guidance for specific workflow steps. Read them as needed — do not load all of them upfront.

| When to read | File |
|---|---|
| Normalizing reports (Steps 1–2) | [`references/normalization-rules.md`](references/normalization-rules.md) |
| Grouping themes by engineering concept (Step 4) | [`references/risk-pattern-taxonomy.md`](references/risk-pattern-taxonomy.md) |
| Classifying and prioritizing themes (Steps 5–6) | [`references/prioritization-model.md`](references/prioritization-model.md) |
| Drafting standards candidates (Steps 8–8a) | [`references/standards-writing-guidance.md`](references/standards-writing-guidance.md) |
| Drafting learning recommendations (Step 9) | [`references/learning-recommendation-guidance.md`](references/learning-recommendation-guidance.md) |
| Validating legacy-format normalization | [`examples/legacy-assessment-seed-summary.md`](examples/legacy-assessment-seed-summary.md) |
| Final quality review | [`examples/synthesis-workflow-checklist.md`](examples/synthesis-workflow-checklist.md) |

> Before writing any output, read the **Safety and Tone Rules** section near the end of this skill. Those rules apply throughout the entire synthesis.

## Workflow

### Step 1: Inventory the assessment set

Identify:

- number of reports found
- number of usable non-empty reports
- repository names
- primary archetypes
- reviewer confidence levels
- whether each report uses current format or legacy format

If some reports are unreadable, empty, or clearly incomplete, list them separately and exclude them from aggregation.

### Step 2: Normalize each report

For each repository, create a normalized summary with:

- repository name
- primary archetype
- reviewer confidence
- architecture rating
- design rating
- readability rating
- reliability rating
- testability rating
- complexity rating
- risk pattern tags
- top engineering risks
- candidate standards
- learning signals
- representative evidence references
- normalization confidence

If the report has a `Synthesis Input Summary`, use it as the primary source. Validate it against the rest of the report.

If the report is legacy format, infer the same fields from the narrative. Mark normalization confidence as `High`, `Medium`, or `Low`. See [`references/normalization-rules.md`](references/normalization-rules.md) for detailed inference guidance and confidence criteria. For a worked example of what normalized legacy-report output looks like, see [`examples/legacy-assessment-seed-summary.md`](examples/legacy-assessment-seed-summary.md).

### Step 3: Aggregate dimension ratings

Create a portfolio-level distribution of ratings across:

- architecture
- design
- readability
- reliability
- testability
- complexity

Do not over-interpret numeric counts. Counts are a signal, not the conclusion.

### Step 4: Identify recurring engineering themes

Group related findings into recurring themes. Prefer engineering concepts over wording similarity. Use the canonical pattern tags from [`references/risk-pattern-taxonomy.md`](references/risk-pattern-taxonomy.md) to ensure consistent naming across repositories.

For example, group these together:

- anemic model
- behavior displaced into services
- validation outside domain types
- mutable data bags
- helper methods that belong on domain types

under a broader theme such as:

`Domain modeling and invariant enforcement weakness`

### Step 5: Classify each theme

Classify each recurring theme as one of:

- **Standards candidate**: recurring, actionable, teachable, and important enough to guide future development
- **Learning recommendation**: recurring evidence of a skill gap, best addressed through teaching, examples, pairing, or workshops
- **Repository-specific remediation**: severe or important, but not broad enough to become a team standard
- **Watch item**: visible pattern, but not yet enough evidence for a standard or formal recommendation

### Step 6: Prioritize

Use the prioritization model in [`references/prioritization-model.md`](references/prioritization-model.md).

Prioritize higher when a theme is:

- repeated across multiple repositories
- connected to reliability, correctness, security, data integrity, or operational support
- visible in core request, message, or batch-processing paths
- difficult to detect through tests alone
- likely to slow future delivery
- teachable through concrete examples

### Step 7: Draft the synthesis report

The synthesis report should be evidence-backed but not punitive.

It should answer:

- What are the most repeated engineering risks?
- Which risks appear systemic?
- Which risks are isolated but severe?
- Which standards should be drafted first?
- Which learning recommendations would help the team most?
- Which examples are suitable for teaching?
- Where should leadership focus attention?

### Step 8: Draft standards candidates

Read [`references/standards-writing-guidance.md`](references/standards-writing-guidance.md) before drafting. It explains what makes a standard practical versus a slogan, and provides tone guidance and a recommended shape for each standard.

For each standards candidate, include:

- standard name
- problem it addresses
- why it matters
- evidence pattern across repositories
- practical expectation
- non-goals
- implementation guidance
- problem example summary
- preferred example summary
- testing example summary
- suggested code review checks
- suggested automation or quality gate
- learning support needed
- drafting priority

Each standards candidate should include enough code-example direction that a final standard can be drafted without inventing the teaching approach later.

Do **not** write standards as academic principles or broad slogans. Write them as practical expectations a development team could apply during design, implementation, and code review.

#### Code example guidance for high-priority candidates

For every high-priority standards candidate, include a code-example plan. Prefer simplified, fictional examples that resemble the team's technology stack and problem space without copying internal repository code.

Use this example structure:

1. **Problem example**: a small, recognizable snippet that demonstrates the anti-pattern or risk.
2. **Preferred example**: a better implementation that demonstrates the intended standard.
3. **Testing example**: a small test showing how the preferred design is easier to verify.

Code examples should:

- be short enough to teach one idea clearly
- use realistic Spring Boot, Java, testing, or messaging examples when appropriate
- avoid copying proprietary code from assessed repositories
- avoid naming real internal systems unless the input reports already make those names safe to use
- show the engineering consequence, such as easier testing, clearer boundaries, safer failure handling, or stronger domain invariants
- include comments only when they clarify the teaching point
- always use **explicit Java types** — never use `var`. Write `CorrespondenceService service = new CorrespondenceService(...)` not `var service = ...`. The team reads and reviews code with explicit types and `var` creates unnecessary friction in teaching material.
- use **layered architecture patterns** the team recognizes: `@Controller` (or `@RestController`) → `@Service` → `@Repository`. Avoid clean/hexagonal architecture vocabulary (`UseCase`, ports, adapters in the hexagonal sense, domain services) — this would introduce an unfamiliar style that distracts from the teaching point. The goal is to illustrate one engineering improvement clearly, not to advocate for an architectural style the team hasn't adopted.

If the synthesis evidence is strong but the example shape is not obvious, include a placeholder such as `Example to draft: service responsibility boundary using a fictional correspondence workflow` rather than inventing a misleading example.

### Step 9: Draft learning recommendations

Read [`references/learning-recommendation-guidance.md`](references/learning-recommendation-guidance.md) before drafting. It includes a table matching common engineering patterns to effective learning formats (workshops, katas, walkthroughs, etc.) and guidance on supportive tone.

For each learning recommendation, include:

- skill area
- evidence from assessments
- why the learning matters
- recommended learning format
- suggested exercise or workshop
- a brief **before/after code example** that illustrates the skill gap in a small, recognizable snippet — use the same code style rules as standards candidates (explicit types, layered architecture, no `var`)
- expected outcome
- priority

Learning recommendations should be supportive and team-enabling, not remedial or blame-oriented.

### Step 10: Write the executive summary

The executive summary should be short, calm, and leadership-appropriate.

It should emphasize:

- the assessments are diagnostic evidence, not performance reviews
- the synthesis identifies patterns, not individual blame
- the standards should be practical and incremental
- learning recommendations are part of the improvement strategy
- not every finding becomes a rule

## Safety and Tone Rules

- Do not name individual developers.
- Do not describe teams as careless, incompetent, lazy, or irresponsible.
- Do not imply that a repository owner failed personally.
- Do not turn the assessment reports into a giant compliance checklist.
- Do not recommend rewriting systems unless evidence strongly supports that conclusion.
- Prefer incremental remediation, standards, and learning paths.
- Separate engineering risk from moral judgment.
- State uncertainty when the evidence is incomplete.

## Important Distinctions

| Artifact | Purpose | Audience | Level of detail |
|---|---|---|---|
| Repository assessment | Diagnose risks in one repository | Reviewers, leads, standards authors | High detail |
| Cross-repository synthesis | Identify recurring patterns | Leads, architects, engineering managers | Medium detail |
| Engineering standards | Define practical team expectations | All developers | Concise and practical |
| Learning recommendations | Help developers improve | Team members, mentors | Supportive and targeted |

## Final Quality Check

Before finalizing, verify:

- every major conclusion is supported by assessment evidence
- standards candidates are based on recurring or high-consequence findings
- standards candidates include concrete, relatable code-example direction
- learning recommendations map to observed skill gaps
- repository-specific findings are not overstated as systemic
- rating counts match the normalized summaries
- tone is improvement-oriented
- output can be shared without causing people to mistake the diagnostic reports for final standards

For a detailed checklist to use during this review, see [`examples/synthesis-workflow-checklist.md`](examples/synthesis-workflow-checklist.md).
