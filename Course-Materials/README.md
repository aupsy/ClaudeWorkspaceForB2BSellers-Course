# Course Materials

Practice materials and reference frameworks for all 5 modules. Use these when you don't have real data available — or as a supplement to understand what good outputs look like.

---

## Reference Frameworks (all modules)

| File | Used in | What it is |
|------|---------|-----------|
| `crisp-framework.md` | M1–M5 | The CRISP prompt framework — audit any prompt that gives vague output |
| `spear-framework.md` | M2 | Worksheet for identifying which workflows should become Skills |
| `discovery-roleplay-prompt.md` | M2 | Claude-as-sparring-partner template for discovery call practice |
| `self-coaching-scorecard.md` | M4 | The 7-dimension call scoring rubric for the 360° Call Debrief |
| `monday-morning-workflow.md` | M5 | Cowork task template for the Monday Morning Workflow demo |
| `ready-to-use-prompts.md` | All | 20 ready-to-use sales prompts organized by workflow |

---

## Sample Data — for sellers who don't have their own data yet

### Module 3: Personalization Audit

| File | What it is | How to use |
|------|-----------|-----------|
| `sample-cold-emails.md` | 10 fictional cold emails at varying quality levels (excellent → poor) | Paste into Claude chat with the Personalization Audit prompt from `ready-to-use-prompts.md` |

### Module 4: Post-Call + Proposal + Deal Coaching

| File | What it is | How to use |
|------|-----------|-----------|
| `sample-transcripts/discovery-call-enterprise.md` | 47-min discovery call, Meridian Industrial Group — VP Sales + Sales Ops, $2.1M pain, coaching opportunity embedded | Copy to `Accounts/Meridian/`, run `/post-call Meridian debrief` |
| `sample-transcripts/discovery-call-midmarket.md` | 31-min call, Vantage Software — CRO, clean structure, clear urgency | Copy to `Accounts/Vantage/`, run `/post-call Vantage` |
| `sample-rfp.md` | Fictional RFP from Meridian Industrial Group — AE ramp time problem, ties back to the enterprise transcript | Use with enterprise transcript for Proposal Generation exercise |
| `sample-deal-notes.md` | CRM-style notes for Thornwood Capital — $95K, stuck 35 days in Negotiation, legal stall | Paste with deal coaching prompt for Module 4 Deal Coaching exercise |

### Module 5: Pipeline Review

| File | What it is | How to use |
|------|-----------|-----------|
| `sample-pipeline.md` | 12-deal pipeline, 2.4x quota coverage, 3 at-risk flags | Paste the table when `/pipeline-review` asks for pipeline data |

### Module 1: Sample Product Knowledge

| File | What it is | How to use |
|------|-----------|-----------|
| `Knowledge/product/sample-product-overview.md` | Pre-filled fictional product overview (Apex Sales Intelligence) | Opens automatically if you haven't run `/hydrate` yet — replace with your real product by running `/hydrate website [your URL]` |

---

## Quick Setup for Each Module Exercise

**Module 2 — Discovery Roleplay**:
1. Generate an account brief: `/account-research [any account]`
2. Open `discovery-roleplay-prompt.md`
3. Copy the prompt into Claude chat, paste in 3–5 context bullets from the brief
4. Run the roleplay — get scored at the end

**Module 3 — Personalization Audit**:
1. Option A: Paste your own 10 sent emails
2. Option B: Paste from `sample-cold-emails.md`
3. Use the audit prompt from `ready-to-use-prompts.md` (#6)

**Module 4 — 360° Debrief**:
1. Create `Accounts/Meridian/` (or your own account folder)
2. Copy `sample-transcripts/discovery-call-enterprise.md` into it
3. Run `/post-call Meridian debrief`
4. Compare Claude's scorecard to your self-score

**Module 4 — Proposal**:
1. Drop `sample-rfp.md` and `sample-transcripts/discovery-call-enterprise.md` into your workspace
2. Run the proposal generation prompt from `ready-to-use-prompts.md` or `COURSE.md`

**Module 4 — Deal Coaching**:
1. Open `sample-deal-notes.md`
2. Paste into Claude chat with the deal coaching prompt at the bottom of the file

**Module 5 — Pipeline Review**:
1. Run `/pipeline-review [today's date]`
2. When prompted, paste the table from `sample-pipeline.md`

---

## After the Course

These materials are for practice. Replace with real data as you go:
- Add real call notes to `Accounts/[Your Account]/` and run `/post-call`
- Replace `sample-product-overview.md` with your real product via `/hydrate website [URL]`
- Connect CRM via `SALESFORCE-SETUP.md` to skip manual pipeline pasting
