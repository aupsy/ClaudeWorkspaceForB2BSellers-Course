---
name: pipeline-review
description: Generate a weekly pipeline review report. Analyzes deal stages, flags at-risk deals, and produces a formatted report ready for manager 1:1s.
---

# Pipeline Review Skill

Generate a weekly pipeline snapshot. Usage: `/pipeline-review [date]`

## Instructions

When invoked, do the following:

### Step 1: Query Your CRM (Primary Source)

Use the CRM MCP server to fetch the rep's open pipeline live:

```soql
SELECT Id, Name, StageName, Amount, CloseDate, Probability,
       NextStep, LastActivityDate, LastStageChangeDate,
       Account.Name, Account.Industry,
       Owner.Name
FROM Opportunity
WHERE OwnerId = :currentUserId
  AND IsClosed = false
ORDER BY CloseDate ASC
```

Also fetch recent activities to assess deal health:
```soql
SELECT WhatId, MAX(ActivityDate) lastActivity
FROM Task
WHERE OwnerId = :currentUserId
  AND ActivityDate >= LAST_N_DAYS:60
GROUP BY WhatId
```

**If your CRM is not Salesforce**, query the equivalent objects (HubSpot Deals, Dynamics Opportunities) via the configured MCP server.

**If MCP is not configured**, fall back to asking the rep to provide data:
- Paste a CSV/table export from their CRM, or
- List deals manually as: `[Account] | [Stage] | [ARR] | [Close Date] | [Last Activity]`

Flag clearly that CRM data is not live when using the fallback.

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

### Step 4: Knowledge Health Pulse

Before the final report, do a quick freshness check on the two knowledge files most likely to affect deal outcomes this week:

1. **Pricing-and-Packaging.md** — check `last_updated` vs. `stale_after_days: 30` in frontmatter
2. Any battle card (`Knowledge/compete/[Competitor].md`) for competitors that appear in the current pipeline — check `last_updated` vs. `stale_after_days: 90`

If any are stale (🟡 Aging or 🔴 Overdue), append a two-row table at the bottom of the pipeline report:

```markdown
### Knowledge Health (Quick Check)

| File | Status | Note |
|------|--------|------|
| Pricing-and-Packaging.md | 🟡 Aging ([N] days old) | Verify before any Negotiation-stage calls this week |
| compete/[Competitor].md | 🔴 Overdue ([N] days old) | [Competitor] is in [N] active deals — battle card may be stale |

Run /knowledge-health for the full dashboard.
```

**Only include rows for files that are actually stale.** If everything is current (🟢), omit this section entirely — don't clutter pipeline reports that don't need the warning.

### Step 5: Ask for Review

"Here's your pipeline review. A few questions before your 1:1:
- Are there any deals I'm missing or that have changed status?
- Are the risk flags accurate, or is there context I should know?
- What do you want to highlight to your manager?"
