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

### Step 2 — Fill In CLAUDE.md
Open `CLAUDE.md` and fill in all the `[FILL IN]` sections:
- Your company and product
- Your ICP and deal parameters
- Your team OKRs and quota
- Your sales methodology

This file loads automatically every Claude session. Filling it in once means you never have to re-explain context.

### Step 3 — Add Your Accounts
For each active account:
1. Copy `Accounts/_template/` → `Accounts/[Account Name]/`
2. Fill in `Account-Overview.md` with everything you know
3. Log your first notes in `Engagement-Log.md`

That's it. Start using skills like `/call-prep Acme Corp` immediately.

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

## The Value of Account Folders

Every note you log in `Accounts/[Name]/Engagement-Log.md` becomes context Claude can use. The more you log, the better every skill performs. Think of it as a compound interest account — small deposits now pay off exponentially when you need to prep for an exec meeting or hand off an account.

**Golden rule**: Log call notes within 24 hours. Use the `Engagement-Log.md` template — it takes 5 minutes.

---

## Team Usage

This works best as a shared team repo:
- Each rep maintains their own account folders
- Competitive intel and plays are shared in `Knowledge/`
- Win/loss write-ups in `Win-Loss/` become team learning
- PRs for battle card updates = lightweight knowledge management

---

## Contributing

See `SETUP.md` for the recommended onboarding order. File issues or PRs to improve shared knowledge (battle cards, objection handling, plays).
