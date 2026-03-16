---
name: retro
description: Run a structured win/loss retrospective when an opportunity closes. Extracts competitive, product, process, messaging, and pricing insights from the deal. Maps them to specific Knowledge/ files and optionally drafts those updates — so every closed deal improves the team's shared knowledge.
compatibility: claude-code
metadata:
  category: self-improvement
  invocation: /retro [Account Name] [won|lost]
---

# Retro Skill

Run after every closed deal (won or lost) to capture what you learned and feed it back into the Knowledge base.

## Invocation

```
/retro Acme Corp
/retro Acme Corp won
/retro Acme Corp lost
```

The outcome (won/lost) can be provided upfront or discovered from CRM data.

---

## Step 1: Query CRM for the Closed Opportunity

Fetch the most recently closed opportunity for the account:

```soql
SELECT Id, Name, StageName, Amount, CloseDate, Probability,
       Account.Name, Account.Industry,
       CloseReason__c, CompetitorLost__c, LostReason__c,
       (SELECT Id, Subject, ActivityDate, Description FROM Tasks
        ORDER BY ActivityDate DESC LIMIT 20),
       (SELECT Id, Name, Title, Role FROM OpportunityContactRoles)
FROM Opportunity
WHERE Account.Name LIKE '%{account_name}%'
  AND IsClosed = true
ORDER BY CloseDate DESC
LIMIT 1
```

Determine won/lost from `StageName` (e.g., "Closed Won" vs. "Closed Lost") if not provided at invocation.

If no closed opportunity is found: ask the rep to confirm the account name or paste the opportunity ID directly.

---

## Step 2: Read Local Account Context

Check for `Accounts/[Account Name]/` folder:
- `Account-Overview.md` — stakeholders, relationship history, deal narrative
- `Engagement-Log.md` — qualitative notes across the sales cycle
- `Open-Items.md` — any outstanding items at close

Note any competitors or themes mentioned that should inform the retrospective questions.

---

## Step 3: Read Reference Knowledge

Before asking questions, read:
- The appropriate template: `Win-Loss/win-template.md` (won) or `Win-Loss/loss-template.md` (lost)
- Any battle card in `Knowledge/compete/` for competitors referenced in CRM data or account notes — note the current state so you can identify updates after the conversation

---

## Step 4: Ask Structured Retrospective Questions

Present these conversationally — the goal is specific, actionable insight, not generic deal review platitudes.

### For a WON deal:

```
Quick retro on [Account Name] — congratulations on the win. A few questions to capture
what worked so we can replicate it and update the playbook. Answer as briefly or as
deeply as you like.

1. Top 3 reasons we won — be specific. Not "great relationship" but what we actually
   did or had that materially tipped it.

2. Who was our champion and how did they show up? Did they pass the test — did they
   get us EB access, share internal dynamics, coach us on the decision process?

3. Was there a competitor in play? What tipped it our way against them specifically?

4. What almost killed this deal? The near-miss moments — what nearly lost it?

5. One tactic, question, or moment in this deal that every rep on the team should know.

6. Reference customer potential — would they talk to other prospects? For what
   conversation or use case?
```

### For a LOST deal:

```
Quick retro on [Account Name]. No judgment — these are the ones we learn the most from.

1. What did they tell us officially? What do you actually think happened?

2. Walk me through MEDDIC — where were we weakest?
   Metrics / Economic Buyer / Decision Criteria / Decision Process / Pain urgency / Champion

3. Who won and what do you know about why they won? What did they offer or do that
   we couldn't match?

4. In retrospect — was this a winnable deal? What would have had to be different for
   us to win?

5. What early warning signs would you now recognize in a similar deal?

6. One thing you'd do differently in the first 30 days of a similar opportunity.
```

---

## Step 5: Tag Each Insight

As the rep answers, tag each insight with one or more of:

| Tag | What it captures |
|-----|-----------------|
| `[competitive]` | New intel about a specific competitor's behavior, pricing, or positioning |
| `[product-gap]` | Feature or capability we lacked that affected the deal outcome |
| `[process]` | Discovery, qualification, or execution pattern that helped or hurt |
| `[messaging]` | Framing, positioning, or language that worked or failed with this buyer |
| `[pricing]` | Pricing, packaging, or deal structure insight |
| `[objection]` | A new objection pattern or a known objection handled in a new way |
| `[play]` | A specific play or sequence that should be added to or updated in Sales Plays |

---

## Step 6: Map Insights to Knowledge/ Files

After tagging, show a mapping table **before writing anything**:

```
Based on what you shared, here's how I'd map these insights to Knowledge/ updates:

| Insight (tagged) | Target file | What to add/change |
|-----------------|-------------|-------------------|
| [competitive] [Competitor] now offers X | Knowledge/compete/[Competitor].md | Add to "Where They Win" and "Landmines" sections |
| [product-gap] Missing Oracle CRM integration | Knowledge/product/Feature-Roadmap.md | Add to customer-requested features |
| [process] EB access at call 3 was decisive | Knowledge/plays/Discovery-Framework.md | Reinforce Economic Buyer section |
| [messaging] Financial Services ROI framing landed | Knowledge/plays/Objection-Handling.md | Add vertical-specific framing note |
| [objection] New procurement blocker discovered | Knowledge/plays/Objection-Handling.md | Add objection variant |
| [play] Migration reference story was decisive | Knowledge/plays/Sales-Plays.md | Add proof point to Competitive Displacement play |

Does this mapping look right? Anything to skip or add?
```

Wait for confirmation or adjustment before proceeding.

---

## Step 7: Generate the Retrospective Document

Using the appropriate template as the structural base, generate a fully populated retro document. Save to:
- Won: `Win-Loss/Wins/[Account-Name]-[YYYY-MM-DD].md`
- Lost: `Win-Loss/Losses/[Account-Name]-[YYYY-MM-DD].md`

The document should be more detailed than the template alone — include the tagged insight summary at the top (used by `/knowledge-health` to detect pending updates).

Add a **"Knowledge Updates Triggered"** section at the bottom of the retro:

```markdown
## Knowledge Updates Triggered

| Insight tag | Target file | Status |
|------------|-------------|--------|
| [competitive] ... | Knowledge/compete/[Competitor].md | Pending |
| [product-gap] ... | Knowledge/product/Feature-Roadmap.md | Pending |
| [process] ... | Knowledge/plays/Discovery-Framework.md | Pending |
```

This is the paper trail — `/knowledge-health` reads this table to surface what needs to be done.

---

## Step 8: Offer to Draft Knowledge File Updates

After the retro document is saved:

```
The retro is saved at Win-Loss/[Wins|Losses]/[Account-Name]-[date].md.

I've identified [N] Knowledge/ files that should be updated based on what you shared.
Want me to draft suggested updates for any of these?

[list each file with a one-line description of what to add]

I'll follow the same safety rule as /hydrate: I won't overwrite anything you've
customized — I'll show you the proposed change and you confirm before it's written.
```

For each approved update:
- Draft the change as a `<!-- RETRO INSIGHT — [Account Name] [Date] -->` block
- Show the exact proposed text for review before applying
- Never overwrite existing content — append or insert with the tagged block

---

## Step 9: Update Frontmatter on Modified Files

For every Knowledge/ file actually modified, update its frontmatter:
```yaml
last_updated: [today's date YYYY-MM-DD]
source: retro
```

---

## Output Summary

After the full flow:

```
## Retro Complete — [Account Name] ([Won|Lost])

**Deal**: $[Amount] | Closed [Date] | [Stage]
**Insights captured**: [N] total — [competitive: N] [process: N] [messaging: N] [pricing: N] [objection: N] [product-gap: N] [play: N]
**Retro doc**: Win-Loss/[Wins|Losses]/[Account-Name]-[Date].md
**Knowledge updates**: [N] pending / [N] applied

Run /knowledge-health to see all pending retro insights across deals.
```
