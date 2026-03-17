# The CRISP Prompt Framework

Every great Claude prompt includes five elements. When your output is vague or generic, audit your prompt against CRISP — the problem is almost always a missing element.

---

## The Five Elements

| Letter | Element | Question to ask yourself |
|--------|---------|--------------------------|
| **C** | **Context** | Who are you, what is the situation, what does Claude need to know? |
| **R** | **Role** | What perspective should Claude take? |
| **I** | **Instructions** | What exactly should Claude do, step by step? |
| **S** | **Specifics** | Constraints, style rules, length, tone, what to avoid |
| **F** | **Format** | What should the output look like? |

---

## Example: Cold Email

**Generic prompt** (missing C, R, S, F):
> "Write a cold email to the VP of Sales at Acme Corp about our sales automation software."

**CRISP prompt**:
> "**Context**: Acme just announced a Series C and plans to double their sales team from 40 to 80 AEs in Q2. They use Salesforce and Outreach. The VP of Sales is Lisa Chen — she posted on LinkedIn last week about the challenge of scaling onboarding without losing quality.
>
> **Role**: Consultative enterprise AE who communicates without jargon and leads with insight.
>
> **Instructions**: Write a cold email that opens with the Series C + headcount expansion as the trigger, connects it to the SDR/AE ramp time problem, and ties our 40% ramp reduction stat as the hook.
>
> **Specifics**: Under 150 words. No "Hope this finds you well." No features list. CTA: 15-minute call. Add a P.S. referencing her LinkedIn post.
>
> **Format**: Subject line, email body, P.S. line."

---

## Example: Post-Call Follow-Up

**Generic prompt**:
> "Write a follow-up to my prospect at Meridian."

**CRISP prompt**:
> "**Context**: 45-minute discovery call with Sarah Kowalski, VP Sales at Meridian Industrial Group. She shared that new AE onboarding takes 8–9 months and they lost $2.1M in deals last year due to ramp delays. They're hiring 18 new AEs in Q2. She mentioned a Salesforce migration as a timing concern. Next step: demo with her and the CRO in 2 weeks.
>
> **Role**: Same rep from the call — consultative, not pushy.
>
> **Instructions**: Write a post-call follow-up that confirms what was discussed, references the $2.1M figure and the Q2 hiring timeline, addresses the migration concern briefly, and confirms the demo.
>
> **Specifics**: Under 200 words. Conversational prose, not bullet points. Reference her exact words where possible.
>
> **Format**: Email with subject line, body, sign-off."

---

## CRISP Self-Audit

After writing a prompt, ask:

- [ ] **C**: Does Claude know who the buyer is, what they said, and what the deal context is?
- [ ] **R**: Did I tell Claude what perspective to take, or is it guessing?
- [ ] **I**: Are my instructions specific steps, or one vague ask?
- [ ] **S**: Did I give length, tone, and things to avoid?
- [ ] **F**: Did I specify exactly what the output should look like?

If you check fewer than 4 boxes, rewrite the prompt before running it. The prompt is the skill.

---

*For use in Modules 1–5 of Modern Selling in the Age of AI.*
