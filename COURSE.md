# Modern Selling in the Age of AI — Cowork Workspace Guide

This guide is your companion to the course. It maps each module to the pre-built skills in this workspace and shows you exactly what to run, when, and what to expect. Keep it open alongside the course session.

**How this workspace fits the course:**
- **Modules 1–3** (Chat + Projects): These exercises work directly in Claude chat — no workspace setup required. The workspace is running in the background.
- **Modules 4–5** (Cowork): These exercises use the skills in this workspace. By now you've loaded your context; the workspace becomes your autonomous colleague.

**Before Module 4**: Make sure you've completed `COURSE-SETUP.md` — it's the 15-minute workspace setup that makes the Module 4-5 exercises work.

---

## Module 1: The AI Seller Shift (60 min)

**Coaching truth**: Buyers in 2026 arrive having done 70% of their research. They don't need you to explain your product — they need you to tell them something they don't already know about *their own situation*. Insight-led openers win. "Tell me about your business" does not.

**What Claude removes**: The 45 minutes of manual research that would have been necessary to build the brief that makes an insightful opener possible.

### In-class exercise: Your first account brief (10 min)

**Step 1 — Claude Projects setup** (if not already done):
1. Claude Desktop → **Projects** → **New Project: "My Territory"**
2. Upload: your ICP definition (a rough paragraph works), your product one-pager or key value props, and 3 high-performing emails from yourself or a top teammate
3. Set instructions: your name, role, tone preferences ("direct and consultative, no jargon")

**Step 2 — First account brief**:
In the Project chat, type:
```
Create a one-page account brief for [Company] — cover business overview, key executives,
recent news in the last 90 days, likely pain points, and a suggested insight-led opening
talk track for a first call.
```

**What good output looks like**: A specific brief with named executives, a real trigger event (funding, leadership change, expansion, product launch), a pain hypothesis tied to your solution, and an opener you wouldn't have written without this research.

**If it feels generic**: Your Project needs more context. Add your product one-pager and re-run.

### Workspace setup (runs in parallel with M1)

Complete `COURSE-SETUP.md` (15 min). This loads your product knowledge into the workspace's skills so that `/account-research`, `/email-drafter`, and `/post-call` understand your business. You'll need this for Modules 4–5.

```
/hydrate website [your product homepage URL]
```

### Module 1 deliverable
One live account brief for a real prospect — with a rewritten insight-led opener based on what you learned. Not a demo account. One you'd actually use tomorrow.

---

## Module 2: Account Intelligence — Discovery Is a Research Problem (60 min)

**Coaching truth**: Discovery quality is a research problem as much as a questioning technique problem. You cannot ask insightful questions about a business you don't understand. The Orientation → Exploration → Advancement framework gives you the sequence; the account research Skill gives you the raw material.

- **Orientation**: Open with a credibility statement that earns the right to ask hard questions — show you understand their situation before asking them to explain it
- **Exploration**: Current state → Business impact → What would change if that problem went away? Never jump to pain without earning it
- **Advancement**: Summarize in their exact words; set the next step live, before you hang up

**What Claude removes**: The inconsistency. Reps who do this research manually do it well sometimes, skip it when busy. A Skill makes the excellent version automatic.

### In-class exercise A: Build or customize the account-research Skill (15 min)

Open `.claude/skills/account-research/SKILL.md` in the workspace file tree.

Read through **Step 3: Generate the Research Brief** — the output format section. Customize it to how you actually like to prep:
- Reorder sections (some reps want competitive context first)
- Add a discovery question format aligned to the Orientation → Exploration → Advancement framework
- Change discovery question count (5 → 3 for shorter calls, 7 for enterprise)

Save the file. Run:
```
/account-research [a second prospect from your pipeline]
```
You should see your customizations reflected.

### In-class exercise B: Discovery roleplay (10 min)

After generating an account brief, use `Course-Materials/discovery-roleplay-prompt.md` as a sparring partner. Copy the prompt, paste it into Claude chat (not the workspace skill — just plain chat), and replace `[Company]` and `[Title]` with the account you just researched:

```
Act as a skeptical [Title] at [Company]. You've agreed to a 20-minute discovery call.
You're evaluating three vendors. You don't love being sold to.
Answer my discovery questions honestly but with appropriate resistance.
After I'm done, score my performance on: insight-led opener, question quality,
whether I listened or just moved on, and quality of my next-step close.
```

This is private, non-judgmental practice. The coaching note it produces feeds into your self-awareness — and into the Self-Coaching Scorecard we'll use in Module 4.

### The SPEAR check (5 min)

Before leaving Module 2, use `Course-Materials/spear-framework.md` to identify one more workflow in your week that should become a Skill. Any workflow scoring 3+ out of 5 is worth building.

### Module 2 deliverable
- Customized `account-research` SKILL.md (your preferred output format + O→E→A discovery questions)
- One Claude-coached discovery roleplay with a written scorecard

---

## Module 3: Outreach That Gets Responses (60 min)

**Coaching truth**: Buyers choose sellers they trust over sellers with the best product. Trust is built through demonstrated understanding — not charm, not persistence, not a clever subject line. *Insight personalization* (showing you understand their specific business situation) is what creates that trust. *Surface personalization* (Michigan Wolverines, mutual connections) signals shallow research.

**What Claude removes**: The 45 minutes of research per prospect that makes insight personalization impractical at scale. With an account brief already built, the email writes itself — contextualized by real trigger events.

### In-class exercise A: The Personalization Audit (10 min)

Option 1 — Use your own emails: Pull your last 10 sent cold emails and paste them into Claude chat with this prompt:
```
Analyze these 10 cold emails I've sent. For each one, score it 1–5 on:
- Specificity of the trigger referenced (1 = generic, 5 = highly specific)
- Quality of the problem hypothesis (1 = feature push, 5 = genuine business insight)
- CTA quality (1 = vague "let me know", 5 = specific, low-friction ask)
Then tell me: what patterns do you see? What would the best rep at my company do differently?
```

Option 2 — Use the sample set: Open `Course-Materials/sample-cold-emails.md`. Paste the 10 sample emails with the same prompt above. The patterns it finds will be the same ones it would find in most reps' real outboxes.

Either way: the score usually stings. The gap creates the motivation to build the outreach Skill properly.

### In-class exercise B: Customize the email-drafter Skill (15 min)

Open `.claude/skills/email-drafter/SKILL.md`.

Find **Step 3: Draft the Email(s)**. Add three customizations:

1. **Your banned phrases**:
   ```
   Banned phrases: "Hope this finds you well", "I came across your profile",
   "I'd love to connect", "circle back", "touch base", any phrase with "synergy"
   ```

2. **Your preferred CTAs** (replace the generic library):
   ```
   Preferred CTAs (use one per email):
   - "Worth a 15-minute call this week?"
   - "Happy to send a 2-minute overview video first if helpful."
   - "Are you the right person to talk to, or should I reach out to someone else?"
   ```

3. **Your sign-off** — whatever you actually use.

Save the file.

### In-class exercise C: Generate a 3-email sequence + LinkedIn message (10 min)

Pick a real prospect you've been meaning to reach out to. Run:
```
/email-drafter [Company Name] write a 3-email cold outreach sequence.
Email 1 (Day 1): intro referencing [specific trigger — recent news, funding, job posting].
Email 2 (Day 5): different angle, value-led.
Email 3 (Day 12): soft breakup with a genuine question.
Also write a LinkedIn connection request under 300 characters.
```

The output should sound like you — because it's pulling your CLAUDE.md context, `Knowledge/product/`, and the style customizations you just added.

**CRISP check**: Use `Course-Materials/crisp-framework.md` to evaluate your prompt above. Where does it map to Context, Role, Instructions, Specifics, Format? Where is it weak?

### Module 3 deliverable
- Completed Personalization Audit with a written reflection on what you'll change
- Customized `email-drafter` SKILL.md (your voice, your CTAs, your banned phrases)
- A 3-email sequence + LinkedIn message for a real prospect

---

## Module 4: Pipeline Velocity — The Self-Coaching Loop (60 min)

**Coaching truth**: Reps improve fastest when feedback is specific, timely, and tied to actual conversations. The problem: most reps never get coached on their individual calls because managers don't have the capacity. This creates a skill plateau — reps repeat the same patterns indefinitely. The Self-Coaching Scorecard breaks the plateau.

**What Claude removes**: The 60–90 minutes of manual post-call work (CRM update, follow-up email, summary, notes) that is the most consistently skipped part of a rep's day. And the absence of coaching feedback that compounds over months into stalled skill development.

### In-class exercise A: The 360° Call Debrief (20 min)

This is the most powerful exercise in the course.

**Step 1 — Self-score first** (5 min, no Claude):
Open `Course-Materials/self-coaching-scorecard.md`. Score yourself on last week's best discovery call — honestly, before Claude sees anything.

**Step 2 — Run the debrief** (2 min):

*Option A — Use a sample transcript* (if you don't have a recent call):
1. Navigate to `Course-Materials/sample-transcripts/`
2. Copy `discovery-call-enterprise.md` into `Accounts/Meridian/` (create the folder if needed)
3. Run:
   ```
   /post-call Meridian debrief
   ```

*Option B — Use your own notes* (recommended if you had a call this week):
1. Create `Accounts/[Account Name]/call-notes-[today's date].md`
2. Paste your notes (rough is fine — bullet points, timestamps, fragments all work)
3. Run:
   ```
   /post-call [Account Name] debrief
   ```

**What you'll get**:
- Scorecard scores with specific transcript evidence for each dimension
- Talk-to-listen ratio estimate
- Three moments where a question would have been stronger than a statement
- Standard outputs: call summary, CRM update fields, follow-up email draft, coaching note

**Step 3 — Compare** (8 min): Where did Claude see something you missed? Where did your rep instinct beat the AI? Which gaps surprised you?

The coaching note in the enterprise transcript has a specific opportunity embedded — if the skill catches it, you'll know you're using it correctly.

### In-class exercise B: Proposal generation (10 min)

Open `Course-Materials/sample-rfp.md` (the Meridian Industrial Group RFP). Then run:
```
Task: Generate a first-draft proposal for Meridian Industrial Group

Inputs:
- Course-Materials/sample-rfp.md (the RFP)
- Course-Materials/sample-transcripts/discovery-call-enterprise.md (the discovery call)

Deliver:
- Executive summary tied to their stated priorities
- Solution section mapped to their specific pain points from the discovery call
- Business case using the numbers Sarah mentioned in the call
- Why us vs. Highspot (the competitor they mentioned)

Save as Accounts/Meridian/Meridian-Proposal-Draft-v1.md
```

The coaching principle: a first draft that captures their language and their numbers is more persuasive than a polished template that doesn't.

### In-class exercise C: Deal coaching on a stalled deal (10 min)

*Option A — Your own stalled deal*: Describe a deal that's been stuck in 3-4 sentences (stage, deal size, who you've met, what the pain is, what's blocking it). Paste into Claude chat:
```
I've been working on [Company] for [X weeks].
[Paste your deal context]

Tell me:
1. Top 3 risk factors for this deal not closing
2. Questions I have not yet answered for the buyer
3. What is the likely internal conversation happening on their side right now?
4. What should my next move be?
```

*Option B — Sample stalled deal*: Open `Course-Materials/sample-deal-notes.md` (Thornwood Capital — 35 days stuck in Negotiation). Paste the notes with the same prompt above.

### Module 4 deliverable
- Completed 360° Call Debrief with self-score vs. Claude score comparison
- Post-call summary + follow-up email from a real or sample transcript
- First-draft proposal for Meridian (or your own account)

---

## Module 5: The AI Seller Mindset — Amplifier, Not Crutch (60 min)

**Coaching truth**: The danger is real — if you outsource all your thinking to Claude, you will gradually become less capable, not more. The reps who get the most out of AI in 2026 are the ones who use it to think harder, not to think less. The tasks AI handles well (research, drafting, data entry) are table stakes. The tasks that create competitive advantage are becoming *more human*, not less: complex judgment, genuine curiosity, relationship depth, creative problem-solving.

**What Claude removes**: The 65% of time currently lost to busywork — so you can reinvest it in developing those irreplaceable human skills, not in clearing more items off the task list.

### In-class activity: The AI-Free Debrief (10 min, pairs)

Before the Cowork demo — put devices down. With a partner:
- Tell them everything you know about your best current deal, from memory
- What do you know for certain? What are you assuming? What haven't you actually asked?
- What is the buyer feeling that they haven't said out loud?

The deal that was "prepped by Claude" often has shallow human understanding underneath. That gap is the work.

### In-class exercise A: Full workspace configuration (15 min)

Your workspace folder structure is already set up (this repo). Now add the global instructions:

1. Open `CLAUDE.md` (already exists in the workspace)
2. Verify your 4 fields are filled in: Company, Product, ICP, CRM
3. Add or update the **Sales Motion** and **Qualification Framework** fields with your real methodology

Then set **Cowork global instructions** in Claude Desktop → Settings → Cowork:
```
You are a sales productivity assistant for [Name] at [Company].
Our solution: [one sentence]
Our ICP: [2–3 sentences]
My territory: [geography/segment/industry]
My tone: [e.g., "direct, consultative, no jargon"]
CRM: [system] [connected via MCP: yes/no]
Always format outputs as files, not chat responses.
When preparing meeting briefs, follow the Account Research Skill.
When drafting outreach, follow the Cold Outreach Skill.
When processing calls, follow the Post-Call Skill.
```

### In-class exercise B: Pipeline review (10 min)

**If CRM is connected**:
```
/pipeline-review [today's date]
```

**If CRM is NOT connected** (most of you in the room):
```
/pipeline-review [today's date]
```
When prompted for pipeline data, paste the table from `Course-Materials/sample-pipeline.md`.

Look at the output: which deals trip the at-risk flags and why? What's the coverage ratio? Is there a Knowledge Health pulse at the bottom — any stale files?

### In-class exercise C: The Monday Morning Workflow (10 min)

Copy the workflow from `Course-Materials/monday-morning-workflow.md` into Claude Cowork as a new task. Replace the placeholder account names with 3 real deals.

Manual equivalent: 90–120 minutes. Cowork: 5–8 minutes while you prepare for your first call.

### In-class exercise D: Knowledge health + retro (optional, 10 min)

```
/knowledge-health
```

After a full day of exercises, you'll see which knowledge files are current vs. stale, and any pending gaps. Then, if time permits, run a retro on a deal you closed in the last 90 days:
```
/retro [Account Name] [won or lost]
```
If CRM isn't connected, Claude will ask for basics and run the full retrospective questions — no CRM needed.

### Module 5 deliverable
- Fully configured workspace: CLAUDE.md complete, Cowork global instructions set, all three Skills tested
- Pipeline review output (from sample data or live CRM)
- Optional: CRM connected via `SALESFORCE-SETUP.md`

---

## CRM Connection (Optional — Do After Class)

Follow `SALESFORCE-SETUP.md` for Salesforce, HubSpot, or Dynamics 365.

**If your IT hasn't approved MCP access**: Every skill works without CRM. CRM connection is a force multiplier on a workflow that should already be running. Start with manual input — connect later.

**After class**: Once you're at your desk with your usual IT environment, the connection typically takes 15–20 minutes.

---

## 30-Day Adoption Roadmap

Take this home. One focus area per week.

**Week 1 — Foundation**
Run Claude account research before every call. Time yourself against your pre-course baseline.
Goal: Build the habit of opening Claude before your CRM.

**Week 2 — Outreach**
Deploy your 3-email sequence from Module 3 on 20 new prospects.
Measure open and reply rates against your pre-course baseline.
Refine the `email-drafter` SKILL.md based on what responses tell you.

**Week 3 — Cowork**
Run `/post-call debrief` after every discovery call this week.
Compare your self-scores to Claude's scores. Where is the gap narrowing?
Connect CRM if you haven't yet.

**Week 4 — Optimization**
Use the SPEAR framework on your remaining time sinks — build Skills for anything scoring 3+.
Run `/knowledge-health` — see how much the workspace has improved.
Share your best-performing Skill with one teammate.

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Can't find a skill | Make sure you opened the *folder* (not a file) in Claude Desktop. Skills live in `.claude/skills/`. |
| Output is too generic | Your `CLAUDE.md` needs more context — especially `Product:` and `ICP:`. Fill those in and re-run. |
| CRM errors | Check `SALESFORCE-SETUP.md` troubleshooting section. |
| Skill underperforming | Run `/knowledge-health` — it often surfaces why (missing or stale knowledge files). |
| Prompt gives vague output | Apply the CRISP framework (`Course-Materials/crisp-framework.md`) — the issue is almost always missing Specifics or Format. |
