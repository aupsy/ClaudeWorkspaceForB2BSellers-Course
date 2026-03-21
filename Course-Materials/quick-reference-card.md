# Quick Reference Card — Modern Selling in the Age of AI

*Print this. Put it next to your monitor. Reference it the first week back.*

---

## CRISP Prompt Framework

| Letter | Stands for | What to include |
|--------|------------|-----------------|
| **C** | Context | Who you are, your product, the deal/account situation |
| **R** | Role | What role you want Claude to play ("act as a B2B sales coach") |
| **I** | Instructions | What you want it to do, step by step |
| **S** | Specifics | Actual names, numbers, quotes, dates — no placeholders |
| **F** | Format | How you want the output (bullets, email, scorecard, table) |

**Weak prompt:** *"Write me a cold email to a VP Sales"*
**CRISP prompt:** *"I'm Jordan Rivera at Catalyst Sales Intelligence (AI sales coaching for SDR/AE teams). Write a cold email to Marcus Reid, CRO at Vantage Software — they just announced 8 new SDR hires and Marcus posted last week about pipeline quality vs. volume. Lead with that specific insight, connect it to SDR ramp time as the root problem, and use a 15-minute call CTA. Under 120 words."*

---

## O → E → A Discovery Framework

**Orientation** — Earn the right to ask hard questions
> *"Based on what I've seen, it looks like [specific observation about their situation]. Is that accurate?"*

**Exploration** — Current state → Business impact → What would change
> *"Walk me through what [the problem] looks like today."*
> *"What does that cost you — in revenue, time, or headcount?"*
> *"If that problem went away, what would be different for you?"*

**Advancement** — Summarize, then set next step live
> *"Let me make sure I've got this right: the core problem is [their words]. Is that how you'd put it?"*
> *"What should happen next on your side, and on ours?"*

---

## Self-Coaching Scorecard (1–5 per dimension)

| Dimension | 1 | 3 | 5 |
|-----------|---|---|---|
| Up-front contract | No agenda set | Partial agenda | Clear agenda + time + mutual outcome |
| Insight-led opener | "Tell me about your business" | Used some research | Opened with specific insight that earned engagement |
| Question quality | Feature-telling | Mix of open/closed | All open, hypothesis-driven, evidence-based |
| Business impact uncovered | None | Surface pain only | Quantified impact in buyer's words |
| Stakeholder mapping | Unknown buying process | Know the champion | Full map: EB, champion, blockers, process |
| Next-step close | "I'll follow up" | Date set | Date + agenda + mutual commitment confirmed live |
| Talk-to-listen ratio | >70% talking | ~50/50 | <40% talking |

---

## Skill Invocations (run in Claude Cowork)

| What you want | Command |
|---------------|---------|
| Account research brief before any call | `/account-research [Company]` |
| 1-page call prep briefing | `/call-prep [Account Name]` |
| Personalized outreach email | `/email-drafter [Company] [context]` |
| Post-call summary + CRM + coaching + follow-up | `/post-call [Account Name]` |
| MEDDIC deal score + next actions | `/deal-health [Account Name]` |
| Weekly pipeline snapshot + risk flags | `/pipeline-review [date]` |
| Battle card for a competitor | `/competitive-intel [Competitor]` |
| Win/loss retrospective | `/retro [Account Name] [won or lost]` |
| Knowledge freshness dashboard | `/knowledge-health` |

---

## Top 5 Prompts (copy-paste ready)

**1. Pre-call research (Claude Projects)**
```
Create a one-page account brief for [Company]. Include: business overview,
key executives, recent news (last 90 days), likely pain points given our
ICP, and an insight-led opening talk track for a first call.
```

**2. Discovery question generator**
```
Here are my notes on [Company]: [paste].
Generate 10 discovery questions a highly prepared rep would ask [Title]
in a 30-minute intro call. Reference specific details from the notes.
```

**3. Insight-led cold email**
```
Write a cold email to [Name] at [Company].
Lead with a specific, verifiable event from the last 90 days.
Connect it to a business pain it creates. One sentence on how we solve it.
CTA: 15-minute call. Under 120 words. No "Hope this finds you well."
```

**4. Post-call processing**
```
Here are my raw notes from my [Company] call today: [paste].
Give me: 1) clean CRM opportunity note, 2) MEDDIC scorecard with gaps,
3) three coaching observations, 4) follow-up email to [Name].
```

**5. Stalled deal coaching**
```
I've been working on [Company] for [X weeks]. [Paste deal context.]
Tell me: top 3 risk factors, questions I haven't answered for the buyer,
what's likely happening internally on their side, and my recommended next move.
```

---

## SPEAR Workflow Score (identify what to automate)

| Letter | Question | Score 1–5 |
|--------|----------|-----------|
| **S** Standardized | Does this follow the same steps every time? | |
| **P** Prompt-heavy | Does it require a lot of typing / template work? | |
| **E** Error-prone | Do you make mistakes when you do it manually? | |
| **A** Accounting for time | Does it take >15 minutes per instance? | |
| **R** Reusable | Do you need to do this >3x per week? | |

**Score 3+ = worth building into a Skill**

---

*Modern Selling in the Age of AI | Keep this card at your desk*
