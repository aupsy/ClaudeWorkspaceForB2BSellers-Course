---
name: hydrate
description: Bootstrap the Knowledge/ base by extracting product, competitive, and sales context from a product website, documentation URL, local folder, or Seismic location. Fills in Knowledge/ templates without overwriting content the seller has already customized.
---

# Hydrate Skill

Populate your Knowledge/ base from real sources — no blank-page setup.

**Usage**: `/hydrate [source-type] [location]`

**Examples**:
```
/hydrate website https://www.acmecorp.com
/hydrate docs https://docs.acmecorp.com/overview
/hydrate folder "C:/Users/seller/Documents/Sales Materials"
/hydrate seismic "Enterprise/Pitch Decks"
/hydrate all
```

Run multiple times with different sources — each run adds to what's already there rather than overwriting it.

---

## Safety Rules (Always Follow)

1. **Never overwrite customized content.** Before writing to any Knowledge/ file, check if it still contains `[FILL IN]` placeholders. If placeholders remain, fill them in. If the seller has already replaced them with real content, do not overwrite — append a `<!-- HYDRATED SUGGESTION -->` block at the bottom instead, and tell the seller to review and merge manually.

2. **Mark everything hydrated.** Prefix all hydrated content with a `> 🔍 *Hydrated from [source] — review before using*` callout. This makes it easy for the seller to spot and verify auto-populated content.

3. **Ask before writing.** After extracting content, show the seller a summary of what you found and what files you plan to update. Get a quick confirmation before writing.

4. **Be honest about confidence.** If you're inferring something (e.g., guessing the ICP from the website's customer logos), say so clearly.

---

## Source: Website (`/hydrate website [URL]`)

### Step 1: Crawl Key Pages

Fetch the following pages (adapt based on site structure):
- Homepage (main value prop, headline messaging)
- `/pricing` or `/plans` (tiers, pricing model)
- `/customers` or `/case-studies` (ICP signals, customer logos, ROI stats)
- `/product` or `/features` or `/solutions` (feature set, use cases)
- `/about` or `/company` (company stage, founding, mission)
- `/integrations` (tech stack compatibility)
- `/security` or `/trust` (compliance, data handling)

### Step 2: Extract

From the fetched pages, extract:

**For `Knowledge/product/Product-Overview.md`**:
- One-liner value proposition (from headline/hero copy)
- Problems solved (from "pain" or "challenge" language)
- Key features and capabilities
- ICP signals (customer logos, "built for [X]" language, case study industries)
- Integration list
- Compliance/security claims

**For `Knowledge/product/Pricing-and-Packaging.md`**:
- Pricing model (per seat, flat, usage-based)
- Tier names and what's included
- Any public pricing numbers

**For `Knowledge/compete/Competitive-Landscape.md`**:
- Competitors mentioned (in comparison pages, G2 badges, "vs." pages)
- How the company positions against them

### Step 3: Populate Files

For each file, fill in `[FILL IN]` placeholders where you have confident data. For inferred data, add a review callout. Show the seller a before/after diff summary before writing.

---

## Source: Documentation (`/hydrate docs [URL]`)

### Step 1: Identify Structure

Fetch the docs homepage/index. Identify:
- Top-level sections (Getting Started, Features, Integrations, API, etc.)
- Any "overview" or "introduction" page

### Step 2: Crawl High-Value Pages

Focus on:
- Overview / Introduction (what the product does, core concepts)
- Features / Capabilities (what's available)
- Integrations (full list with details)
- Security / Compliance / Data handling
- Limits / Requirements (useful for technical evaluations)

Avoid deep API reference pages — focus on conceptual/feature documentation.

### Step 3: Extract and Populate

Supplement `Knowledge/product/Product-Overview.md` with:
- Technical detail on features (more precise than website copy)
- Full integration list with details
- Security and compliance specifics (SOC 2, GDPR, data residency)
- System requirements or limitations

This is especially useful for filling in the **Technical/Security Notes** section of `Product-Overview.md` that website copy often skips.

---

## Source: Local Folder (`/hydrate folder [path]`)

### Step 1: Scan and Classify

List all files in the specified folder (and subfolders). Classify each by likely content type:

| File pattern / name contains | Likely content | Target Knowledge/ file |
|------------------------------|---------------|------------------------|
| "pitch", "deck", "overview" | Product positioning, messaging | `product/Product-Overview.md` |
| "battle card", "competitive", "vs" | Competitive intel | `compete/[Competitor].md` |
| "objection", "FAQ", "questions" | Objection handling | `plays/Objection-Handling.md` |
| "discovery", "qualification", "playbook" | Sales methodology | `plays/Discovery-Framework.md` |
| "pricing", "packaging", "quote" | Pricing/packaging | `product/Pricing-and-Packaging.md` |
| "case study", "customer story", "ROI" | Customer proof/ICP signals | `product/Product-Overview.md` |
| "onboarding", "implementation" | Process / post-sale | `org/Process-Guide.md` |

### Step 2: Read and Extract

For each classified file, read its content and extract the relevant structured information. For PDFs and Office files, extract the text content.

For files you can't determine the content type from the name alone, read the first few paragraphs to classify.

### Step 3: Route and Populate

Write extracted content to the appropriate `Knowledge/` files, following the safety rules. If multiple files map to the same target, merge intelligently rather than overwriting.

After hydration, show the seller:
- What files were read
- What was extracted from each
- What Knowledge/ files were updated and how

---

## Source: Seismic (`/hydrate seismic [folder-path]`)

Seismic is a sales enablement platform where teams store pitch decks, battle cards, and playbooks. This source requires Seismic API credentials in your `.env` file.

### Prerequisites

Your `.env` must contain:
```
SEISMIC_TENANT=yourcompany.seismic.com
SEISMIC_TOKEN=your_bearer_token
```

See `SALESFORCE-SETUP.md` → Seismic section for how to get these.

### Step 1: List Content in the Specified Folder

Call the Seismic Content API to list items in the folder:

```
GET https://{SEISMIC_TENANT}/api/content/v2/contents
  ?teamsiteId={teamsite_id}
  &path={folder_path}
Authorization: Bearer {SEISMIC_TOKEN}
```

List all content items with their names, types, and IDs. Show the seller the list and ask which items to hydrate from (or confirm "all").

### Step 2: Fetch Content

For each selected item, retrieve the content:

```
GET https://{SEISMIC_TENANT}/api/content/v2/contents/{id}
Authorization: Bearer {SEISMIC_TOKEN}
```

For **LiveDocs and Pages** (HTML-based): fetch the text content directly.
For **PowerPoint/PDF files**: fetch the preview/text version if available via the API; otherwise note the file and ask the seller to summarize the key points from each deck.

### Step 3: Classify and Extract

Classify each Seismic item by content type using the same rules as the local folder source (name-based + content-based). Common Seismic content patterns:

| Seismic content type | Likely extract target |
|---------------------|----------------------|
| "Sales Pitch" / "Executive Deck" | `product/Product-Overview.md` (messaging, differentiators) |
| "Battle Card — [Competitor]" | `compete/[Competitor].md` |
| "Objection Handling" | `plays/Objection-Handling.md` |
| "Discovery Guide" / "Qualification Playbook" | `plays/Discovery-Framework.md` |
| "ROI / Business Case" | `product/Product-Overview.md` (ROI story section) |
| "Product Overview" / "1-pager" | `product/Product-Overview.md` |

### Step 4: Populate Knowledge/ Files

Follow the same safety rules as other sources. For each battle card found, create a new `Knowledge/compete/[Competitor Name].md` using the `_competitor-template.md` structure, populated with content from the Seismic battle card.

---

## Source: All (`/hydrate all`)

Interactive mode — walks through each source type in sequence:

1. Ask: "Do you have a product website URL?" → run website hydration
2. Ask: "Do you have a product documentation URL?" → run docs hydration
3. Ask: "Do you have a local folder of sales materials?" → run folder hydration
4. Ask: "Are you using Seismic? If so, what folder should I look in?" → run Seismic hydration

After all sources are processed, generate a **Hydration Summary**:

---

## Hydration Summary
*Generated: [date] | Sources: [list]*

### What Was Populated

| Knowledge/ File | Status | Source | Needs Review |
|----------------|--------|--------|-------------|
| `product/Product-Overview.md` | [Fully populated / Partially populated / Skipped] | [Sources used] | [Yes/No — what to check] |
| `product/Pricing-and-Packaging.md` | | | |
| `compete/Competitive-Landscape.md` | | | |
| `compete/[Competitor].md` | | | |
| `plays/Objection-Handling.md` | | | |
| `plays/Discovery-Framework.md` | | | |

### Still Needs Manual Input

Items that couldn't be auto-populated (typically internal/confidential info not found in public sources):
- [ ] `[FILL IN]` sections still remaining in CLAUDE.md
- [ ] Team quota and OKRs (`Knowledge/metrics/Sales-OKRs.md`)
- [ ] Discount authority and deal desk process (`Knowledge/product/Pricing-and-Packaging.md`)
- [ ] Team territory and org structure (`Knowledge/org/Team-Context.md`)

### Recommended Next Steps

1. Review all files marked "Needs Review" — verify accuracy, correct anything that was misinterpreted
2. Fill in the remaining `[FILL IN]` items above
3. Connect your CRM (see `SALESFORCE-SETUP.md`) if you haven't already
4. Run `/call-prep [Account Name]` to test the full workflow end-to-end

---
