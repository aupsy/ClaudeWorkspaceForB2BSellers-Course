# In-Class Setup — 20 Minutes

By the end of this setup you'll have two things running: a **Claude Project** with your sales context loaded (for Modules 1–3), and the **Cowork workspace** set up (for Modules 4–5). No CRM connection needed for either.

---

## Prerequisites (do before class)

- [ ] **Claude Desktop** installed (download at claude.ai/download — Mac or Windows)
- [ ] **Claude Pro or Team plan** active ($20/month minimum — required for Projects, Skills, and Cowork)

If you haven't done these yet, do them now — it takes about 5 minutes.

---

## Part A: Claude Projects Setup (5 min) — for Modules 1–3

Claude Projects gives Claude persistent memory of your sales context — your ICP, your product, your territory. Every chat in the Project automatically knows who you are and what you sell.

1. Open **Claude Desktop** → click **Projects** in the left sidebar → **New Project**
2. Name it: `My Territory — [Your Name]`
3. Click **Add to Project** and upload:
   - Your ICP definition (a paragraph or bullet list works — it doesn't need to be formatted)
   - Your product one-pager or key value props (PDF or text)
   - 3 high-performing emails from yourself or top teammates (paste as text if needed)
4. In **Project Instructions**, add:
   ```
   My name: [Your Name]
   My role: [Your Title] at [Company]
   Tone: [e.g., "direct and consultative, no jargon"]
   CRM: [System — leave blank if not connected yet]
   ```
5. **Test**: In the Project chat, type: "Create a one-page account brief for [any real prospect]"

You should get a specific brief that knows your product. If it's generic, add more context to the Project.

---

## Part B: Cowork Workspace Setup (15 min) — for Modules 4–5

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

## Step 2: Open in Claude Cowork (1 min)

1. In **Claude Desktop**, switch to **Cowork** mode (top of the chat panel)
2. **File → Open Folder** (or drag the folder onto the window)
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

## Test: Your first Cowork account brief (1 min)

In the Cowork chat panel, type:

```
/account-research [any real prospect you're currently pursuing]
```

If you see a formatted brief with company context, exec names, and suggested talk track — **the workspace is live.**

> **Tip**: This Cowork brief pulls from your `Knowledge/product/` files. The Projects brief (from Part A) pulls from your Project uploads. They complement each other — the Projects path is faster for one-off chat tasks; the Cowork path generates files you can save and reuse.

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
