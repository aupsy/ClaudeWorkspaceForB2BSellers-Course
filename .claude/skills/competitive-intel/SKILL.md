---
name: competitive-intel
description: Pull competitive battle card context for any competitor. Returns positioning, strengths/weaknesses, landmine questions, and how to handle their attacks on us.
---

# Competitive Intel Skill

Get battle card context for a competitor, fast. Usage: `/competitive-intel [Competitor Name]`

## Instructions

When invoked with a competitor name:

### Step 1: Find the Battle Card

Look in `Knowledge/compete/` for a file named `[Competitor].md` or similar. If found, read it fully.

### Step 2: Check Freshness

Note when the battle card was last updated. If it's more than 90 days old, flag it as potentially stale.

### Step 3: Check for Any Account Context

If the user also mentions an account name (e.g., "competitive-intel Competitor Corp for Acme deal"), read the relevant account folder to understand the specific context of the competitive situation.

### Step 4: Generate the Briefing

**If the battle card exists**, generate a focused briefing:

---

## Competitive Intel: [Competitor Name]
*Battle card last updated: [date] | [🟢 Current / 🟡 Verify — >90 days old / 🔴 Outdated — >6 months]*

### Who They Are
[2-3 sentences: their positioning, market presence, typical buyer]

### Where We Win vs. Them

| Our Strength | Their Gap | How to Articulate It |
|-------------|-----------|---------------------|
| [Advantage 1] | [Their weakness] | "[What to say]" |
| [Advantage 2] | [Their weakness] | "[What to say]" |
| [Advantage 3] | [Their weakness] | "[What to say]" |

**Best proof point**: [Customer who chose us over them + headline stat]

### Where They Win vs. Us

[Be honest — where are they genuinely strong? Include how to respond.]

| Their Strength | How to Respond |
|---------------|---------------|
| [Strength 1] | [Counter-positioning] |
| [Strength 2] | [Counter-positioning] |

### Landmine Questions to Plant

Questions that reveal their weaknesses without sounding like an attack:
- "[Question 1]"
- "[Question 2]"
- "[Question 3]"

### What They Say About Us (and How to Respond)

| Their Attack | Your Response |
|-------------|--------------|
| "[Their claim]" | "[Counter]" |
| "[Their claim]" | "[Counter]" |

### How to Compete

[3 tactical tips specific to beating this competitor, based on what's worked]

1. [Tactic 1]
2. [Tactic 2]
3. [Tactic 3]

---

**If no battle card exists**:

"I don't have a battle card for [Competitor] yet. Let me do some quick research and then we can build one together."

Then:
1. Use web search to research the competitor (their website, G2 reviews, recent news, positioning)
2. Generate a preliminary battle card using the `_competitor-template.md` format
3. Save it to `Knowledge/compete/[Competitor].md`
4. Ask the rep: "Can you fill in what you know from actual competitive encounters? That's the most valuable part."

---

### Step 5: Offer Next Steps

"Anything specific about this competitive situation I should know? For example:
- What are they claiming in this deal?
- What did the prospect say about [Competitor]?
- Do you want me to draft a response to a specific attack they made?"

### Step 6: Offer to Update the Battle Card

After handling any deal-specific questions, offer to update the battle card if either:
- The battle card was flagged as stale (🟡 or 🔴 in Step 2), OR
- The rep mentioned anything new about the competitor during the conversation

```
One more thing — [this battle card is [X] days old / you mentioned [new intel about Competitor]].
Want me to draft an update to the battle card with what you've shared?

I'll follow the same safety rule as /hydrate: I'll show you the proposed change as a
<!-- RETRO INSIGHT --> block before writing anything, and you confirm before it goes in.

Keeping this current helps the next rep who runs into [Competitor] in a deal.
```

If the rep confirms:
- Draft the proposed change as a `<!-- RETRO INSIGHT — Manual update [YYYY-MM-DD] -->` block
- Show the exact text for review
- After approval, apply the edit and update `last_updated` in the frontmatter to today's date
