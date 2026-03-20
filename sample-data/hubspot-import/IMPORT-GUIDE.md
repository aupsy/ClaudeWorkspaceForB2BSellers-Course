# HubSpot Import Guide
## Populating Your Trial Account with Course Demo Data

---

## Prerequisites

- A HubSpot trial account (free at hubspot.com — no credit card required)
- The 3 CSV files in this folder: `companies.csv`, `contacts.csv`, `deals.csv`
- About 30 minutes

---

## Step 1 — Create a Custom Sales Pipeline

HubSpot's default pipeline stages don't match the course materials. Create a custom pipeline first so deal stages import correctly.

1. In HubSpot, go to **Settings → CRM → Deals → Pipelines**
2. Click **Add Pipeline** → name it: `Catalyst Sales Pipeline`
3. Delete the default stages, then add these in order:

| Stage Name | Probability |
|------------|-------------|
| Discovery | 10% |
| Technical Evaluation | 20% |
| Proposal | 40% |
| Negotiation | 60% |
| Verbal Commit | 80% |
| Closed Won | 100% |
| Closed Lost | 0% |

4. Click **Save**

> **Why custom stages?** The course materials (sample-pipeline.md, deal-notes.md, transcripts) all use these stage names. Keeping them consistent means skills like `/pipeline-review` and `/deal-health` produce output that matches what participants expect.

---

## Step 2 — Import Companies

1. Go to **CRM → Companies**
2. Click **Import** → **Start an Import** → **File from computer**
3. Select `companies.csv`
4. Map columns (HubSpot should auto-map most; verify these):
   - `Company name` → Company Name
   - `Domain name` → Company Domain Name
   - `Industry` → Industry
   - `Number of employees` → Number of Employees
   - `Annual revenue` → Annual Revenue
   - `City` → City
   - `State/Region` → State/Region
   - `Description` → Description
5. Click **Finish Import**

Expected result: **14 companies** created.

---

## Step 3 — Import Contacts

1. Go to **CRM → Contacts**
2. Click **Import** → **Start an Import** → **File from computer**
3. Select `contacts.csv`
4. Map columns:
   - `First name` → First Name
   - `Last name` → Last Name
   - `Email` → Email
   - `Job title` → Job Title
   - `Associated company` → Company Name *(HubSpot uses this to auto-associate)*
   - `Phone number` → Phone Number
   - `LinkedIn URL` → LinkedIn URL
   - `Notes` → Notes *(if field exists, otherwise skip)*
5. On the association step, select **Associate with existing companies by Company Name**
6. Click **Finish Import**

Expected result: **24 contacts** created and associated to their companies.

---

## Step 4 — Import Deals

1. Go to **CRM → Deals**
2. Click **Import** → **Start an Import** → **File from computer**
3. Select `deals.csv`
4. Map columns:
   - `Deal name` → Deal Name
   - `Deal stage` → Deal Stage *(must match the custom stage names exactly)*
   - `Pipeline` → Pipeline *(select "Catalyst Sales Pipeline")*
   - `Amount` → Amount
   - `Close date` → Close Date
   - `Associated company` → Company Name
   - `Associated contact` → Contact Email
   - `Deal description` → Description
5. On the association step, select both company and contact associations
6. Click **Finish Import**

Expected result: **14 deals** created. 12 open deals in various stages, 1 Closed Won, 1 Closed Lost.

> **Note on deal owner:** All deals will import without an owner. After import, go to any deal and assign yourself as owner. For the demo, this is fine — skills work based on deal data, not ownership.

---

## Step 5 — Add Deal Notes Manually

HubSpot's CSV import doesn't support rich activity notes. After import, add the notes from `deal-notes.md` to each deal manually:

1. Go to **CRM → Deals** → open a deal
2. In the activity feed, click **Note**
3. Paste the relevant note from `deal-notes.md`
4. Click **Save Note**

**Priority order** (do these first for the best demo experience):

| Deal | Priority | Why |
|------|----------|-----|
| Thornwood Capital | P0 | Module 4 deal coaching exercise — needs full history |
| Vantage Software | P0 | Module 2 & 4 demo — ties to call transcript |
| Meridian Industrial Group | P1 | Enterprise transcript exercise |
| Northgate Logistics | P1 | At-risk demo — needs "last contact" context |
| All others | P2 | Helpful but not required for core exercises |

---

## Step 6 — Connect HubSpot to Claude Workspace

HubSpot has a native MCP integration:

1. In Claude.ai (or Claude Code), open **Settings → Integrations** or **Connected Apps**
2. Find **HubSpot** and click **Connect**
3. Authorize with your HubSpot trial account credentials
4. Once connected, Claude can query your HubSpot data live

> **Instructor note:** If running this in Claude Code (VS Code extension), configure the HubSpot MCP connector in your `claude_desktop_config.json` or workspace settings. See [HubSpot's MCP documentation](https://developers.hubspot.com/docs/api/overview) for details.

---

## Step 7 — Validate the Setup

Run these queries in Claude chat to confirm data loaded correctly:

**Test 1 — Pipeline query:**
```
Which of my HubSpot deals haven't had activity in the last 10 days?
```
Expected: Thornwood Capital and Northgate Logistics should surface.

**Test 2 — Stage summary:**
```
Summarize my open HubSpot deals by stage and total ARR in each stage.
```
Expected output should match the summary table in `Course-Materials/sample-pipeline.md`.

**Test 3 — Contact lookup:**
```
Who is my primary contact at Vantage Software and what deal are they associated with?
```
Expected: Marcus Reid, CRO, associated with the Vantage Software deal in Technical Evaluation.

**Test 4 — Skills test:**
```
/deal-health Thornwood Capital
```
Expected: MEDDIC analysis flagging weak EB relationship, missing ROI deck, legal silence as top risks.

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Deals won't import — stage not found | Verify stage names in Step 1 match `deals.csv` exactly (case-sensitive) |
| Contacts not associating to companies | On import, select "Associate with existing companies by Company Name"; ensure company names match exactly |
| HubSpot MCP not connecting | Check that your HubSpot trial account has API access enabled (Settings → Integrations → API Key) |
| Close date format error | HubSpot expects MM/DD/YYYY — all dates in `deals.csv` use this format |

---

*All data is fictional. For course use only.*
