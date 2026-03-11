---
name: qbr-prep
description: Generate a QBR (Quarterly Business Review) narrative and agenda for a customer. Pulls from account history, product roadmap, and engagement logs.
invocation: /qbr-prep
example_usage: /qbr-prep Acme Corp
---

# QBR Prep Skill

Generate a QBR narrative and agenda for any customer account. Usage: `/qbr-prep [Account Name]`

## Instructions

When invoked with an account name:

### Step 1: Read Account Context

Read the full account folder:
- `Account-Overview.md` — company, stakeholders, deal history, our solution
- `Engagement-Log.md` — all entries to understand the full relationship arc
- `Open-Items.md` — outstanding commitments

### Step 2: Read Product Context

- `Knowledge/product/Feature-Roadmap.md` — recently shipped features and coming soon items relevant to this account
- `Knowledge/metrics/Definitions.md` — metric definitions for any data references

### Step 3: Ask Clarifying Questions (if needed)

Before generating, ask:
- "What data do you have on their usage/outcomes? (e.g., time saved, leads processed, pipeline generated)"
- "What quarter are we reviewing and what's the period for the next quarter plan?"
- "Who will be in the room? (exec audience vs. practitioner audience changes the tone)"
- "Is there anything sensitive — relationship tension, product gaps — I should know?"

### Step 4: Generate the QBR Document

---

## QBR: [Account Name] — [Quarter] Review
*Prepared by: [Rep name] | Date: [Meeting date]*

---

### Meeting Context

| | |
|-|-|
| **Customer** | [Account name] |
| **Attendees (their side)** | [Names and titles] |
| **Attendees (our side)** | [Names and titles] |
| **Meeting duration** | [e.g., 60 minutes] |

---

### Agenda

| Time | Topic | Owner |
|------|-------|-------|
| 0-5 min | Welcome and introductions | [Rep] |
| 5-15 min | Quarter in review — results and value delivered | [Rep] |
| 15-25 min | What's next — product roadmap and upcoming features | [Rep] |
| 25-40 min | [Their goals / initiatives for next quarter] | [Customer] |
| 40-50 min | Mutual success plan for Q[X] | Both |
| 50-60 min | Open discussion and Q&A | Both |

---

### Section 1: Quarter in Review

**Relationship snapshot**:
[1-2 sentences: how long we've been working together, what we set out to accomplish]

**Commitments we made last quarter** (and how we delivered):
| Commitment | Status | Notes |
|-----------|--------|-------|
| [Commitment 1] | ✅ Delivered / ⚠️ Partial / ❌ Missed | [Context] |
| [Commitment 2] | | |

**Value delivered this quarter**:
[Lead with outcomes, not features — use their metrics if available]

- [Outcome 1 — e.g., "Processed X leads with a Y% qualification rate, above the Z% benchmark"]
- [Outcome 2 — e.g., "Reduced research time for their team from X hours to Y hours per week"]
- [Outcome 3]

**Usage and adoption highlights**:
[Relevant usage data — active users, feature adoption, volume metrics]

**Challenges and what we're doing about them**:
[Honest acknowledgment of any problems, with your resolution plan — don't hide these; proactively addressing them builds trust]

---

### Section 2: What's Coming

**Recently shipped** (relevant to their use case):
- [Feature 1]: [What it does and why it matters to them]
- [Feature 2]: [What it does and why it matters to them]

**Coming soon** (next 90 days):
- [Feature 1]: Expected [timeframe] — [relevance to their goals]
- [Feature 2]: Expected [timeframe]

**How this maps to their goals**:
[Connect roadmap to their specific strategic priorities from Account-Overview.md]

---

### Section 3: Their World — Next Quarter

[Prep questions to lead this section — you want to understand their goals and challenges for the next quarter so you can position appropriately]

Questions to drive this conversation:
- "What are your team's top 3 priorities for Q[X]?"
- "What does success look like for you by [end of next quarter]?"
- "Are there any new initiatives or changes in your business we should know about?"
- "What's your biggest concern heading into the next quarter?"

---

### Section 4: Mutual Success Plan

**Their goals for Q[X]**:
- [Goal 1 — fill in based on the discussion above]
- [Goal 2]

**How we'll support them**:
- [Support 1 — specific commitments from our side]
- [Support 2]

**Expansion opportunity** (if applicable):
[If there's a natural expansion play — additional seats, new module, adjacent team — introduce it here as a question, not a pitch]
"You mentioned [pain/goal] — is that something you'd want to address in Q[X]? We have a few customers who've tackled exactly this using [capability]."

**Confirmed next steps**:
| Action | Owner | Due by |
|--------|-------|--------|
| [Action 1] | [Name] | [Date] |
| [Action 2] | [Name] | [Date] |

---

### Rep Notes (not shared with customer)

[Internal prep notes — what you're trying to learn, what you're trying to advance, any concerns to watch for]

---

### Step 5: Offer Refinement

"Here's your QBR framework. A few things to customize before the meeting:
- Fill in Section 3 (their world) based on what you know or learn in the meeting
- Add any usage data you have from the Customer Success team
- Would you like me to also draft an email to send the agenda in advance?"
