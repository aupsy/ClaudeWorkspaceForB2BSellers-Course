# SPEAR Framework — Skills Identification Worksheet

Use this to identify which of your weekly workflows should become a Claude Skill. Any workflow scoring 3 or more out of 5 is worth building.

---

## The Five Criteria

| Letter | Criteria | Question |
|--------|---------|---------|
| **S** | **Standardized** | Does this workflow follow the same pattern every time? |
| **P** | **Prompt-heavy** | Am I re-explaining the same context to Claude repeatedly? |
| **E** | **Error-prone** | Does manual execution introduce inconsistencies I wouldn't want a buyer to see? |
| **A** | **Accounting for time** | Does this consume 30+ minutes per week? |
| **R** | **Reusable** | Would more than one rep on my team benefit from this? |

---

## Scoring Your Workflows

For each workflow you're considering, score each criterion: **0** (No) or **1** (Yes).

| Workflow | S | P | E | A | R | Total | Build? |
|----------|---|---|---|---|---|-------|--------|
| Pre-call research brief | | | | | | | |
| Post-call CRM update | | | | | | | |
| Follow-up email after demo | | | | | | | |
| Pipeline review for manager | | | | | | | |
| Cold outreach sequence | | | | | | | |
| Proposal first draft | | | | | | | |
| QBR narrative | | | | | | | |
| [Your workflow] | | | | | | | |
| [Your workflow] | | | | | | | |
| [Your workflow] | | | | | | | |

**Score 3+**: Build a Skill. The ROI is clear.
**Score 2**: Consider building. The benefit is moderate.
**Score 0–1**: Skip. One-off tasks don't justify Skill maintenance.

---

## What Goes in a Skill

A Skill is a SKILL.md file in `.claude/skills/[skill-name]/` that contains:

1. **Context**: What Claude needs to know about your company, product, or process to do this right
2. **Steps**: The exact sequence Claude follows — numbered, specific
3. **Output format**: What the deliverable looks like (sections, length, tone)
4. **Edge case handling**: What to do if key inputs are missing
5. **Examples** (optional): One good example output that anchors Claude's quality bar

The `/account-research` and `/email-drafter` Skills in this workspace are good reference models. Open either one in the file tree to see the structure.

---

## What a Built Skill Saves You

| Workflow | Manual Time | With Skill | Weekly Savings (5 calls/wk) |
|----------|------------|-----------|----------------------------|
| Pre-call research | 30–45 min | 2 min | 2.5–3.5 hrs |
| Post-call processing | 60–90 min | 5 min | 4–7 hrs |
| Follow-up email | 15–20 min | 2 min | 1–1.5 hrs |
| Pipeline review | 20–30 min | 3 min | 17–27 min/wk |

The compound effect: reps who build 3–4 well-maintained Skills recover 6–10 hours per week. That time is meant to go back into discovery conversations, not into more task processing.

---

## Building Your First Skill (After Class)

1. Pick the workflow that scored highest
2. Open `.claude/skills/account-research/SKILL.md` as a template
3. Copy it to `.claude/skills/[your-workflow-name]/SKILL.md`
4. Replace each section with your workflow's specifics
5. Test it on one real task before sharing with your team
6. If it scores 5 on SPEAR ("R" = Reusable), share the SKILL.md with teammates

---

*For use in Module 2 of Modern Selling in the Age of AI.*
