# Ford Motor Company — Account Intelligence Brief
*For use with Lesson 1 Demo: "Research Like You Had a Team"*

---

## Demo Prompt to Use in Claude Cowork
> "Using everything in this file, prep me for my discovery call with James Whitfield at Ford. Give me: their top 3 AI strategic priorities, the business pain I should lead with, 3 questions to uncover budget authority, and 2 ways NVIDIA is a better fit than their current AWS setup."

---

## Company Overview
**Ford Motor Company** | NYSE: F | Dearborn, Michigan
- Revenue: $185.0B (FY2025)
- Employees: ~177,000 globally
- AI/Tech Budget: ~$5B annually (Ford Pro Intelligence + Ford Blue Oval Intelligence)

## Strategic AI Initiatives (Priority Order)
1. **Autonomous & ADAS** — Ford Latitude AI (formerly Argo AI assets); developing Level 2+ ADAS for F-Series trucks; training on 10M+ hours of driving data
2. **Manufacturing AI** — "Ford Production System 2.0": predictive maintenance on 67 plants, visual quality inspection using computer vision, 14% reduction in unplanned downtime target
3. **Digital Twin** — Full virtual replica of River Rouge Complex; requires 8–12 weeks of simulation compute per quarter currently running on Azure

## Current Technology Stack
- **Primary cloud:** Microsoft Azure (Ford-Microsoft 6-year partnership, announced 2021, $100M)
- **AI training:** Mix of Azure NDv4 (A100) instances + small on-prem CPU cluster in Dearborn
- **ML frameworks:** PyTorch (primary), TensorFlow (legacy ADAS models)
- **Data platform:** Databricks on Azure, Snowflake for analytics

## Known Pain Points
- Azure GPU availability: James mentioned to his network a 6-week wait for A100 spot instances in Q4 2025, which delayed a critical ADAS model release
- **Training speed bottleneck:** Their Level 2 ADAS model retraining cycle takes 19 days on current Azure setup — blocking 3 planned feature releases in 2026
- **Cost overrun:** Azure AI bill ran 34% over budget in FY2025 ($47M actual vs $35M forecast) due to unpredictable spot pricing
- **IP / data sovereignty concerns:** Ford legal flagged risk of training proprietary ADAS data on shared hyperscaler infrastructure in Q3 2025

## Buying Signals
- Ford issued an RFI in January 2026 for "on-premises AI compute infrastructure" — NVIDIA responded
- James Whitfield posted on LinkedIn (Feb 2026): *"The future of automotive AI isn't in the cloud — it's at the edge and on-prem. Data sovereignty is the next competitive moat."*
- Ford IT issued a budget pre-approval for $15M in AI infrastructure for H1 2026

## Champion Profile: James Whitfield
- **Title:** VP of AI & Data, Ford Blue Oval Intelligence
- **Background:** Ex-AWS ML specialist SA (2016–2020), joined Ford 2020; strong technical credibility
- **Motivations:** Wants to own AI infrastructure decision; building a legacy as the exec who "brought AI production to scale" at Ford
- **Communication style:** Data-driven, skeptical of vendor hype — lead with proof points and TCO math, not feature lists
- **LinkedIn:** Active poster on AI/automotive topics; commented positively on NVIDIA's GTC 2026 announcement
- **Key concern:** Making a $14M decision that gets second-guessed by CFO if ROI isn't clear

## Economic Buyer: David McClelland (CFO, Ford Blue Oval)
- Approved $15M AI infra budget contingent on 3-year ROI > 2.5x
- Will want to see: total cost comparison vs Azure, risk mitigation story, reference customers

## Competitive Situation
- **Microsoft Azure** is the incumbent; Ford-Microsoft partnership creates internal political pressure
- AMD has engaged Ford's procurement team with MI300X pricing in Q1 2026
- NVIDIA advantage: Ford's ML team already runs on CUDA; switching cost to AMD is 6–18 months of engineer re-tooling

## Recent News (last 60 days)
- March 2026: Ford announced delay of 2027 F-150 ADAS upgrade — cited "insufficient AI compute capacity"
- February 2026: Ford Q4 2025 earnings — CEO Jim Farley: *"AI is the single biggest determinant of whether Ford wins or loses the next decade"*
- January 2026: Ford-Microsoft partnership expansion announced, BUT excludes AI training infrastructure (Azure ML scope only)

---
*Source file for NVIDIA Cowork Demo | Lesson 1: Account Research*
