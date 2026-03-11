---
name: pipeline-review
description: Generate a weekly pipeline review report. Analyzes deal stages, flags at-risk deals, and produces a formatted report ready for manager 1:1s.
invocation: /pipeline-review
example_usage: /pipeline-review 2026-03-11
---

# Pipeline Review Skill

Generate a weekly pipeline snapshot. Usage: `/pipeline-review [date]`

## Instructions

When invoked, do the following:

### Step 1: Gather Pipeline Data

Ask the rep to provide their pipeline data in one of these ways:
- **Option A**: Paste a CSV or table from Salesforce/CRM
- **Option B**: List deals manually in the format: `[Account] | [Stage] | [ARR] | [Close Date] | [Last Activity]`
- **Option C**: Say "read from my account folders" — in which case scan all folders in `Accounts/` and extract deal status from each `Account-Overview.md`

### Step 2: Read Context Files

- `Knowledge/metrics/Sales-OKRs.md` — current quota and targets
- `Knowledge/metrics/Definitions.md` — stage definitions and probability weights

### Step 3: Generate the Pipeline Review

Output the following report and save it to `Pipeline/Weekly-Reviews/pipeline-review-[date].md`:

---

## Weekly Pipeline Review — [Date]
*Prepared for: [Rep name from CLAUDE.md team context]*

### Headline Numbers

| Metric | Target | This Week | Last Week | Trend |
|--------|--------|-----------|-----------|-------|
| Total pipeline | [3x quota] | $[X] | $[X] | [↑/↓/→] |
| Weighted pipeline | — | $[X] | $[X] | |
| Commit (high confidence) | — | $[X] | — | |
| Upside | — | $[X] | — | |
| Deals in pipeline | — | [#] | [#] | |
| Quota remaining this period | — | $[X] | — | |
| Coverage ratio | 3x | [X]x | — | |

### Pipeline by Stage

| Stage | # Deals | Total ARR | Avg Deal Size |
|-------|---------|-----------|--------------|
| Discovery | | | |
| Qualified | | | |
| Technical Evaluation | | | |
| Proposal | | | |
| Negotiation | | | |
| Verbal Commit | | | |
| **Total** | | | |

### Deal Tracker

| Account | Stage | ARR | Close Date | Last Activity | Health |
|---------|-------|-----|------------|--------------|--------|
[List all deals]

### At-Risk Deals (Flag These)

Flag any deal that meets at least one of:
- No activity in the last [21] days
- Close date is in the past
- Stage hasn't changed in [30] days
- Missing Economic Buyer
- No confirmed next step

For each at-risk deal, note WHY it's flagged and suggest a next action.

| Account | Risk Signal | Recommended Action |
|---------|------------|-------------------|
| | | |

### Deals Closing This Period

Deals with close date within the next 30 days — these need the most attention:

| Account | ARR | Close Date | Confidence | Next Step |
|---------|-----|------------|-----------|-----------|
| | | | | |

### Pipeline Gaps

[Analysis: Does pipeline coverage meet the 3x target? What stage is the biggest gap? What actions would close the gap? How many new deals need to be sourced?]

### Recommended Focus for Next Week

Top 3 actions to improve pipeline health:
1. [Action 1 — specific, accountable]
2. [Action 2]
3. [Action 3]

---

### Step 4: Ask for Review

"Here's your pipeline review. A few questions before your 1:1:
- Are there any deals I'm missing or that have changed status?
- Are the risk flags accurate, or is there context I should know?
- What do you want to highlight to your manager?"
