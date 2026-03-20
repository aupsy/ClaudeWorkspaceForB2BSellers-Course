# Siemens Energy — Proposal Context Pack
*For use with Lesson 4 Demo: "Proposals That Don't Take All Weekend"*

---

## Demo Prompt to Use in Claude Cowork
> "Using the context below, draft an executive summary section for our proposal to Siemens Energy. It should be 300–400 words, written for Klaus Brandt (CTO), lead with their business outcome (not our product specs), reference the specific pain of 8-week simulation cycles, and position our DGX Cloud POC as the low-risk first step. Close with a clear recommended next action."

---

## Deal Context
- **Account:** Siemens Energy AG
- **HQ:** Munich, Germany (decision-maker team is Munich + Houston)
- **Champion:** Klaus Brandt, CTO
- **Deal value:** $22.1M (3-year contract: DGX Cloud + H200 on-prem cluster)
- **Stage:** Stage 4 – Proposal (proposal due April 4, 2026)
- **Close date:** Q1 2026 (end of March — we're at risk of slipping to Q2)
- **Competing vendor:** AWS (incumbent for their Azure workloads... wait, AWS via their Houston subsidiary)

---

## Siemens Energy Business Context

### What They Do
Siemens Energy is a global energy technology company — gas turbines, wind turbines, grid technology, and green hydrogen. Revenue €34B (FY2025). They are a spin-off from Siemens AG (completed 2020).

### Their AI Strategic Initiative: "Digital Energy Twin"
- **Goal:** Build a real-time digital twin of every gas turbine and wind farm they operate globally
- **Why it matters:** A 1% improvement in turbine efficiency = €340M annual savings across their fleet
- **Current state:** Digital twin runs on a simulation stack built on AWS; model retraining takes **8–12 weeks per cycle**
- **Target state:** Retraining in under 2 weeks; real-time inference at edge (on-turbine sensors)

### Known Pain Points
- 8–12 week retraining cycle means they can only improve the model 4–6x per year; competitors targeting weekly cycles
- AWS costs are $9.2M/year and growing 40% YoY — CFO has flagged this as unsustainable
- Data sovereignty: EU AI Act compliance requires training data for critical infrastructure to remain in EU jurisdiction; AWS eu-west-1 has had compliance questions raised by Siemens legal
- Their ML team (40 engineers in Munich) complains they spend 60% of time waiting for GPU capacity on AWS

---

## Proposed NVIDIA Solution

### Phase 1: DGX Cloud POC (Months 1–3) — $0 additional cost
- Migrate one turbine family model (SGT-800) to DGX Cloud
- Target: reduce retraining from 8 weeks to 12 days
- KPI: demonstrate 3x+ speedup on their actual dataset

### Phase 2: On-Premises H200 Cluster (Months 4–12) — $14.5M
- 8x H200 DGX systems (64 H200 GPUs total)
- Deployed in Siemens Energy data center, Munich (EU data sovereignty compliant)
- NVIDIA AI Enterprise software stack, 3-year support

### Phase 3: Edge Inference Deployment (Year 2) — $7.6M
- NVIDIA IGX Orin modules for on-turbine inference
- Enables real-time anomaly detection without cloud round-trip
- Target: 400 turbines in Year 2, full fleet (2,000+ turbines) by Year 3

---

## Financial Summary
| Component | Year 1 | Year 2 | Year 3 | Total |
|---|---|---|---|---|
| DGX H200 Cluster | $14.5M | — | — | $14.5M |
| NVIDIA AI Enterprise (3yr) | $1.2M | $1.2M | $1.2M | $3.6M |
| Edge Inference (IGX) | — | $4.1M | $3.5M | $7.6M |
| Professional Services | $0.4M | — | — | $0.4M |
| **Total** | **$16.1M** | **$5.3M** | **$4.7M** | **$26.1M** |

*Note: Proposal value being presented is $22.1M (excludes Year 3 edge expansion which is in a separate SOW)*

### ROI Case for Klaus / CFO
- AWS savings: $9.2M/year → $27.6M over 3 years
- Efficiency gain from faster model iteration: estimated €68M–€102M over 3 years (1–1.5% turbine efficiency improvement)
- Net 3-year benefit: $95.6M vs $22.1M investment = **4.3x ROI**

---

## Key Stakeholders
- **Klaus Brandt (CTO)** — Decision-maker; wants to own the AI transformation story; risk-averse, wants proof before full commitment → DGX Cloud POC is the right opener
- **Helga Fischer (CFO)** — Will scrutinize 3-year TCO vs AWS; needs clear payback period (our math: 26 months)
- **Dr. Ahmed Mansour (Head of AI, Munich)** — Technical validator; ML engineer who needs to believe the CUDA stack won't require re-tooling their PyTorch codebase
- **Legal (Munich, unnamed)** — EU AI Act compliance sign-off; NVIDIA EU data center deployment answers this

## Key Dates
- April 4: Proposal submission deadline
- April 14: Oral presentation to Klaus + Helga (we are confirmed for this)
- April 28: Siemens vendor selection decision
- May 15: Target contract signature

---
*Source file for NVIDIA Cowork Demo | Lesson 4: Proposals*
