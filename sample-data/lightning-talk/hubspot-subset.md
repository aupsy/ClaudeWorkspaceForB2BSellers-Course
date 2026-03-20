# Lightning Talk — HubSpot Guide
## Which Demos Need HubSpot vs. Pasted Context

---

## Short Answer

The existing lightning talk lesson files (`01_lesson1_ford_account_brief.md` through `05_lesson5_weekly_pipeline_plan.md`) use **NVIDIA selling to Ford, Caterpillar, Siemens, Boeing, and GM** — a large enterprise AI compute scenario. These are designed as **pasted-context demos** and do **not require a live HubSpot connection**.

| Lesson | Demo | Needs HubSpot? |
|--------|------|----------------|
| Lesson 1 — Account Research | Ford Motor account brief | No — paste `01_lesson1_ford_account_brief.md` |
| Lesson 2 — Insight-Led Email | Caterpillar cold outreach | No — paste `02_lesson2_caterpillar_email_context.md` |
| Lesson 3 — Post-Call | Ford post-call notes processing | No — paste `03_lesson3_ford_postcall_notes.md` |
| Lesson 4 — Complex Proposal | Siemens proposal context | No — paste `04_lesson4_siemens_proposal_context.md` |
| Lesson 5 — Weekly Planning | Pipeline + weekly plan | **Optional** — can paste `05_lesson5_weekly_pipeline_plan.md` OR query live HubSpot |

**Bottom line:** For a quick lightning talk demo, skip HubSpot entirely. Use the existing lesson files — they work immediately with zero setup.

---

## Lesson 5: Live HubSpot Option (Recommended if HubSpot is Set Up)

If you've already run the full course HubSpot import, Lesson 5 becomes significantly more impressive when demonstrated with a live CRM query instead of a paste.

### Option A — Paste (no setup required)
Use the existing file: `Lightning talk course materials/05_lesson5_weekly_pipeline_plan.md`

Prompt:
> "It's Monday morning. Using my pipeline below, help me plan this week. Tell me: which 2 deals need my attention most urgently and why, what the single most important action is on each deal, who I should prioritize calling today vs. later this week, and flag any deals at risk of slipping. Give me a day-by-day focus plan for Mon–Fri."

### Option B — Live HubSpot query (more impressive — shows real CRM integration)
With HubSpot connected, use this prompt instead:

> "It's Monday morning. Pull my open deals from HubSpot and help me plan this week. For each deal, tell me: the current stage, days since last activity, and any close date risk. Then give me: (1) the 2 deals I need to act on first and why, (2) the single most important action on each, and (3) a day-by-day focus plan for Mon–Fri."

Expected output: Claude will query HubSpot live, surface Thornwood Capital and Northgate Logistics as at-risk, flag the coverage gap (2.4x vs. 3x target), and build a prioritized week plan.

**Why this is a better demo:** It shows the workspace accessing live data, not just processing a paste. The "I can see your actual CRM" moment lands harder than the query-from-text version.

---

## Using the SaaS Scenario Instead of NVIDIA

If you'd prefer to run the entire lightning talk in the **Catalyst Sales Intelligence / SaaS** persona (consistent with the full 5-hour course), here are the equivalent prompts using the HubSpot dataset:

### Lesson 1 Equivalent — Account Research (Meridian Industrial Group)
```
Research Meridian Industrial Group for me. I'm selling Catalyst Sales Intelligence.
Give me: their top 3 business priorities in sales and enablement, the pain I should
lead with in my first call, and 3 questions to uncover whether they have budget authority.
```

### Lesson 2 Equivalent — Insight-Led Email (Clearpath Solutions)
```
I'm reaching out to Natasha Burns, VP of Sales at Clearpath Solutions. They're a
165-person professional services firm that just went through a sales leadership change.
Write a cold outreach email under 100 words that leads with an insight about their
situation — not our product. End with a specific, easy question.
```

### Lesson 3 Equivalent — Post-Call (Vantage Software)
Paste `Course-Materials/sample-transcripts/discovery-call-midmarket.md` and run:
```
/post-call Vantage Software
```

### Lesson 4 Equivalent — Deal Coaching (Thornwood Capital)
Use `sample-data/hubspot-import/deal-notes.md` (Thornwood Capital section) and run:
```
I've been working the Thornwood Capital deal for 8 weeks. Here are my deal notes:
[paste Thornwood notes]

Tell me: top 3 risk factors for this deal not closing this quarter, questions I've
left unanswered for the buyer, what I should do in the next 48 hours, and a
realistic close path.
```

### Lesson 5 Equivalent — Weekly Planning (Full Pipeline)
Connect HubSpot and use the Option B prompt above.

---

## Setup Time Comparison

| Option | Setup Time | Best For |
|--------|------------|----------|
| Lightning talk with existing NVIDIA files | 0 min | Quick demos, first-time audiences |
| Lightning talk with HubSpot (Lesson 5 only) | 30 min (if full import done) | Audiences who want to see CRM integration |
| Lightning talk with SaaS scenario (Catalyst) | 0 min (if CLAUDE-demo.md is active) | Audiences already in the 5-hour course context |

---

*For the 30-minute lightning talk, the existing lesson files are fully sufficient. HubSpot adds the most value during the full 5-hour course modules that use `/pipeline-review`, `/deal-health`, and the Monday morning workflow.*
