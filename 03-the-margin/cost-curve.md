# Cost Curve & Pricing Strategy — AI Campaign Orchestrator / Liquid Content

## Product Framing

- **🏆 Leader:** The feature they come for: **Campaign Orchestration**
- **🍟 Filler:** Nice add, bumps ARPU: **Catch Me Up**
- **💀 Killer:** Premium AI feature: **Agentic Liquid Content** — the ability to create multiple campaign variants and content pieces from one prompt. This is risky because it can create too many options, too much user error, repeated re-dos, and unpredictable usage.

**Killer usage %:** Approx. **30% of Premium AI users** are likely to actively use killer features in a given month. This is not something every customer is asking for, but it is complex, expensive, and risky to roll out to everyone, so make sense in the premium bundle.

**Bundle or premium tier:**  
Agentic Liquid Content should **not** be included in the blanket **$3 AI Companion** package. It should be included only in the **$6 Agentic AI Companion Bundle** package.

**70% rule:** If Killer usage is below 70%, it should not sit in the core bundle. In this case, Agentic Liquid Content belongs in the premium AI tier.

---

# Cost Model

## Assumption

AI Companion is priced at a blanket **$3 per contracted user per month**.

Core Comms Orchestrator is included in AI Companion, but only a small number of comms, HR, or admin users are expected to use it directly.

Agentic Liquid Content is not included in the $3 AI Companion package. It is included in the **$6 Premium AI** package.

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
| Inference — primary model | $2.00 | Frontier or higher-quality model used for Productivity — Create. Main generation cost for building campaigns and creating net-new content. Create actions use more tokens and require higher-complexity reasoning than edits. |
| Inference — cascading / triage | $1.60 | Small or mid-tier model supports editing, rewriting, summarizing, analyzing, and improving content. These tasks are less complex than create actions and should not require the frontier model by default. |
| Infrastructure | $0.05 | Permissions, observability, job queues, logging, orchestration, and rate limits. |
| Data / storage | $0.05 | Prompt context, campaign metadata, document metadata, embeddings, cached outputs, and audit history. |
| Human-in-the-loop | $1.00 | QA sampling, content safety review, customer onboarding calibration, tone checks, and evaluation of generated outputs. |
| **Total AI COGS** | **$4.70** | Fully loaded cost per active Comms Orchestrator user per month, excluding translation and incremental Agentic Liquid Content usage. |

---

## Blended COGS Model

Because AI Companion is priced across the full employee base, Comms Orchestrator COGS should be blended across all contracted users.

**Formula:**
| Segment | Example Org Size | Active Comms Orchestrator Users (average) | Monthly AI Companion Revenue at $3 PUPM | Enterprise AI Search COGS | Comms Orchestrator COGS | Total AI COGS | Gross Profit After AI COGS | Gross Margin |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Small org | 1,000 | 2 | $3,000 | $1,000 | $9.40 | $1,009.40 | $1,990.60 | 66.4% |
| Mid-market | 25,000 | 5 | $75,000 | $25,000 | $23.50 | $25,023.50 | $49,976.50 | 66.6% |
| Enterprise | 500,000 | 10 | $1,500,000 | $500,000 | $47.00 | $500,047.00 | $999,953.00 | 66.7% |

**Key takeaway:** Comms Orchestrator costs approximately $4.70 per active creator, but less than $0.015 per contracted user in a small 1,000-person customer with 3 active users.

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
- tone of voice

**Advanced / reasoning model path:**  
Zoom AI Companion 3.0 advanced model path, including Zoom’s larger federated models and NVIDIA Nemotron-based reasoning capabilities where appropriate.

Used for:
-  Liquid Content
-  Agentic execution 
-  Deep research (although this will be blocked in our platform under any tier, unless the user requests it, in that case they will move to ZoomMate, Zoom's $15+ PUPM model)

**Routing rule:**  
Every request is classified first through Zoom AI Companion 3.0. Simple edits, tone changes, summaries, and rewrites stay on the lightweight or standard model path. Net-new campaign creation starts on the standard model path and escalates only when the content is long-form, executive-facing, addressed to 500+ employees, spans 3+ channels, or requires multiple audience variants.

**Agentic routing rule:**  
Agentic Liquid Content is only available in the **$6 Premium AI** package. It should use the advanced / reasoning model path and stricter controls because it can generate multiple campaign variants, trigger more re-dos, and create unpredictable usage.

**Expected cascade ratio:**  
20% lightweight model path / 65% standard model path / 15% advanced model path.


# Pricing Model

**Current pricing for AI Companion:** AI Companion is priced at a blanket $3 per contracted user per month.

**Current pricingfor Agentic AI Companion:** Agentic AI Companion is priced at a premium of $6 per contracted user per month.

**Model:** Two-tier blanket seat-based pricing.

**Tier	Price	Includes**
AI Companion	$3 PUPM	Core Comms Orchestrator, Productivity Edit, limited Productivity Create, and Catch Me Up
Premium AI	$6 PUPM	Everything in AI Companion, plus Agentic Liquid Content and higher-value AI creation capabilities

Why this model works: Seat-based pricing keeps the commercial model simple and maps to how Workvivo is already priced. Comms Orchestrator usage is concentrated among a small number of comms/admin users, so the cost blends down across the full contracted employee base. The $6 Premium AI package creates more room to absorb the higher usage risk of Agentic Liquid Content.

**Why Agentic sits in Premium AI:** Agentic Liquid Content is not a separate add-on, but it should not be included in the $3 package. It belongs in the $6 Premium AI tier because it is more powerful, less predictable, and more likely to create repeated generations, user error, and margin risk.


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
