# Course Guide: Claude Cowork for Sales Reps

This guide maps each course module to the pre-built skills in this workspace. Instead of building skills from scratch during class, you'll customize and use skills that are already production-ready — so every exercise produces something you can deploy the same day.

**How to use this guide**: Keep it open alongside the course slides. At each module's hands-on segment, jump to the relevant section below for the specific commands to run.

---

## Module 1: The AI Seller Shift (60 min)

**What you're doing in the repo**: First setup + first account brief.

### In-class exercise (10 min hands-on)

Follow `COURSE-SETUP.md` if you haven't already. Then:

```
/account-research [name of a real prospect in your pipeline]
```

**What good output looks like**: A one-page brief with company snapshot, key exec names and titles, recent news (last 90 days), inferred pain points mapped to your solution, and 5 discovery questions.

**If it feels generic**: You need more product context. Run:
```
/hydrate website [your product homepage]
```
Then re-run the account research. The brief should be noticeably more specific.

### Module 1 deliverable
One live account brief for a real prospect. Not a demo — something you'd actually use tomorrow.

---

## Module 2: Account Intelligence in Minutes (60 min)

**What you're doing in the repo**: Understand how a skill is built, customize it to your output preferences, add a competitor battle card.

### In-class exercise A: Read and customize the account-research skill (15 min)

Open `.claude/skills/account-research/SKILL.md` in the file tree.

Read through the steps. Find **Step 3: Generate the Research Brief** — the output format section. Customize the section headers and order to match how you actually like to prep for calls. Common customizations:
- Reorder sections (some reps want competitive watch first)
- Add a "Forecast/ICP Fit Score" section
- Change discovery question count (5 → 3 for shorter calls)

Save the file. Run `/account-research [another prospect]` — you should see your customizations reflected.

### In-class exercise B: Build a battle card (10 min)

Run:
```
/hydrate website [your main competitor's homepage URL]
```

Claude visits the competitor's site and auto-populates `Knowledge/compete/[Competitor].md` with their positioning, likely strengths, and messaging. Then:
```
/competitive-intel [competitor name]
```

You'll see the battle card. It'll be a rough first pass — you'll refine it over the next few weeks as you encounter them in deals.

### Module 2 deliverable
- Customized `account-research` SKILL.md (your preferred output format)
- One competitor battle card in `Knowledge/compete/`

---

## Module 3: Outreach That Gets Responses (60 min)

**What you're doing in the repo**: Customize the email-drafter skill to your voice, generate a real outreach sequence.

### In-class exercise A: Customize the email-drafter skill (15 min)

Open `.claude/skills/email-drafter/SKILL.md`.

Find **Step 3: Draft the Email(s)**. This step already includes format instructions, but you should add:

1. **Your banned phrases** — add a line like:
   ```
   Banned phrases: "Hope this finds you well", "I came across your profile",
   "I'd love to connect", "circle back", "touch base", any phrase with "synergy"
   ```

2. **Your preferred CTAs** — replace the generic CTA library with your actual go-tos:
   ```
   Preferred CTAs (use one per email):
   - "Worth a 15-minute call this week?"
   - "Happy to send over a 2-minute overview video first if helpful."
   - "Are you the right person to talk to, or should I reach out to someone else on your team?"
   ```

3. **Your sign-off** — whatever you actually use.

Save the file.

### In-class exercise B: Generate a real 3-email sequence (10 min)

Pick a real prospect you've been meaning to reach out to. Run:
```
/email-drafter [Company Name] write a 3-email cold outreach sequence.
Email 1: intro referencing [trigger — recent news, funding, job posting, etc].
Email 2: value-led follow-up from a different angle.
Email 3: soft breakup.
```

The output should sound like you — because it's pulling your CLAUDE.md context, your product knowledge from `Knowledge/product/`, and the style customizations you just added.

**Compare against the CRISP framework** from the slides. Where does the prompt above map to each letter?

### Module 3 deliverable
- Customized `email-drafter` SKILL.md (your voice, your CTAs)
- A 3-email cold outreach sequence for a real prospect

---

## Module 4: Pipeline Velocity — From Call to Closed (60 min)

**What you're doing in the repo**: Process a call transcript into a structured summary, follow-up email, and coaching note. Score a stalled deal's MEDDIC health.

### In-class exercise A: Post-call workflow (20 min)

**Option 1 — Use a sample transcript** (if you don't have a recent call to use):

1. In the file tree, navigate to `Course-Materials/sample-transcripts/`
2. Copy `discovery-call-enterprise.md` into `Accounts/Meridian/` (create the folder)
3. Run:
   ```
   /post-call Meridian
   ```

**Option 2 — Use your own notes** (recommended if you had a call this week):

1. Create a folder: `Accounts/[Your Account Name]/`
2. Create a file in that folder: `call-notes-[today's date].md`
3. Paste your notes (rough is fine — bullet points, timestamps, fragments all work)
4. Run:
   ```
   /post-call [Your Account Name]
   ```

**What you should get**:
- Structured call summary (pain, buying signals, objections, next steps, deal risks)
- CRM field update suggestions
- Draft follow-up email
- One coaching note

Read the coaching note. Does it catch something you missed? What's the "quantifying question" the skill flags in the enterprise transcript?

### In-class exercise B: Deal health check (10 min)

Pick a deal that's been stuck or that you're worried about. Run:
```
/deal-health [Account Name]
```

If CRM isn't connected: Claude will ask you to describe the deal. Give it a 3-4 sentence summary: stage, deal size, who you've met, what the pain is, what's blocking it.

You'll get a MEDDIC scorecard with specific gaps flagged. The "Recommended Next Actions" section is the part worth deploying immediately.

### Module 4 deliverable
- Post-call summary + follow-up email from a real or sample transcript
- MEDDIC scorecard for a stalled deal with 3 specific next actions

---

## Module 5: Advanced Cowork — Your Autonomous Sales Agent (60 min)

**What you're doing in the repo**: Run a full pipeline review, see the self-improvement loop in action, optionally connect CRM.

### In-class exercise A: Pipeline review (15 min)

**If CRM is connected**: Run:
```
/pipeline-review [today's date]
```
Claude queries your live pipeline and generates a full snapshot.

**If CRM is NOT connected** (most of you): Run:
```
/pipeline-review [today's date]
```
Claude will ask you to provide pipeline data. Copy the table from `Course-Materials/sample-pipeline.md` and paste it when prompted.

Look at the output. Notice:
- The at-risk flags (which deals trip them and why?)
- The "Recommended Focus" section
- The Knowledge Health pulse at the bottom (which files are stale?)

### In-class exercise B: Knowledge health check (10 min)

Run:
```
/knowledge-health
```

You'll see a dashboard showing which knowledge files are current vs. stale, any competitor gaps (competitors in active deals with no battle card), and any pending retro insights.

After a full day of exercises, your `Product-Overview.md` should be populated but several files will still be empty or at their initial state. The dashboard makes the gaps visible — and tells you exactly what to do next.

### In-class exercise C: Retro on a past deal (10 min, if time permits)

Think of a deal you closed in the last 90 days — won or lost. Run:
```
/retro [Account Name] [won or lost]
```

If CRM isn't connected, Claude will ask for the basics (outcome, deal size, competitor) and then run the retrospective questions. The questions are designed to surface insights you might not capture in a standard deal review.

### Module 5 deliverable
- Pipeline review report (from sample or live CRM)
- Knowledge health dashboard showing your current baseline
- Optional: CRM connected via `SALESFORCE-SETUP.md` (or equivalent)

---

## CRM Connection (Optional — Module 5)

Follow `SALESFORCE-SETUP.md` for Salesforce, or the HubSpot/Dynamics sections in the same file.

**If your IT hasn't approved MCP access**: Don't worry. Every skill in this workspace works without CRM — it just asks you to provide the data manually. CRM connection is a force multiplier, not a requirement.

**After class**: Once you're back at your desk with your usual IT environment, the CRM connection typically takes 15-20 minutes. The `SALESFORCE-SETUP.md` guide walks through each step with screenshots.

---

## 30-Day Adoption Plan

Take this home. One thing per week.

**Week 1 — Foundation**
- Run `/account-research` before every call this week
- Run `/call-prep` the morning of each call (even without CRM — paste your notes)
- Goal: build the habit of opening Claude before your CRM

**Week 2 — Outreach**
- Deploy your 3-email sequence from Module 3 on 10 new prospects
- Measure open and reply rate vs. your pre-course baseline
- Refine the `email-drafter` SKILL.md based on what responses tell you

**Week 3 — Post-Call**
- Run `/post-call` after every discovery call this week
- Compare the follow-up emails Claude drafts to what you'd have written yourself
- Connect CRM if you haven't yet

**Week 4 — Pipeline Review**
- Run `/pipeline-review` before your weekly manager 1:1
- Run `/retro` on 2 recently closed deals (one win, one loss)
- Run `/knowledge-health` — see how much the workspace has improved in 4 weeks

---

## Getting Help

- **Can't find a skill**: Make sure you opened the folder (not a file) in Claude Desktop. All skills live in `.claude/skills/`.
- **Skill output is too generic**: Your `CLAUDE.md` needs more context — especially `Product:` and `ICP:`. Fill those in and re-run.
- **CRM errors**: Check `SALESFORCE-SETUP.md` troubleshooting section.
- **Something isn't working as described**: Run `/knowledge-health` — it often surfaces why a skill is underperforming (missing knowledge files).
