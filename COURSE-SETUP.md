# In-Class Setup — 15 Minutes

By the end of this setup you'll have a working AI sales workspace, your product knowledge loaded, and your first account brief ready. No CRM connection needed.

---

## Prerequisites (do before class)

- [ ] **Claude Desktop** installed (download at claude.ai/download — Mac or Windows)
- [ ] **Claude Pro or Team plan** active ($20/month minimum — required for skills and Cowork mode)

If you haven't done these yet, do them now — it takes about 5 minutes.

---

## Step 1: Download the workspace (5 min)

**Option A — with git (faster):**
```
git clone https://github.com/aupsy/ClaudeWorkspaceForB2BSellers-Course
```

**Option B — no git needed:**
1. Go to: `github.com/aupsy/ClaudeWorkspaceForB2BSellers-Course`
2. Click the green **Code** button → **Download ZIP**
3. Unzip to your Documents folder

---

## Step 2: Open in Claude Desktop (1 min)

1. Open **Claude Desktop**
2. **File → Open Folder** (or drag the folder onto the Claude Desktop window)
3. Select the folder you just downloaded/unzipped

You should see a file tree on the left panel. If you don't see it, go to **View → Show Files**.

---

## Step 3: Fill in your 4 fields (5 min)

Open `CLAUDE.md` (click it in the file tree). Find the **Company & Product Context** section and fill in these 4 lines — everything else can wait until after class:

```
Company:  [your company name — e.g., Acme Corp]
Product:  [what you sell — one sentence — e.g., "Sales readiness platform for enterprise AE teams"]
ICP:      [your ideal customer — e.g., "Enterprise SaaS, 500-5000 employees, VP Sales or CRO as buyer"]
CRM:      [leave blank for now — we'll connect this in Module 5 if your IT allows]
```

Save the file (Ctrl+S or Cmd+S).

---

## Step 4: Load your product knowledge (3 min)

In the Claude chat panel at the bottom, type:

```
/hydrate website https://[your product homepage URL]
```

Example: `/hydrate website https://www.salesforce.com`

Claude visits your product website and auto-fills `Knowledge/product/Product-Overview.md` with your positioning, ICP, differentiators, and key messages. This powers every account research brief and email you'll write today.

> **No website?** Type `/hydrate website [your company homepage URL]` instead — even a general company page gives Claude useful context.

---

## Test: Your first account brief (1 min)

Type:

```
/account-research [any real prospect you're currently pursuing]
```

If you see a formatted brief with company context, exec names, and suggested talk track — **you're live.** That's it.

---

## What's in this workspace

10 pre-built skills you'll use during the course:

| Skill | What it does | Used in |
|-------|-------------|---------|
| `/hydrate` | Load knowledge from website, docs, or Seismic | Module 1 setup |
| `/account-research` | Pre-call research brief from public sources | Modules 1–2 |
| `/call-prep` | 1-page briefing from CRM + notes + web | Module 2 |
| `/email-drafter` | Personalized outreach + follow-up sequences | Module 3 |
| `/post-call` | Transcript → summary + follow-up email + coaching note | Module 4 |
| `/deal-health` | MEDDIC scoring + next actions | Module 4 |
| `/pipeline-review` | Weekly pipeline snapshot with risk flags | Module 5 |
| `/competitive-intel` | Battle card retrieval and updates | Modules 2, 5 |
| `/retro` | Win/loss retrospective → knowledge updates | Module 5 |
| `/knowledge-health` | Freshness dashboard — stale files, gaps, pending updates | Module 5 |

See `COURSE.md` for the module-by-module exercise guide.

---

## Troubleshooting

**"I don't see the file tree"**
View → Show Files panel, or restart Claude Desktop.

**"/hydrate didn't find much"**
Try a more specific URL: your product's "Features" or "Solutions" page usually has better structured content than the homepage.

**"Skills aren't activating"**
Make sure you opened the *folder* (not just a single file) in Claude Desktop. The `.claude/skills/` folder needs to be part of the workspace.

**"I got an error about MCP"**
That's fine — it means your CRM isn't connected yet. All Module 1–4 exercises work without it. We'll address CRM connection in Module 5.
