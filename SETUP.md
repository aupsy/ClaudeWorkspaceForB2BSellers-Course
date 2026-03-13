# Setup Checklist

Complete these steps in order to get full value from this workspace.

---

## Phase 1 — Core Context (Do This First, ~30 min)

Start with hydration — it auto-populates the Knowledge/ templates from your real sales materials, so you're filling gaps rather than starting from scratch.

### Option A: Hydrate from sources (recommended, ~15 min)

Run one or more of these in Claude Code:
```
/hydrate website https://www.yourproduct.com
/hydrate docs https://docs.yourproduct.com
/hydrate folder "C:/path/to/your/sales/materials"
/hydrate seismic "Pitch Decks/Enterprise"
/hydrate all    ← interactive, walks through all sources
```

After hydration, review the populated files and fill any remaining gaps.

### Option B: Fill in manually (~30 min)

If you don't have accessible sources, fill these in directly:
- [ ] `Knowledge/product/Product-Overview.md` — your product, differentiators, ICP
- [ ] `Knowledge/product/Pricing-and-Packaging.md` — deal structures and tiers
- [ ] `Knowledge/org/Team-Context.md` — your team structure and territory
- [ ] `Knowledge/metrics/Sales-OKRs.md` — your quota and OKRs

### Either way, complete these manually (internal info not in public sources):
- [ ] Fill in `CLAUDE.md` — team name, methodology, OKR numbers
- [ ] Set your quota in `Knowledge/metrics/Sales-OKRs.md`
- [ ] Add discount authority to `Knowledge/product/Pricing-and-Packaging.md`

**Test**: Open Claude Code and ask "What do I sell and who is my ICP?" — Claude should answer from your context.

---

## Phase 2 — Connect Your CRM (~15 min)

- [ ] Follow `SALESFORCE-SETUP.md` (or the HubSpot / Dynamics 365 section if applicable)
- [ ] Copy `.env.example` → `.env` and fill in your credentials (`.env` is gitignored — never commit it)
- [ ] Verify the connection: ask Claude "Query my open opportunities from CRM"

**Test**: Run `/call-prep [Account Name]` — Claude should pull live opportunity data, contacts, and recent activity directly from your CRM. No manual data entry needed.

**Note on account folders**: `Accounts/` folders are optional and gitignored. Use them for qualitative context that doesn't belong in your CRM — political dynamics, relationship nuance, personal observations. Skills work fully from CRM data alone; account notes are a supplement.

---

## Phase 3 — Competitive Intel (~1 hr)

- [ ] Fill in `Knowledge/compete/Competitive-Landscape.md` — your competitive set overview
- [ ] For each major competitor, copy `Knowledge/compete/_competitor-template.md` → `Knowledge/compete/[Competitor Name].md` and fill it in

**Test**: Run `/competitive-intel [Competitor Name]` — you should get positioning and landmines.

---

## Phase 4 — Plays & Process (~30 min)

- [ ] Review and customize `Knowledge/plays/Discovery-Framework.md` for your methodology
- [ ] Review and customize `Knowledge/plays/Objection-Handling.md` for your common objections
- [ ] Fill in `Knowledge/org/Process-Guide.md` — deal desk, approvals, CRM hygiene rules

---

## Phase 5 — Ongoing Habits

**Weekly**:
- [ ] Run `/pipeline-review [date]` before your manager 1:1
- [ ] Update `Accounts/[Name]/Engagement-Log.md` for each call this week
- [ ] Move closed-won/lost deals to `Win-Loss/`

**Monthly**:
- [ ] Update OKR progress in `Knowledge/metrics/Sales-OKRs.md`
- [ ] Update any stale competitive intel

**Quarterly**:
- [ ] Run `/qbr-prep` for each top account before QBR season
- [ ] Write a win/loss retrospective for the quarter
- [ ] Update `Knowledge/product/Feature-Roadmap.md` with new roadmap items

---

## Tips for Getting the Most Out of Claude

1. **More context = better outputs**. The more you fill in account folders, the better call prep and deal health scoring become.
2. **Be specific**. Instead of "help me with Acme", say `/call-prep Acme Corp` or "What are the open items for Acme Corp?"
3. **Keep logs current**. Logs older than 2 weeks make call prep less useful — Claude can't invent what you didn't log.
4. **Use win/loss write-ups**. They're the most underused file type. A good loss retrospective is worth 10 training sessions.
5. **Share battle cards as PRs**. When you learn something new about a competitor in a deal, update the battle card and submit a PR. It takes 5 minutes and makes the whole team smarter.
