---
name: call-prep
description: Generate a 1-page pre-call briefing for any account. Reads account folder, product context, and competitive intel to prepare you for any meeting.
invocation: /call-prep
example_usage: /call-prep Acme Corp
---

# Call Prep Skill

Generate a pre-call briefing for an account. Usage: `/call-prep [Account Name]`

## Instructions

When this skill is invoked with an account name:

1. **Find the account folder**: Look in `Accounts/` for a folder matching the account name (fuzzy match is fine — "Acme" should match "Acme-Corp"). If no folder exists, say so and generate a research-based briefing from public context instead.

2. **Read all account files**:
   - `Account-Overview.md` — company, stakeholders, deal status, pain points
   - `Engagement-Log.md` — read the last 3-5 entries to understand recent history
   - `Open-Items.md` — what's committed, what's open, what they owe us

3. **Check for relevant context**:
   - If a competitor is mentioned in account notes, check `Knowledge/compete/` for the relevant battle card
   - Read `Knowledge/product/Product-Overview.md` for product context relevant to their pain points
   - Check `Knowledge/plays/Discovery-Framework.md` if this is an early-stage call

4. **Generate the briefing** in this format:

---

## Pre-Call Briefing: [Account Name]
*Generated: [Today's date] | Call type: [infer from context]*

### Quick Context (30-second read)
[2-3 sentence summary: who they are, where we are in the deal, what this call needs to accomplish]

### Relationship & Deal Status
- **Stage**: [Current stage]
- **Deal size**: [Estimated ARR]
- **Expected close**: [Close date]
- **Relationship health**: [Green / Yellow / Red — based on recency and sentiment of recent engagement]
- **Champion**: [Name, title] — [1-line on their motivation]
- **Economic Buyer**: [Name, title] — [have we met them? Y/N]

### What Happened Last Time
[3-5 bullet summary of the most recent engagement — key things discussed, tone, what was agreed]

### Open Items Heading Into This Call
**We owe them**:
- [Item 1]
- [Item 2]

**They owe us**:
- [Item 1]
- [Item 2]

### Suggested Agenda
[Draft a 3-5 point agenda based on the stage and open items]

### Key Questions to Ask
[5-7 questions tailored to their situation and where we are in the deal — pull from Discovery Framework if relevant]

### Competitive Watch
[If a competitor is active in this deal: key positioning notes, landmines to avoid, questions to ask]

### What a Good Outcome Looks Like
[Define success for this call — what should we walk away with?]

---

5. **Ask the rep**: "Is there anything specific you want me to focus on or any context I'm missing before the call?"
