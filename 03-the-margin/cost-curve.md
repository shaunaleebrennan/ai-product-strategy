# Cost Curve & Pricing Strategy — AI Campaign Orchestrator (Liquid Content)

- **🏆 Leader:** The feature they come for: Campaign Orchestration
- **🍟 Filler:** Nice add, bumps ARPU: Catch Me Up / Translations
- **💀 Killer:** Premium AI feature: Agentic liquid content — the ability to create multiple campaign variants and content pieces from one prompt. Risky because it can create too many options, too much user error, too many re-dos, and unpredictable usage.

**Killer usage %:** Approx. 30% of Premium AI users likely to actively use killer features in a given month. This is not something all customers are screaming for, but it is powerful, expensive, and risky to roll out to everyone.

**Bundle or premium tier:**  
Agentic liquid content should not be included in the blanket **$3 AI Companion** package. It should be included only in the **$6 Premium AI** package.

70% rule: if Killer usage is <70%, it should not be in the core bundle. In this case, it belongs in the premium AI tier.

---

# Cost Curve & Pricing Strategy — AI Campaign Orchestrator / Liquid Content

## Cost Model

**Assumption:** AI Companion is priced at a blanket **$3 per contracted user per month**. Core Comms Orchestrator is included in AI Companion, but only a small number of comms, HR, or admin users are expected to use it directly.

Expected active Comms Orchestrator users by customer size:

| Segment | Employee Range | Expected Active Comms Orchestrator Users |
|---|---:|---:|
| Small org | 1,000–5,000 employees | 1–3 users |
| Mid-market | 5,000–50,000 employees | 3–5 users |
| Enterprise | 50,000+ employees | 5–10 users |

One active Comms Orchestrator user performs approximately **20 paid AI content actions per month**:

- 4 net-new campaign creations
- 16 edits / regenerations

Agentic liquid content is not included in the $3 AI Companion package. It is included in the **$6 Premium AI** package.

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
| **Total AI COGS** | **$4.70** | Fully loaded cost per active Comms Orchestrator user per month, excluding translation and incremental agentic liquid content usage. |

---

## Blended COGS Model

Because AI Companion is priced across the full employee base, Comms Orchestrator COGS should be blended across all contracted users.

**Formula:**

```text
Blended Comms Orchestrator COGS per contracted user =
Active Comms Orchestrator users × $4.70
÷ total contracted employees
