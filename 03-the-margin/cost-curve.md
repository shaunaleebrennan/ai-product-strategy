# Cost Curve & Pricing Strategy — AI Campaign Orchestrator / Liquid Content

## Product Framing

- **🏆 Leader:** The feature they come for: **Campaign Orchestration**
- **🍟 Filler:** Nice add, bumps ARPU: **Catch Me Up**
- **💀 Killer:** Premium AI feature: **Agentic Liquid Content** — the ability to create multiple campaign variants and content pieces from one prompt. This is risky because it can create too many options, too much user error, repeated re-dos, and unpredictable usage.

**Killer usage %:** Approx. **30% of active Campaign Orchestrators** are likely to actively use killer features in a given month. This is not something every customer is asking for, but it is complex, expensive, and risky to roll out to everyone, so make sense in the premium bundle.

**Bundle or premium tier:**  
Agentic Liquid Content should **not** be included in the blanket **$3 AI Companion** package. It should be included only in the **$6 Agentic AI Companion Bundle** package.

**70% rule:** If Killer usage is below 70%, it should not sit in the core bundle. In this case, Agentic Liquid Content belongs in the premium AI tier.

---

# Cost Model

## Assumption
The core SaaS platform is priced at **$4 per contracted user per month.**

AI Companion is priced at a blanket **$3 per contracted user per month** bringing the combined Core SaaS + AI Companion price to $7 PUPM.

Core Campaign Orchestrator is included in AI Companion, but only a small number of comms, HR, or admin users are expected to use it directly.

Agentic / Liquid Content is not included in the $3 AI Companion package. It is included in the **$6 Premium Agentic AI** package.

Expected active Comms Orchestrator users by customer size:

| Segment | Employee Range | Expected Active Comms Orchestrator Users |
|---|---:|---:|
| Small org | 1,000–5,000 employees | 1–3 users |
| Mid-market | 5,000–50,000 employees | 3–5 users |
| Enterprise | 50,000+ employees | 5–10 users |

One active Comms Orchestrator user performs approximately **20 paid AI content actions per month**:

- 4 net-new campaign creations
- 16 edits / regenerations

Translation has been removed from this model to keep the cost curve focused on Campaign Orchestration and Liquid Content.

---

## Active User Cost Model

| Feature | Action | Unit Cost | Credits | Monthly Usage | Monthly Cost |
|---|---|---:|---:|---:|---:|
| Productivity — Create | 1 doc / campaign creation | $0.50 | 50 | 4 | $2.00 |
| Productivity — Edit | 1 doc edit / analyze | $0.10 | 10 | 16 | $1.60 |
| **Total feature-level usage cost** |  |  |  | **20 paid content actions** | **$3.60** |

---

## Cost Category Breakdown

| Cost Category | Per Active Comms Orchestrator User / Month | Notes |
|---|---:|---|
| Inference — primary model, advanced creation path | $2.00 | Frontier or higher-quality model used for Productivity — Create. Main generation cost for building campaigns and creating net-new content. Create actions use more tokens and require higher-complexity reasoning than edits. |
| Inference — standard edit / regeneration path | $1.60 | Small or mid-tier model supports editing, rewriting, summarizing, analyzing, and improving content. These tasks are less complex than create actions and should not require the frontier model by default. |
| Infrastructure | $0.05 | Permissions, observability, job queues, logging, orchestration, and rate limits. |
| Data / storage | $0.05 | Prompt context, campaign metadata, document metadata, embeddings, cached outputs, and audit history. |
| Human-in-the-loop | $1.00 | QA sampling, content safety review, customer onboarding calibration, tone checks, and evaluation of generated outputs. |
| **Total AI COGS** | **$4.70** | Fully loaded cost per active Comms Orchestrator user per month, excluding translation and incremental Agentic Liquid Content usage. |

**Human-in-the-loop note:** Human-in-the-loop is modeled as $1.00 per active creator/month for early-stage QA, calibration, and safety review. Over time, this should decline or move from variable COGS to a customer onboarding / operating cost assumption.

---

## Blended COGS Model

Because AI Companion is priced across the full employee base, Comms Orchestrator COGS should be blended across all contracted users.

**Formula:**
| Segment | Example Org Size | Active Comms Orchestrator Users (average) | Monthly AI Companion Revenue at $3 PUPM | Enterprise AI Search COGS | Comms Orchestrator COGS | Total AI COGS | Gross Profit After AI COGS | AI Companion Standalone Gross Margin |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Small org | 1,000 | 2 | $3,000 | $1,000 | $9.40 | $1,009.40 | $1,990.60 | 66.4% |
| Mid-market | 25,000 | 5 | $75,000 | $25,000 | $23.50 | $25,023.50 | $49,976.50 | 66.6% |
| Enterprise | 500,000 | 10 | $1,500,000 | $500,000 | $47.00 | $500,047.00 | $999,953.00 | 66.7% |

**Key takeaway:** Key takeaway: Comms Orchestrator is not the primary margin risk in the $3 AI Companion package. It costs approximately $4.70 per active creator, which blends to only $0.0094 per contracted user in a 1,000-person customer with 2 active creators. The main COGS driver is Enterprise AI Search, which costs approximately $1.00 per contracted user/month if every user performs 20 searches.

## Enterprise Creator Sensitivity

The base enterprise assumption is 5–10 active Comms Orchestrator users. This may be conservative for global organizations with central, regional, HR, frontline, and local comms teams.

| Enterprise Org Size | Active Comms Orchestrator Users | Monthly Comms Orchestrator COGS | Blended Comms Orchestrator COGS / Contracted User |
|---:|---:|---:|---:|
| 500,000 | 10 | $47.00 | $0.0001 |
| 500,000 | 50 | $235.00 | $0.0005 |
| 500,000 | 100 | $470.00 | $0.0009 |
| 500,000 | 500 | $2,350.00 | $0.0047 |

**Interpretation:** Even with more active creators, standard Comms Orchestrator remains a small blended cost. The risk is not standard creation usage; it is repeated regeneration, creator sprawl, and Agentic Liquid Content usage.


# Cascading Strategy

**AI orchestration layer:**  
Zoom AI Companion 3.0.

**Model approach:**  
Workvivo AI requests are routed through Zoom AI Companion 3.0’s federated AI architecture. Instead of hard-coding one named model provider into the product strategy, requests should be routed to the most appropriate Zoom AI Companion model path based on task complexity, latency needs, cost, and quality.

**Lightweight / triage model path:**  
Zoom proprietary Small Language Models, or equivalent lightweight model paths within Zoom AI Companion 3.0.

Used for:

- Intent classification
- Request routing
- Simple edits
- Tone changes
- Short rewrites
- Basic summaries
- Detecting whether escalation is needed

**Standard model path:**  
Zoom AI Companion 3.0 standard model path for most everyday content work.

Used for:

- Edits
- Rewrites
- Regenerations
- Summaries
- Standard first drafts
- Campaign outline support
- Routine content improvements
- Campaign orchestration
- tone of voice

**Advanced / reasoning model path:**  
Zoom AI Companion 3.0 advanced model path, including Zoom’s larger federated models and NVIDIA Nemotron-based reasoning capabilities where appropriate.

Used for:
-  Liquid Content
-  Agentic execution 

**Routing rule:**  
Every request is classified first through Zoom AI Companion 3.0. Simple edits, tone changes, summaries, and rewrites stay on the lightweight or standard model path. Net-new campaign creation starts on the standard model path and escalates only when the content is long-form, executive-facing, addressed to 500+ employees, spans 3+ channels, or requires multiple audience variants.

**Agentic routing rule:**  
Agentic Liquid Content is only available in the **$6 Premium AI** package. It should use the advanced / reasoning model path and stricter controls because it can generate multiple campaign variants, trigger more re-dos, and create unpredictable usage.

**Expected cascade ratio:**  
20% lightweight model path / 65% standard model path / 15% advanced model path.


# Pricing Model

**Current pricing for AI Companion:** AI Companion is priced at a blanket $3 per contracted user per month.

**Current pricingfor Agentic AI Companion:** Agentic AI Companion is priced at a premium of $6 per contracted user per month.

**Model:** Two-tier blanket seat-based pricing, with PAYG when ceiling is reached.

**Tier	Price	Includes**
AI Companion	$3 PUPM	Core Comms Orchestrator, Productivity Edit, limited Productivity Create, and Catch Me Up
Premium AI	$6 PUPM	Everything in AI Companion, plus Agentic Liquid Content and higher-value AI creation capabilities

**TWhy this structure:**T Workvivo AI pricing has two commercial motions, both taking a hybrid seat-based and consumption-based pricing model.

Seat-based pricing maps to how Workvivo is already sold and keeps the commercial model simple for customers. It works for Campaign Orchestrator because direct usage is concentrated among a small number of comms, HR, and admin users, while the value is realized across the full employee base.

The $3 AI Companion package supports broad adoption and includes core campaign orchestration. The $6 Agentic AI Companion package creates a premium tier for higher-value, more complex, and higher-risk capabilities such as Agentic Liquid Content. Usage ceilings and consumption-based pricing protect margin when customers exceed expected usage, especially through repeated campaign regenerations, multi-audience variants, and heavy content creation.

# Pricing Model

## Current Pricing Structure

| Package | Price | Above Threshold Pricing | Core Positioning |
|---|---:|---|---|
| AI Companion | $3 PUPM | PAYG / Consumption Based Pricing TBD | Includes Campaign Orchestrator **without** liquid content |
| Agentic AI Companion | $6 PUPM | PAYG / Consumption Based Pricing TBD  | Includes Campaign Orchestrator **with** liquid content |


**Why this structure:**
Workvivo AI pricing has two commercial motions, both taking a hybrid seat based pricing and consumption based pricing model.
Seat-based pricing maps to how Workvivo is already sold and keeps the commercial model simple for customers. It works for Campaign Orchestrator because direct usage is concentrated among a small number of comms, HR, and admin users, while the value is realized across the full employee base.

The $3 AI Companion package supports broad adoption and includes core campaign orchestration. The $6 Agentic AI Companion package creates a premium tier for higher-value, more complex, and higher-risk capabilities, such as Agentic Liquid Content. Usage ceilings and consumption-based pricing protect margin when customers exceed expected usage, especially through repeated campaign regenerations, multi-audience variants, and heavy content creation.


## Stress Tests

| Scenario | Impact on Margin | Response |
|---|---|---|
| **Inference costs 3x** | Active Comms Orchestrator COGS rises from **$4.70 to $14.10** per active creator. In a 1,000-person org with 2 active creators, blended COGS rises from **$0.0094 to $0.0282** per contracted user. AI Companion margin remains healthy, but heavy creator usage becomes more visible. | Tighten routing through Zoom AI Companion 3.0 so more edits, rewrites, and regenerations stay on lightweight or standard model paths. Reserve advanced model paths for long-form, executive-facing, or multi-channel campaigns. |
| **Heaviest segment doubles** | If active Comms Orchestrator users double, a small org moves from **2 to 4 active creators**, a mid-market org from **5 to 10**, and an enterprise from **10 to 20**. COGS doubles, but remains low when blended across all contracted users. The bigger risk is repeated regenerations and uncontrolled creator access. | Add creator access controls, usage dashboards, and fair-use thresholds. Keep core Comms Orchestrator in AI Companion, but route heavy generation and high-volume creators into Agentic AI Companion or consumption-based pricing. |
| **Model provider / platform costs rise 50%** | Active Comms Orchestrator COGS rises from **$4.70 to $7.05** per active creator. In a 1,000-person org with 2 active creators, blended COGS rises from **$0.0094 to $0.0141** per contracted user. Margin impact is limited for standard Comms Orchestrator, but broader AI Companion margin may compress if Enterprise AI Search usage also rises. | Use Zoom AI Companion 3.0 model routing to shift routine edits and summaries to lower-cost model paths. Monitor search and generation separately, and apply consumption pricing once usage ceilings are reached. |
| **Agentic Liquid Content usage spikes** | Incremental agentic COGS is **[NEEDS INPUT]**, but usage could become unpredictable if users generate many campaign variants from one prompt. The risk is higher in the **$6 Agentic AI Companion** tier because users expect more advanced generation. | Keep Agentic Liquid Content out of the $3 AI Companion tier. Apply stricter routing, variant limits, usage ceilings, and consumption pricing after the ceiling is reached. |
| **Enterprise AI Search usage doubles** | Search COGS rises from **$1.00 to $2.00 per contracted user** if average usage increases from 20 to 40 searches per user/month. This has a much larger margin impact than Comms Orchestrator because search is used across the full employee base. | Treat Enterprise AI Search as the main COGS driver. Use caching, retrieval limits, query rewriting, and consumption pricing after the usage ceiling is reached. |


## Board One-Pager

### Before (traditional SaaS)

- **Current pricing:** $4 PUPM
- **Current gross margin:** ~80%
- **Value framed as:** Internal communications, employee engagement, campaign publishing, and content delivery. For comms teams, the value is helping them reach employees, keep people informed, and manage campaigns more efficiently across Workvivo.

---

### After (AI-enabled)

- **Proposed pricing:**  
  - Core SaaS + AI Companion: **$7 PUPM**  
    - $4 core platform + $3 AI Companion  
  - Core SaaS + Agentic AI Companion: **$10 PUPM**  
    - $4 core platform + $6 Agentic AI Companion  
  - Consumption-based pricing applies once usage ceilings are reached.

- **AI COGS per user/month:**  
  - Enterprise AI Search: **$1.00 per contracted user/month**  
    - Based on 20 searches per user/month at $0.05 per search.  
  - Comms Orchestrator: **$4.70 per active creator/month**  
  - Blended Comms Orchestrator COGS in a small 1,000-person customer with 2 active creators: **$0.0094 per contracted user/month**  
  - Total modeled AI COGS for AI Companion: **$1.0094 per contracted user/month**

- **Expected gross margin:**  
  - Core SaaS gross margin: **~80%**  
  - Core SaaS + AI Companion: **~74.2%**, assuming $0.80 non-AI COGS from the current SaaS margin and $1.0094 AI COGS.  
  - Core SaaS + Agentic AI Companion: **~81.9% before incremental Agentic Liquid Content COGS**.  
  - Incremental Agentic Liquid Content COGS: **[NEEDS INPUT]**

- **Value framed as:** Workvivo shifts from a comms and engagement platform into an AI-powered orchestration layer. For comms teams, this means faster campaign creation, AI-assisted content generation, predictive channel performance, recommended timing, direct publishing to Workvivo, and the ability to coordinate content across multiple channels. For the business, the value is connecting knowledge, systems, and conversations so employees can get answers and turn those answers into action.

---

### Net margin shift

- **Margin moves from ~80% to ~74.2% for the Core SaaS + AI Companion package.**
- Margin decreases because AI introduces variable usage-based COGS, primarily from Enterprise AI Search usage across the full contracted employee base. Comms Orchestrator itself is not the main cost driver because only a small number of comms, HR, or admin users actively use it. The larger cost driver is broad employee search usage at approximately **$1.00 per contracted user/month**.

---

### Why this is still a good business

Even though gross margin falls from ~80% to ~74.2%, gross profit per user increases.

- Traditional SaaS gross profit:  
  - $4 revenue × 80% margin = **$3.20 gross profit/user/month**

- Core SaaS + AI Companion gross profit:  
  - $7 revenue - $0.80 non-AI COGS - $1.0094 AI COGS = **$5.1906 gross profit/user/month**

That means gross profit per user increases by approximately **$1.99 PUPM**, even though the margin percentage declines.

This is still attractive because AI Companion expands the value proposition from communication delivery to governed intelligence and orchestration. Workvivo is not just helping comms teams publish content; it is helping them plan campaigns, generate content, predict performance, recommend timing, and activate the platforms the organization already owns. That creates a stronger case for ARPU expansion, retention, NRR, and movement into the **$6 Agentic AI Companion** tier.

The $6 Agentic AI Companion tier creates additional upside because it raises total revenue to **$10 PUPM** and gives Workvivo a premium path for higher-value capabilities like Agentic Liquid Content. Final Agentic AI Companion margin depends on **[NEEDS INPUT: incremental Agentic Liquid Content COGS]**.

---

### Board-ready narrative

The core SaaS platform is priced at **$4 PUPM** with an estimated gross margin of around **80%**. Adding AI Companion increases the customer price to **$7 PUPM** and introduces approximately **$1.0094 PUPM** in modeled AI COGS, bringing expected gross margin to around **74.2%**. While the margin percentage declines, gross profit per user increases from **$3.20 to $5.19**, so the AI package improves monetization if it supports adoption, retention, and expansion. The strategic value is that Workvivo moves from a comms and engagement platform to an orchestration layer that helps customers connect knowledge, create campaigns, recommend actions, and activate the systems they already own. The main risk is uncontrolled AI usage, especially broad Enterprise AI Search growth, repeated campaign regeneration, or Agentic Liquid Content. We mitigate that through Zoom AI Companion 3.0 routing, usage ceilings, creator access controls, and consumption-based pricing once customers exceed planned usage.

**The bet works if...** AI Companion increases ARPU and retention enough to justify the margin shift, while Agentic AI Companion captures premium orchestration and liquid content use cases and usage ceilings protect margin from heavy consumption.
