# CLAUDE.md — B2B Sales Workspace
# DEMO VERSION — Catalyst Sales Intelligence
#
# INSTRUCTOR INSTRUCTIONS:
# Copy this file to the workspace root as CLAUDE.md before running demos.
# All [FILL IN] sections are completed for the fictional company "Catalyst Sales Intelligence."
# This identity is consistent with all Course-Materials/ sample files and HubSpot demo data.
# ─────────────────────────────────────────────────────────────────────────────

---

> ## In-Class Quick Start
> This workspace is pre-configured. Skip the fill-in step and go straight to:
> - Test account research: `/account-research Thornwood Capital`
> - Test pipeline review: `/pipeline-review`
> - Test deal health: `/deal-health Vantage Software`

---

## Company & Product Context

- **Company**: Catalyst Sales Intelligence
- **Product**: Catalyst — AI-powered sales coaching and revenue intelligence platform
- **What we sell**: Catalyst analyzes top-performer behaviors across your SDR and AE teams and distributes real-time, context-aware coaching guidance into every rep's existing workflow — Salesforce, Outreach, and email — so your entire team performs like your top 20%. Average customers reduce the top/bottom performer productivity gap by 30–40% within 90 days.
- **Ideal Customer Profile (ICP)**: Mid-market B2B companies, 150–2,000 employees, 20–150 sales reps. Economic buyer is VP Sales or CRO. Champion is typically VP RevOps, Sales Enablement Lead, or Director of Sales Ops. Buying signals: hiring wave incoming, SDR performance spread >2x top vs. bottom, recent leadership change on sales team, Gong or Chorus deployed but coaching at scale still manual.
- **Average deal size**: $50K–$180K ARR
- **Sales cycle length**: 3–6 months
- **Primary competitors**: Gong, Chorus.ai (ZoomInfo), Salesloft, Highspot, Mindtickle
- **CRM**: HubSpot

---

## Team Context

- **Team**: Mid-Market Sales, North America
- **Manager**: Sarah Kim, Regional VP Sales
- **Territory/Segment**: Mid-market accounts, 150–2,000 employees, AMER West + Central
- **Fiscal year end**: December 31

---

## Sales OKRs

*For demo purposes — figures represent a rep at ~70% of quota with a pipeline gap to close.*

| Objective | Key Result | Target | Current |
|-----------|------------|--------|---------|
| Hit quota | Closed ARR | $1,200,000 | $420,000 |
| Build pipeline | Pipeline coverage (3x quota) | $2,400,000 | $1,147,000 |
| Expand accounts | NRR | 110% | 108% |
| Win rate | % deals won | 28% | 24% |

---

## Key Documents

- **`Knowledge/product/Product-Overview.md`** — What we sell, key differentiators, ICP
- **`Knowledge/plays/Discovery-Framework.md`** — MEDDIC discovery questions and qualification criteria
- **`Knowledge/plays/Objection-Handling.md`** — Common objections and responses
- **`Knowledge/compete/Competitive-Landscape.md`** — Overview of competitive set
- **`Knowledge/metrics/Sales-OKRs.md`** — Full OKR detail with progress

---

## Knowledge Taxonomy

This workspace distinguishes two types of knowledge with different improvement mechanisms.

**Descriptive knowledge** ("what is") — facts about product, pricing, competitors, market. Comes from external sources (PMM, product team, competitor research). Goes stale when the world changes.
- Files: `product/`, `compete/`, `metrics/`
- Improve with: `/hydrate` to auto-refresh from public sources, PMM updates, `/competitive-intel`
- Each file has a `stale_after_days` threshold — `/knowledge-health` shows what's overdue

**Procedural knowledge** ("how we do it") — discovery methods, objection handling, plays. Comes from field experience. Improves when we extract learnings from closed deals.
- Files: `plays/`, `org/Process-Guide.md`
- Improve with: `/retro` after every win or loss

**The self-improvement loop:**
```
Deal closes → /retro [Account Name]
  → insights tagged [competitive / process / messaging / objection / play]
  → mapped to specific Knowledge/ files → retro doc written with update tracker
→ /knowledge-health → freshness dashboard + competitor gaps + pending retro insights
→ /hydrate → auto-refresh stale descriptive files from public sources
```

**Run `/knowledge-health` monthly. Run `/retro` after every closed deal.**

---

## Priority Framework

- **P0**: Customer commitments, active deal decisions, manager requests with deadlines
- **P1**: Pipeline-building activities, active opportunities in late stages, QBR prep
- **P2**: Prospecting, relationship maintenance, competitive research
- **P3**: Administrative work, internal alignment, non-urgent learning

**Decision filter**: Does this move a deal forward? Does it build pipeline? Will it help me hit quota?

---

## Working Principles

- **"Understand before proposing"** — Learn the prospect's business before pitching. Ask, don't tell.
- **"Champion or no deal"** — If you don't have an internal champion, you don't have a deal.
- **"Pipeline is a lagging indicator"** — The leading indicators are activities: calls, meetings, demos, proposals.
- **"3-bullet rule"** — If you can't explain the customer's pain in 3 bullets, keep asking questions.
- **Always know the next step** — Every interaction ends with a confirmed next meeting or action.

---

## Sales Methodology

- **Qualification framework**: MEDDIC (Metrics, Economic Buyer, Decision Criteria, Decision Process, Identify Pain, Champion)
- **Sales motion**: Consultative / Solution selling — lead with pain, earn the right to pitch, prove with a time-bound POC
- **Typical buying committee**: Economic Buyer (VP Sales or CRO), Champion (VP RevOps or Sales Enablement), Technical Approver (IT/Security), HR (informed, rarely a blocker)

---

## Available Skills

| Skill | Invocation | What it does |
|-------|------------|-------------|
| **Hydrate** | `/hydrate [source] [location]` | Bootstrap Knowledge/ from website, docs, folder, or Seismic — run this first |
| Call Prep | `/call-prep [Account Name]` | 1-page briefing before any call |
| Pipeline Review | `/pipeline-review [date]` | Weekly pipeline snapshot with risk flags |
| Deal Health | `/deal-health [Account Name]` | MEDDIC scoring + next actions |
| Account Research | `/account-research [Company Name]` | Public research → pain points + outreach hooks |
| Competitive Intel | `/competitive-intel [Competitor]` | Battle card retrieval |
| QBR Prep | `/qbr-prep [Account Name]` | Customer QBR narrative |
| Email Drafter | `/email-drafter [Account Name] [context]` | Context-aware follow-up email |
| **Retro** | `/retro [Account Name] [won\|lost]` | Win/loss retrospective → extracts insights → updates Knowledge/ |
| **Knowledge Health** | `/knowledge-health` | Freshness dashboard — stale files, competitor gaps, pending retro insights |

---

## Recurring Commitments

- **Weekly**: Pipeline review with Sarah Kim (use `/pipeline-review`)
- **Monthly**: Forecast call — commit, upside, best case
- **Quarterly**: QBRs with top accounts (use `/qbr-prep`), personal deal retrospective
- **Ongoing**: Update `Accounts/[Name]/Engagement-Log.md` within 24 hours of every call

---

## Data Architecture

**Your CRM is the system of record for deals.** This workspace does not sync or store CRM data — it queries your CRM live via MCP so your org's sharing rules and RBAC are always respected.

| What lives here (git) | What lives in your CRM | Queried live (productivity tools) | What stays local only |
|----------------------|----------------------|----------------------------------|----------------------|
| Shared knowledge (product, compete, plays) | Opportunities, contacts, activities | Recent emails + meetings (not in CRM) | Account qualitative notes (`Accounts/`) |
| Skills and automation | Pipeline and forecast data | Calendar events and upcoming calls | Generated pipeline reports |
| Win/loss retrospectives | Deal history | Slack threads mentioning an account | |

**`Accounts/` folders are for qualitative context that doesn't belong in your CRM** — political dynamics, relationship nuance, stakeholder motivations. They are gitignored and never shared.

---

## Document Naming Convention

Use YYYYMMDD timestamps for strategic docs: `document-name-20260120.md`
