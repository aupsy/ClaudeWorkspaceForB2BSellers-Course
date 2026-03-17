---
name: post-call
description: Process a call transcript or rough notes into a structured call summary, CRM update suggestions, follow-up email draft, and one coaching note. Supports a 'debrief' mode that scores the call against the Self-Coaching Scorecard for the 360° Call Debrief exercise. No CRM required.
compatibility: claude-code
metadata:
  category: pipeline-velocity
  invocation: /post-call [Account Name] | /post-call [Account Name] debrief
---

# Post-Call Skill

Convert raw call notes or a transcript into everything you need to advance the deal — in under 2 minutes.

**Standard mode**: `/post-call [Account Name]`
**Debrief mode** (360° scorecard analysis): `/post-call [Account Name] debrief`

---

## Debrief Mode

When invoked with the `debrief` keyword, run the Self-Coaching Scorecard analysis **before** the standard outputs. Read `Course-Materials/self-coaching-scorecard.md` for the full scoring rubric.

Score each of the 7 dimensions (1–5) with specific evidence from the transcript:

```
## 360° Call Debrief — [Account Name] — [Date]

| Dimension | Score | Evidence from call |
|-----------|-------|--------------------|
| Up-front contract | /5 | [what was or wasn't said] |
| Insight-led opener | /5 | [opening line or approach] |
| Question quality | /5 | [strongest and weakest question] |
| Business impact uncovered | /5 | [what was or wasn't quantified] |
| Stakeholder mapping | /5 | [what's known/unknown about the committee] |
| Next step close | /5 | [how the call ended] |
| Talk-to-listen ratio | /5 | [estimated % — note: rough estimate from transcript] |

**Total**: [sum]/35

**3 moments where a question would have been stronger than a statement**:
1. [Timestamp or context + the statement made + suggested question instead]
2. [...]
3. [...]

**Next step assessment**: [Was it committed or vague? Specific date + agenda confirmed?]

**One coaching note**: [The single most important thing to improve in the next call]
```

Then continue with the standard outputs below (Steps 3–8).

---

## Instructions

### Step 1: Find the Input

Check `Accounts/[Account Name]/` for the most recently modified file containing call content. Look for files named like:
- `call-notes-*.md`
- `transcript-*.md`
- `*-call.md`
- Any `.txt` file added today

**If no file is found**, ask:

```
I don't see call notes or a transcript in Accounts/[Account Name]/.

You can:
1. Paste your notes directly here (rough bullets, timestamps, fragments are all fine)
2. Drop the transcript file into Accounts/[Account Name]/ and re-run /post-call

What format were your notes from? (Gong/Chorus export, Zoom transcript, manual notes)
```

### Step 2: Parse the Content

Accept any format — structured or unstructured:
- **Gong/Chorus transcript**: timestamped speaker turns
- **Zoom transcript**: speaker-labeled paragraphs
- **Rough notes**: bullet points, partial sentences, abbreviations
- **Email recap someone sent**: prose summary

Read the full content before summarizing. Do not assume — pull directly from what was said.

### Step 3: Extract and Structure

Identify and organize:

**Pain points**
What specific problems did they describe? For each, note:
- The problem in their language (quote them if possible)
- Business impact (quantified if they gave numbers, inferred if not)
- Urgency level (burning platform? nice to have? something in between?)

**Buying signals**
Positive indicators that they're moving toward a decision:
- Specific questions about implementation, timeline, pricing, or integration
- Statements of urgency or readiness
- Internal stakeholders they offered to introduce
- Comparisons to alternatives that favor you

**Objections**
What friction points came up? For each:
- The objection as stated
- How it was handled (if at all)
- Whether it was resolved, deferred, or still open

**Next steps**
Commitments made by both parties:
- What you committed to (send X by Y date)
- What they committed to (pull in Z, make a decision by Y)
- The confirmed next meeting or touchpoint (date, attendees, agenda)

**Deal risks**
What's not yet established that needs to be:
- MEDDIC gaps: missing EB access, unclear decision process, unquantified pain, untested champion
- Competitive exposure (were other vendors mentioned?)
- Timeline or budget uncertainty
- Open questions that weren't answered

**Key quote**
One memorable thing the prospect said — the line that captures the conversation. This goes in the Engagement Log as the anchor for this interaction.

### Step 4: Suggest CRM Updates

Generate a block the rep can paste directly into their CRM:

```
## Suggested CRM Updates — [Account Name] — [Date]

**Stage**: [leave / move to: {next stage}] — Reason: [evidence from call]
**Probability**: [X%] — Rationale: [key signals]
**Next activity**: [type] on [date] with [contact names]
**Close date**: [leave / adjust to {date}] — Reason: [what they said about timeline]

**Opportunity description update** (replace or append):
[2-3 sentences capturing the current state of the deal after this call]

**Key contact notes**:
- [Contact name]: [title] — [key insight about their role, stance, or influence]
- [Contact name]: [anything notable about their engagement]
```

If CRM MCP is configured, offer: "Want me to update the opportunity in Salesforce/HubSpot directly?"

### Step 5: Draft the Follow-Up Email

Write a follow-up email that:
- Opens by referencing something specific from the conversation (not a generic "great speaking with you")
- Confirms the key things discussed (their pain, what you proposed)
- Delivers any materials or information you promised
- States the confirmed next step with specifics (date, time, attendees)
- Has a clear, low-friction CTA if next step isn't confirmed

**Format**: Subject line + body. Under 200 words. Conversational, not stiff.

**Pull from**: the rep's writing style (from sent email history if productivity tools configured), the `Knowledge/product/` context for any solution references, and the account folder for any relationship nuance.

### Step 6: Write the Coaching Note

One strength and one specific improvement — based only on what you can infer from the notes or transcript.

```
## Coaching Note — [Account Name] — [Date]

**What worked**: [specific behavior with evidence from the call]
Example: "You got [Contact] to quantify the problem — '$2.1M in lost deals' gives you a
powerful anchor for the ROI conversation."

**One to sharpen**: [specific gap with a suggested alternative]
Example: "You heard the pain number but didn't go deeper — a follow-up like
'What's an extra month of ramp time worth per AE?' would have strengthened the business case
and given you a number to build the proposal around."
```

Keep it factual. If you can't find evidence for praise or a gap, say so rather than inventing feedback.

### Step 7: Save to Engagement Log

Append the full structured summary to `Accounts/[Account Name]/Engagement-Log.md`:

```markdown
---

## Call — [Date] — [Type: Discovery / Demo / Negotiation / etc.]

**Participants**: [Rep name] + [Prospect names and titles]
**Duration**: [if available]

**Summary**: [2-3 sentence recap of where the deal stands after this call]

**Key quote**: "[Most memorable thing the prospect said]"

### Pain Points
[structured list]

### Buying Signals
[structured list]

### Objections
[structured list]

### Next Steps
**We owe them**: [list]
**They owe us**: [list]
**Next meeting**: [date + attendees + confirmed agenda if known]

### Deal Risks
[structured list]
```

### Step 8: Deliver the Summary

Output the complete summary in this order:
1. Call Summary (structured notes)
2. CRM Update Block
3. Follow-Up Email (subject + body)
4. Coaching Note

Close with:
```
Engagement log updated at Accounts/[Account Name]/Engagement-Log.md.

Next step confirmed: [what they committed to / what you committed to].

[If CRM is configured]: Want me to push the CRM updates to Salesforce/HubSpot directly?
[If CRM is not configured]: When you're ready, the CRM Update Block above is formatted to paste directly into your opportunity record.
```

---

## Notes on Input Quality

**Rough notes produce rough outputs.** The quality of the post-call summary scales directly with the specificity of your notes. Even a bullet like "asked about timeline → Q3" is more useful than nothing.

**Timestamps help but aren't required.** If your transcript has them, the skill uses them to identify the sequence of the conversation (late-call objections vs. early-call ones signal different things).

**The coaching note is most useful on transcripts.** On rough notes, the skill can only coach on what was written down — missed questions or weak probes that didn't make it into the notes won't appear. For regular coaching value, record calls and use the transcript.
