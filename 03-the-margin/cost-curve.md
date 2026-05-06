# Cost Curve & Pricing Strategy — AI Campaign Orchestrator (Liquid Content)

🏆 Leader: The feature they come for: Campaign Orchestration
🍟 Filler: Nice add, bumps ARPU: Catch me up 
💀 Killer: Sell separately or die: Agentic liquid content - the ability to create endless content pieces from one prompt - risky as too many options, and too much user error/ re-do's - this could kill us if bundled

**Killer usage % ** 30% of users actively use killer features in a given month. (not something our customers are screaming for, but expensive - so risky to rollout to everyone.

** Bundle or add-on **: Add-on  (70% rule: if Killer usage is <70%, it is probably an add-on.)

## Cost Model

**Assumption:** 
One comms manager performs 20 AI content actions per month — 4 net-new campaign or knowledge doc creations and 16 edits, and regenerations. Editing is the dominant use case. Net-new creation is more expensive and receives tighter routing.

| Feature | Action | Unit Cost | Credits | Monthly Usage | Monthly Cost |
|---|---|---:|---:|---:|---:|
| Productivity — Create | 1 doc creation | $0.50 | 50 | 4 | $2.00 |
| Productivity — Edit | 1 doc edit / analyze | $0.10 | 10 | 16 | $1.60 |
| **Total** |  |  |  | **20 actions** | **$3.60** |

| Cost Category | Per-User/Month | Notes |
|---|---:|---|
| Inference — primary model | $2.60 | Main generation cost for creating, editing, rewriting, summarizing, analyzing, and improving content. Create actions use more tokens and higher-quality models than edit actions. |
| Inference — cascading / triage | $0.30 | Small model classifies whether the task is create or edit, detects complexity, rewrites prompts, and routes to the right model tier. |
| Infrastructure | $0.30 | Content orchestration, templates, permissions, observability, job queues, logging, and rate limits. |
| Data / storage | $0.25 | Draft content, prompt context, document metadata, embeddings, cached outputs, and audit history. |
| Human-in-the-loop | $0.15 | QA sampling, content safety review, customer onboarding calibration, tone checks, and evaluation of generated outputs. |
| **Total AI COGS** | **$3.60** | Target ceiling is **$3.60 per AI content user per month** based on 4 create actions and 16 edit actions. |

---

## Cascading Strategy

**Triage model:** GPT-4.1 mini or equivalent small model.
**Mid-tier model:** Standard model for most edits, rewrites, summaries, and standard first drafts.
**Frontier model:** GPT-4.1 / Claude Sonnet for long-form campaigns, executive all-hands, multi-audience content, and policy docs.
**Routing rule:** Every request is classified first. Simple edits, tone changes, and summaries stay on small or mid-tier models. Net-new creation starts on mid-tier and escalates to frontier when content is long-form, executive-facing, addressed to 500+ employees, or spans 3+ channels.
**Expected cascade ratio:** 40% small model / 45% mid model / 15% frontier model


**Expected cascade ratio:**  
**40% small model / 45% mid model / 15% frontier model**

---

## Pricing Model

**Current pricing:**  
AI content creation is either bundled into AIC+ or not priced separately.

**Proposed AI pricing:**  
Price AI content creation as an **$8–$10 PUPM add-on**, or include limited creation credits inside AIC+ and meter additional usage.

**Model:**  
Hybrid seat-based + credit-based pricing.

**Why this model:**  
Seat-based pricing is simple for customers and maps to the buyer’s budget. Credits protect margin because **Productivity — Create costs 5x more than Productivity — Edit**.

Recommended packaging:

| Capability | Packaging Recommendation |
|---|---|
| Productivity — Edit | Bundle into AIC+ or AI Content Assist |
| Productivity — Create | Include limited allowance, then meter through credits |
| Heavy creation usage | Premium tier or PAYG |
| Executive / sensitive content | Frontier-routed and premium-controlled |

---

## Stress Tests

| Scenario | Impact on Margin | Response |
|---|---|---|
| Create usage doubles | AI COGS rises from **$3.60 to $5.60** per user per month. At $8 PUPM, gross margin falls from **55% to 30%**. | Limit included create actions, meter additional creation, and route simple creation to mid-tier models. |
| Edit usage doubles | AI COGS rises from **$3.60 to $5.20** per user per month. Even cheaper edit actions create pressure at high volume. | Keep edit bundled but monitor heavy users, use small models for simple edits, and introduce fair-use thresholds. |
| Model provider raises prices 50% | AI COGS rises from **$3.60 to $5.40**. At $8 PUPM, margin drops from **55% to 33%**. | Use multi-model routing, reduce frontier usage, cache common prompts, and avoid unlimited create usage. |
| Create becomes 50% of usage | If users perform 10 creates and 10 edits, AI COGS rises to **$6.00** per user per month. At $8 PUPM, margin falls to **25%**. | Treat create-heavy usage as a premium package, meter create actions, or price closer to $10 PUPM. |

---

## Board One-Pager

**Before — traditional SaaS:**  
Content creation tools are largely fixed-cost software features. Gross margin is predictable because usage does not materially change cost per user.

**After — AI-enabled:**  
AI content creation introduces variable COGS. Editing is relatively safe to bundle, but net-new document creation creates margin risk because each create action costs **$0.50**, compared with **$0.10** for an edit.

**Net margin shift:**  
At **$8 PUPM**, AI content creation generates approximately **55% gross margin** in the base case. At **$10 PUPM**, margin improves to approximately **64%**. The margin profile breaks down if create usage becomes too high or if unlimited creation is bundled into a low per-user price.

**Strategic recommendation:**  
Bundle **Productivity — Edit** as the everyday value driver. Treat **Productivity — Create** as a premium or credit-metered action. The package works if editing remains the dominant behavior and net-new creation is limited, metered, or priced into a higher tier.

---

## Break-Even Math

**Average customer:** 5,000 AI content users  
**Proposed price:** $8 PUPM  
**Average monthly revenue:** 5,000 × $8 = **$40,000**  
**Average AI COGS:** 5,000 × $3.60 = **$18,000**  
**Gross profit:** **$22,000 per month**  
**Gross margin:** **55%**

**Break-even:**  
If monthly fixed operating costs for this AI content product are **$50,000**, Workvivo needs approximately:

**$50,000 / $4.40 gross profit per user = 11,364 AI content users**

So the package breaks even at roughly **11.4k paid AI content users** at $8 PUPM.


## Board One-Pager

### Before (traditional SaaS)

- **Current pricing:** AI content creation is either bundled into AIC+ or not priced separately.
- **Current gross margin:** [NEEDS INPUT]
- **Value framed as:** Productivity, content support, and faster internal communications workflows.

---

### After (AI-enabled)

- **Proposed pricing:** $8–$10 PUPM for AI content creation, or limited creation credits inside AIC+ with additional usage metered.
- **AI COGS per user/month:** $3.60
- **Expected gross margin:**  
  - 55% at $8 PUPM  
  - 64% at $10 PUPM
- **Value framed as:** Faster content creation, better-quality employee communications, reduced manual drafting and editing time, and higher-value productivity for comms and knowledge workers.

---

### Net margin shift

- **Margin moves from [NEEDS INPUT]% to 55–64%.**
- Margin changes because AI content creation introduces variable COGS where traditional SaaS features are mostly fixed-cost. The main cost driver is **Productivity — Create**, which costs **$0.50 per action**, compared with **$0.10 per Productivity — Edit action**. If users mostly edit, the package remains commercially viable. If users create too much net-new content, margin compresses quickly.

---

### Why this is still a good business

Even though gross margin may be lower than traditional SaaS, AI content creation can still be attractive if it increases **revenue per user**, strengthens the AIC+ value proposition, and improves retention or expansion. At **$8 PUPM**, each user generates **$4.40 gross profit per month** after AI COGS. For an average customer with **5,000 AI content users**, this creates **$40,000 in monthly revenue**, **$18,000 in AI COGS**, and **$22,000 in gross profit**.

The package breaks even at approximately **11,364 paid AI content users**, assuming **$50,000 in monthly fixed operating costs**. The business works if Workvivo can keep editing as the dominant behavior, meter heavier creation usage, and use model routing to avoid sending every content request to a frontier model.

---

### Board-ready narrative

AI content creation changes the margin profile because usage now has a direct cost, especially when users generate net-new content. Our base case assumes each user performs **4 create actions** and **16 edit actions** per month, resulting in **$3.60 AI COGS per user**. At **$8–$10 PUPM**, this produces **55–64% gross margin**, which is lower than traditional SaaS but still attractive if it drives higher ARPU, stronger AIC+ adoption, and better retention. The main risk is that create usage becomes too high and erodes margin. We mitigate that by bundling Productivity — Edit, limiting or metering Productivity — Create, and routing simple content tasks to small or mid-tier models.

**The bet works if...** AI content creation increases ARPU and retention enough to justify a lower gross margin, while Productivity — Create remains limited, metered, or priced into a premium tier.
