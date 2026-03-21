# Ford Motor Company — Pre-Call Account Notes
*For use with Lesson 3: "Discovery Questions That Show You've Done the Work"*

---

## Demo Prompt to Use (show on screen — do not run live)
```
Here are my account notes on Ford Motor Company: [paste below].
Generate 10 discovery questions a highly prepared sales rep would ask the VP of AI & Data
in a 30-minute intro call. Questions should reference specific details from these notes
and probe for problems we can actually solve. Do not use generic discovery questions.
```

> **Facilitator note:** This lesson has no live demo — show the prompt and the notes on screen,
> then read out 2–3 of the questions Claude would produce. The audience's reaction is usually
> "I'd never have thought to ask that." That's the moment. Move on.

---

## Account Notes to Paste with the Prompt

**Company**: Ford Motor Company
**Contact**: James Whitfield, VP of AI & Data
**Deal stage**: Pre-discovery / first call scheduled

**What we know about Ford's AI situation:**
- Announced aggressive autonomous driving timeline — ADAS level 4 vehicles targeting volume production in 2027
- Current AI training infrastructure is Azure-based (NDv4 GPU clusters), but internal teams have flagged 6-week wait times for GPU allocation during peak training cycles
- Their published earnings call (Q3 2025) included the CFO flagging AI infrastructure costs as "growing significantly faster than budgeted" — $47M spend vs $35M plan
- James Whitfield published a LinkedIn post three weeks ago about data sovereignty concerns: "We need to control our training data. Shipping it to the cloud creates IP exposure we're not comfortable with."
- They have a board presentation in September where the autonomous driving team needs to demonstrate a new accuracy benchmark — creating a hard deadline for compute capacity

**What we don't know yet (gaps to probe):**
- Whether the Azure relationship is strategic (enterprise agreement, executive sponsorship) or just inherited infrastructure
- Whether James has budget authority or needs CFO sign-off
- What the internal debate looks like: cloud vs. on-prem vs. hybrid
- Who else is evaluating this (AMD presented last quarter)
- Whether the September board deadline is real urgency or a soft milestone

**Our relevant capabilities:**
- On-prem H200 GPU clusters with 5x faster training vs NDv4 baseline
- Data sovereignty by design — no data leaves customer environment
- Reference customers: BMW (autonomous), John Deere (agricultural AI), Komatsu (industrial autonomy)

---

## What Good Discovery Questions Look Like (for facilitation reference)

The prompt should produce questions like:
- *"Your Q3 earnings call mentioned AI infrastructure costs running 35% over budget. Is that a supply problem — not enough compute — or an efficiency problem — the compute you have isn't fast enough?"*
- *"James, you wrote about data sovereignty concerns three weeks ago. Is that a regulatory concern, an IP concern, or both — and is that what's driving the on-prem conversation?"*
- *"The September board presentation — is the benchmark you need to hit dependent on having more compute, or could you hit it with the Azure setup if the wait time problem went away?"*

Compare that to a rep who walks in and asks: *"Tell me about your biggest AI challenges this year."*

**Key teaching line:** *"The goal isn't to impress them. It's to make them feel understood. Claude gets you to that place in 2 minutes."*

---

*Source file for NVIDIA Cowork Demo | Lesson 3: Discovery Prep*
