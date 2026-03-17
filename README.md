# B2B Sales Claude Workspace — Course Edition

> **Course participants**: Start here → **[COURSE-SETUP.md](COURSE-SETUP.md)** (15 min, no CRM needed)
> Then follow the module guide → **[COURSE.md](COURSE.md)**

---

# B2B Sales Claude Workspace

A Claude Code workspace template for B2B sales teams. This repo is your AI-native knowledge base — it gives Claude the context it needs to help you prep for calls, analyze your pipeline, score deals, research accounts, and draft follow-ups.

## Philosophy

Context fragmentation kills sales productivity. Your account notes are in CRM, competitive intel is in a wiki, the last call summary is in an email, and the customer's org chart is in your head. Before every call, you spend 30+ minutes pulling it all together.

This workspace solves that. Everything lives in one place. Claude reads it on startup. You ask, it answers.

---

## Quick Start (3 Steps)

### Step 1 — Fork & Clone
Fork this repo and clone it locally. Open the folder in VS Code with the Claude Code extension installed.

```bash
git clone https://github.com/[your-org]/sales-workspace.git
cd sales-workspace
code .
```

### Step 2 — Hydrate Your Knowledge Base
Point Claude at your existing sales materials and it will auto-populate the Knowledge/ templates:

```
/hydrate website https://www.yourproduct.com
/hydrate seismic "Pitch Decks/Enterprise"
/hydrate folder "C:/path/to/sales/materials"
/hydrate all    ← interactive, walks through all sources
```

Supported sources: product website, documentation URL, local folder, Seismic. Each hydration fills in `[FILL IN]` placeholders and marks everything for your review — no silent overwrites.

Then fill in `CLAUDE.md` with the internal details hydration can't know (your quota, team structure, methodology).

### Step 3 — Connect Your CRM
Follow `SALESFORCE-SETUP.md` to connect Salesforce, HubSpot, or Dynamics 365 (~15 min). Each seller connects with their own credentials so your org's sharing rules are always respected.

That's it. Run `/call-prep Acme Corp` and Claude will pull the live opportunity, contacts, and activity from your CRM automatically.

---

## Workspace Structure

```
/
├── CLAUDE.md                    # Your context layer (fill this in first)
├── README.md                    # This file
├── SETUP.md                     # Detailed onboarding checklist
├── .claude/skills/              # Automated workflows (the killer feature)
├── Accounts/                    # One folder per account
├── Knowledge/
│   ├── product/                 # What you sell
│   ├── compete/                 # Competitive intel & battle cards
│   ├── plays/                   # Discovery, objections, sales plays
│   ├── metrics/                 # OKRs and metric definitions
│   └── org/                     # Team structure and processes
├── Pipeline/                    # Weekly reviews and forecasts
└── Win-Loss/                    # Win/loss retrospectives
```

---

## Skills Reference

| Skill | Command | Time Saved |
|-------|---------|-----------|
| **Call Prep** | `/call-prep [Account]` | 30-45 min → 30 sec |
| **Pipeline Review** | `/pipeline-review [date]` | 20-30 min → 2 min |
| **Deal Health** | `/deal-health [Account]` | Manual review → instant MEDDIC score |
| **Account Research** | `/account-research [Company]` | 1 hr research → 5 min |
| **Competitive Intel** | `/competitive-intel [Competitor]` | 15 min Googling → instant |
| **QBR Prep** | `/qbr-prep [Account]` | 2-3 hr prep → 20 min |
| **Email Drafter** | `/email-drafter [Account] [context]` | 15 min writing → 2 min |

---

## Data Architecture: CRM + Workspace

**Your CRM is the system of record.** This workspace doesn't sync or duplicate CRM data — it queries live via MCP using your credentials, so your org's sharing rules and RBAC are always respected. What seller A can't see in the CRM, they can't see here.

| Lives in this repo (shared) | Lives in your CRM (live) | Stays local only (gitignored) |
|----------------------------|-------------------------|------------------------------|
| Product, competitive intel, plays | Opportunities, contacts, activities | `Accounts/` qualitative notes |
| Skills and automation | Pipeline and deal history | Generated pipeline reports |
| Win/loss retrospectives | | |

**Account folders are for context that doesn't belong in your CRM** — political dynamics, relationship nuance, things you'd never log in Salesforce. They're gitignored by default and never shared with teammates.

---

## Team Usage

This works best as a shared team repo:
- **Shared knowledge** lives in `Knowledge/` — every rep benefits from updated battle cards and plays
- **Each seller connects their own CRM credentials** — they see only their accounts, no cross-territory leakage
- **Account notes are local** — never committed, never visible to teammates
- **Win/loss write-ups** are the exception — these are authored retrospectives (not CRM data) and are worth sharing
- PRs for battle card and objection handling updates = lightweight team knowledge management

---

## Contributing

See `SETUP.md` for the recommended onboarding order. File issues or PRs to improve shared knowledge (battle cards, objection handling, plays).
