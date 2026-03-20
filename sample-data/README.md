# Sample Dataset — Catalyst Sales Intelligence
## HubSpot Trial Setup for Course Demos

This folder contains everything needed to populate a HubSpot trial account and run a pre-configured Claude workspace for the course. Estimated setup time: 30–45 minutes.

---

## What's in Here

```
sample-data/
├── README.md                          ← you are here
├── CLAUDE-demo.md                     ← pre-filled CLAUDE.md (copy this over the root CLAUDE.md)
├── hubspot-import/
│   ├── IMPORT-GUIDE.md                ← step-by-step HubSpot import walkthrough
│   ├── companies.csv                  ← 14 company records (import first)
│   ├── contacts.csv                   ← 24 contact records (import second)
│   ├── deals.csv                      ← 14 deal records (import third)
│   └── deal-notes.md                  ← notes to paste into HubSpot manually after import
└── lightning-talk/
    └── hubspot-subset.md              ← lightning talk guide — which demos need HubSpot
```

---

## Setup Sequence

1. **Copy CLAUDE-demo.md** → overwrite the root `CLAUDE.md` (or keep for reference)
2. **Follow `hubspot-import/IMPORT-GUIDE.md`** to populate HubSpot
3. **Connect HubSpot MCP** (see IMPORT-GUIDE.md step 5)
4. **Test** with the validation queries in IMPORT-GUIDE.md step 6

---

## Fictional Universe

**Seller**: Jordan Rivera, Account Executive at **Catalyst Sales Intelligence**
**Product**: AI-powered sales coaching and revenue intelligence platform — reduces the top/bottom performer productivity gap for SDR and AE teams.
**ICP**: Mid-market B2B companies, 150–2000 employees, 20–150 reps, VP Sales or CRO as economic buyer.

All 14 accounts are fictional. Contact names, emails, and deal details are invented for training purposes. The 12 active pipeline deals match `Course-Materials/sample-pipeline.md` exactly — same companies, same ARR amounts, same stages — so existing course materials and HubSpot data are always in sync.

---

## Module-to-Data Map

| Course Module | Exercise | Use This Data |
|--------------|----------|---------------|
| Module 1 | Account brief for live prospect | Any company in HubSpot; try Cascadia Health Systems |
| Module 2 | Discovery prep + roleplay | Vantage Software (Marcus Reid, CRO) |
| Module 2 | Call prep skill demo | Meridian Industrial Group |
| Module 3 | Email drafter | Keystone Manufacturing or Clearpath Solutions |
| Module 4 | Post-call synthesis | `Course-Materials/sample-transcripts/discovery-call-midmarket.md` (Vantage) |
| Module 4 | Enterprise post-call | `Course-Materials/sample-transcripts/discovery-call-enterprise.md` (Meridian) |
| Module 4 | Deal coaching (stalled deal) | Thornwood Capital — full notes in `deal-notes.md` and `Course-Materials/sample-deal-notes.md` |
| Module 4 | Proposal generation | `Course-Materials/sample-rfp.md` + Meridian deal context |
| Module 5 | Monday morning workflow | Full pipeline (all 12 open deals in HubSpot) |
| Module 5 | Pipeline review skill | `/pipeline-review` with HubSpot connected |
| /deal-health | MEDDIC scoring | Thornwood Capital (at-risk) or Vantage Software (strong) |
| /retro | Win retrospective | Pinnacle HR Tech (Closed Won) |
| /retro | Loss retrospective | DataFlow Systems (Closed Lost — lost to Gong) |

---

## At-Risk Deals (pre-flagged for exercises)

The pipeline is designed so `/pipeline-review` naturally flags these four issues — same as `Course-Materials/sample-pipeline.md`:

1. **Thornwood Capital** — Negotiation stage, stuck 35 days, no contact in 26 days
2. **Northgate Logistics** — Close date March 15 (past due), no activity in 16 days
3. **Coverage gap** — Pipeline at 2.4x, below the 3x target
4. **Clearpath Solutions** — No next call scheduled after initial discovery; momentum risk

---

## Lightning Talk

See `lightning-talk/hubspot-subset.md` for which of the 5 lightning talk lessons use HubSpot vs. the existing pasted-context lesson files.

---

*All data is fictional. Companies, individuals, and deal details are invented for course use only.*
