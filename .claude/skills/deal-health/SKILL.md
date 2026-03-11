---
name: deal-health
description: Score a deal's health using the MEDDIC framework. Identifies gaps, rates risk, and recommends next 3 actions to advance the deal.
invocation: /deal-health
example_usage: /deal-health Acme Corp
---

# Deal Health Skill

Score a deal's MEDDIC health and get specific next actions. Usage: `/deal-health [Account Name]`

## Instructions

When invoked with an account name:

### Step 1: Gather Information

1. Find and read the account folder (`Accounts/[Account Name]/`):
   - `Account-Overview.md` — full deal context
   - `Engagement-Log.md` — recent activity and what's been discussed
   - `Open-Items.md` — commitments and open questions

2. If the account folder doesn't exist or is sparse, ask the rep to fill in the gaps before scoring.

### Step 2: Score Each MEDDIC Dimension

For each dimension, rate: **Strong (Green)** / **Partial (Yellow)** / **Missing (Red)**

**Scoring criteria**:

**M — Metrics**
- Green: Specific, quantified success metrics agreed upon (e.g., "reduce research time by 50%, save $200K annually")
- Yellow: General goals stated but not quantified
- Red: No discussion of measurable outcomes

**E — Economic Buyer**
- Green: Met with EB, they're engaged and supportive
- Yellow: Know who they are but haven't met them
- Red: Don't know who controls the budget

**D — Decision Criteria**
- Green: Documented their evaluation scorecard; we influence the criteria
- Yellow: Know some criteria informally
- Red: Don't know how they're making the decision

**D — Decision Process**
- Green: Mapped every step to contract; have a mutual close plan with dates
- Yellow: Know the rough process but not specifics
- Red: Unknown — no visibility into their buying process

**I — Identify Pain**
- Green: Clear, quantified, urgent pain; executive-level acknowledgment
- Yellow: Pain described but not quantified or not urgent
- Red: Pain unclear or too vague to build urgency around

**C — Champion**
- Green: Identified champion who is actively selling for us internally, has EB access
- Yellow: Someone who likes us but hasn't been tested
- Red: No internal advocate

### Step 3: Generate the Deal Health Report

---

## Deal Health: [Account Name]
*Scored: [Today's date]*

### Overall Health: [🟢 Strong / 🟡 At Risk / 🔴 Critical]

**Deal snapshot**: [ARR] | [Stage] | [Close date] | [Days in current stage]

### MEDDIC Scorecard

| Dimension | Score | Evidence | Gap |
|-----------|-------|---------|-----|
| M — Metrics | 🟢/🟡/🔴 | [What we know] | [What's missing] |
| E — Economic Buyer | 🟢/🟡/🔴 | [What we know] | [What's missing] |
| D — Decision Criteria | 🟢/🟡/🔴 | [What we know] | [What's missing] |
| D — Decision Process | 🟢/🟡/🔴 | [What we know] | [What's missing] |
| I — Identify Pain | 🟢/🟡/🔴 | [What we know] | [What's missing] |
| C — Champion | 🟢/🟡/🔴 | [What we know] | [What's missing] |

**MEDDIC score**: [X/6 dimensions Green]

### Key Risks

[List the 2-3 biggest risks to this deal closing — be specific, not generic]

1. [Risk 1 — e.g., "No EB access — decision could go above our champion's head without us"]
2. [Risk 2]
3. [Risk 3]

### Recommended Next Actions

The 3 most impactful things to do in the next 2 weeks:

1. **[Action 1]** — Why: [reasoning tied to a specific gap] — How: [specific approach]
2. **[Action 2]** — Why: — How:
3. **[Action 3]** — Why: — How:

### Forecast Recommendation

Based on MEDDIC health: **[Commit / Upside / Best Case / Qualify Out]**

[1-2 sentence rationale]

---

### Step 4: Follow Up

"Based on this assessment, the biggest risk is [top gap]. Want to talk through how to address it, or should I help you draft the outreach for the Economic Buyer?"
