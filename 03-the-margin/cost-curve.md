# Cost Curve & Pricing Strategy — Workvivo HQ

**Pricing assumption:** All numbers in this model use list pricing. Beta and early-access customers may have negotiated terms, but we model on list for stress-testing margin and the broader strategy. Workvivo platform list = $4.5 PUPM; HQ tier list = $3 PUPM AI add-on; HQ+ list = $6.5 PUPM AI add-on; HQ+ Enterprise = $20 PUPM AI add-on (see ZoomMate note in Pricing Model section).

## Product Framing — Leader / Filler / Killer

- **🏆 Leader (the AI surface they come for):** Ask HQ — AI search and retrieval across the company knowledge layer. This is the AI feature buyers compare against Glean ($45/user) and Microsoft Copilot ($30/user). It's the every-employee reflex for "where do I find...?" and the procurement-killer when sized against alternatives.
- **🍟 Filler (bumps ARPU and drives daily habit, but not the buy reason):** Catch Me Up (the morning surface that makes HQ daily-active), AI Compose Posts, AI Page Builder, AI Journey Builder, AI Podcasts, AI Livestream Summaries, Seer AI Summaries. These deepen the experience and make HQ feel AI-native, but they're not what closes the deal — Ask HQ closes the deal.
- **💀 Killer (premium, complex, risky):** Agentic Liquid Content, agentic execution across connected systems (HRIS approval workflows, multi-step task completion), Deep Research, Custom Avatar video generation. These sit in HQ+ Enterprise / ZoomMate — Workvivo's premium upgrade path, not its primary sales motion. Expensive per-use, unpredictable consumption, and high-stakes when they go wrong — which is why they sit in the agentic tier with stricter routing.

**Killer usage %:** Approximately 20–30% of contracted users will actively use killer features in a given month. Comms managers using Agentic Liquid Content, ops leads triggering cross-system agentic workflows, executives commissioning deep research. Not everyone needs these. Bundling them into the base tier would price out customers who don't.

**70% rule applied:** If a feature is touched by >70% of contracted users, it belongs in HQ. Ask HQ, Catch Me Up, AI Compose Posts — all >70%. They're in HQ. Agentic Liquid Content, agentic HRIS workflows, deep research — all <30%. They're in HQ+ Enterprise / ZoomMate.

---

## Cost Model

### Assumption — workforce composition and pricing

Workvivo HQ prices the AI tier by usage intensity, layered on top of the core platform price. The typical customer splits roughly 80/20:

- **80% of the workforce on HQ** — light AI use. Search a few times a week, occasional workflow trigger. Mobile-first, often deskless. Priced for reach.
- **20% of the workforce on HQ+** — heavier AI use. Daily search, multiple workflows, regular content generation, conversational queries. Priced for value.

Customer-facing combined pricing at list:

| Tier | Platform (list) | AI tier (list) | Combined |
|---|---:|---:|---:|
| HQ | $4.5 | $3.0 | $7.5 PUPM |
| HQ+ | $4.5 | $6.5 | $11.0 PUPM |
| HQ+ Enterprise (ZoomMate) | $4.5 | $20.0 | $24.5 PUPM |

That 80/20 split is the strategic core of the pricing model. Microsoft Copilot prices the whole workforce at $30/user (Copilot license only — on top of M365 base). Workvivo prices the bulk of the workforce at $7.50 combined and the AI-heavy minority at $11 combined — which is how we reach everyone for a fraction of what desk-only competitors charge.

### Per-action unit costs

Customer-facing per-credit prices (overage rates above included credits). Base tier prices include allocated credits; overage is PAYG.

| Action | Customer price | Credits | Cost driver |
|---|---:|---:|---|
| Search query | $0.05 | 5 | Lightweight retrieval, mostly small models |
| Workflow run | $0.10 | 10 | Standard model path |
| Productivity — Edit | $0.10 | 10 | Standard model, lower-token output |
| Productivity — Create | $0.50 | 50 | Frontier model, higher-token output |
| Translation (per hour) | $0.50 | 5 | Standard model, language-specific routing |
| Custom Avatar (per minute) | $0.25 | 25 | Heavy compute, video generation |
| Deep Research | $2.50 | 250 | Frontier model, multi-step reasoning, long context |
| Agentic Delivery (Claw) | $0.05 (TBC) | 5 | Cross-system execution layer |

### HQ tier cost model (per user / month at planned usage)

HQ includes Search, Workflows, and Agentic Retrieval. Lightweight AI surface, mobile-first.

| Action | Usage / month | Credits | Modelled COGS |
|---|---:|---:|---:|
| Search | 20 queries | 100 | $1.00 |
| Workflows | 15 runs | 150 | $0.90 |
| **Total at planned usage** | — | **250** | **~$1.90 modelled COGS** |

At a $3 PUPM HQ tier price, this yields ~37% AI gross margin at planned usage.

### HQ+ tier cost model (per user / month at planned usage)

HQ+ adds Conversation, Productivity (Create + Edit), and Delivery to the HQ surface. Full AI surface.

| Action | Usage / month | Modelled COGS |
|---|---:|---:|
| Search | 20 queries | $1.00 |
| Workflows | 15 runs | $0.90 |
| Productivity — Edit | 16 edits | $1.60 |
| Productivity — Create | 4 creations | $2.00 |
| **Total at planned usage** | — | **~$5.50 modelled COGS** |

At a $6.50 PUPM HQ+ tier price, this yields ~15% AI gross margin at planned usage — tighter than HQ. HQ+ relies on consumption ceilings and selective frontier-model routing to defend margin. Translation, Custom Avatar, and Deep Research are not in base HQ+ usage — those are PAYG above the included credit pool or unlocked at the HQ+ Enterprise / ZoomMate tier.

### Blended COGS model (per typical customer)

Mid-market customer profile: 25,000 employees, 80/20 split (20,000 on HQ + 5,000 on HQ+).

| Tier | Users | AI revenue PUPM | Monthly AI revenue | Modelled AI COGS | AI gross margin |
|---|---:|---:|---:|---:|---:|
| HQ | 20,000 | $3.00 | $60,000 | $38,000 | 36.7% |
| HQ+ | 5,000 | $6.50 | $32,500 | $27,500 | 15.4% |
| **Blended AI tier** | **25,000** | — | **$92,500** | **$65,500** | **29.2%** |

Adding the platform layer (list $4.5 PUPM, ~$0.80 platform COGS, ~82% platform margin):

| Layer | Blended monthly revenue | Blended monthly COGS | Blended margin |
|---|---:|---:|---:|
| Platform (list $4.5 × 25,000) | $112,500 | $20,000 | 82% |
| AI tier | $92,500 | $65,500 | 29% |
| **Combined customer** | **$205,000** | **$85,500** | **58%** |

Total customer-level gross margin at list pricing is ~58% blended — materially lower than legacy 82% SaaS margins, but the AI tier is a pure expansion layer on top of an already-margin-rich platform. The 29% AI-tier margin is the honest story for AI economics; the 58% combined margin is the honest story for total customer economics.

### Enterprise customer benchmark — illustrative

A representative enterprise customer scenario: 512,000 employees, 80% on HQ (409,600) / 20% on HQ+ (102,400). At launch, contracted at HQ only — 100% HQ penetration, HQ+ penetration 0%, blended 80% of the total workforce.

All numbers assume list pricing throughout: $4.5 platform + $3 HQ AI tier = $7.5 combined PUPM.

| Metric | Value |
|---|---:|
| Contracted HQ users | 409,600 |
| Combined list price PUPM (platform + HQ AI tier) | $7.50 |
| **Monthly contract value at list** | **$3,072,000** |
| **Annual contract value at list** | **$36,864,000** |
| — of which platform revenue (at $4.5 PUPM) | $22,118,400 |
| — of which AI tier revenue (at $3.0 PUPM) | $14,745,600 |

The AI tier alone is ~$14.7M ARR — large enough to justify the entire AI engineering investment several times over (see Break-Even Math below). The combined contract approaches $37M ARR at full list, with future upside from HQ+ upgrades as AI usage matures and PAYG overages on heavy users.

This is the proof of the pricing thesis. Reaching the frontline 80% at $3 AI list unlocks revenue that desk-only AI tools cannot capture — Microsoft Copilot at $30/user (Copilot license alone) would price out the 80% frontline majority of this deal.

---

## Cascading Strategy

**AI orchestration layer:** Zoom AI Companion 3.0.

**Model approach:** Workvivo AI requests are routed through Zoom AI Companion 3.0's federated AI architecture. Rather than hard-coding a single model provider, requests are routed to the most appropriate path based on task complexity, latency, cost, and quality.

**Lightweight / triage path** (Zoom proprietary Small Language Models):
- Intent classification, request routing
- Simple edits, tone changes, short rewrites
- Basic summaries
- Search query classification

**Standard path** (Zoom AI Companion 3.0 standard models):
- Most everyday content work — edits, rewrites, regenerations
- Standard first drafts and campaign outlines
- Catch Me Up summaries
- Ask HQ retrieval and answering

**Advanced / reasoning path** (Zoom AI Companion 3.0 advanced models + NVIDIA Nemotron-based reasoning):
- Liquid Content multi-format generation
- Agentic execution across connected systems
- Deep Research
- Custom Avatar generation
- Long-form executive comms

**Routing rules:** Every request is classified first. Simple edits, tone changes, and routine retrieval stay on the lightweight or standard path. Net-new creation starts on standard and escalates only when content is long-form, executive-facing, addressed to 500+ employees, spans 3+ channels, or requires multiple audience variants.

**Agentic routing rule:** Agentic Liquid Content and agentic execution are only available in HQ+ Enterprise / ZoomMate. They use the advanced path with stricter controls because they can generate multiple variants, trigger more re-dos, and create unpredictable usage.

**Expected cascade ratio:** 20% lightweight / 65% standard / 15% advanced.

---

## Pricing Model

### Tier structure (AI tier add-on, on top of $4.5 platform list)

| AI Tier | Price PUPM (AI add-on) | Combined with platform | Above-threshold | Includes |
|---|---:|---:|---|---|
| **HQ** | $3.0 | $7.5 | PAYG via credits | Search, Workflows, Agentic Retrieval. Lightweight AI surface for the frontline majority. |
| **HQ+** | $6.5 | $11.0 | PAYG via credits | Everything in HQ + Conversation, Productivity (Create + Edit), Delivery. Full AI surface for AI-heavy users. |
| **HQ+ Enterprise (ZoomMate)** | $20.0 (with 2,200 credits upfront) | $24.5 | PAYG | Everything in HQ+ + Deep Research, Custom Avatar, Agentic execution across connected systems. For power users running multi-step agentic workflows. |

### A note on HQ+ Enterprise

HQ+ Enterprise at $20 PUPM is functionally Zoom's complete **ZoomMate** application with full agentic scope — cross-system execution, multi-step workflows, deep research, custom avatar generation, and the broader Zoom agentic surface area.

It's available to Workvivo customers if requested, but **it's not Workvivo's primary sales motion**. Our commercial focus is HQ ($3 AI tier) and HQ+ ($6.5 AI tier), where the EX-native value sits and where Workvivo's product investment is concentrated. ZoomMate is the Zoom-platform extension for customers who want full agentic capabilities on top of their HQ deployment — same federated AI architecture, broader scope, Zoom-led roadmap.

That distinction matters for the GTM motion. Workvivo's sales team leads with HQ and upgrades into HQ+ when AI usage justifies it. HQ+ Enterprise / ZoomMate enters the conversation only when a customer explicitly asks for agentic execution across their connected stack — and even then, the deal often gets co-quarterbacked with Zoom's enterprise team because ZoomMate sits inside the broader Zoom agentic platform, not inside Workvivo's product surface.

**Model:** Hybrid tier-based seat pricing + consumption-based overage. Customers buy seats at the tier that matches the user's expected AI usage. Each seat includes a credit allocation. Usage above the allocation is PAYG at per-action rates.

**Why this structure:**

*Tier pricing matches actual usage patterns.* A frontline worker who searches twice a week shouldn't pay the same as a comms manager who creates content daily. Microsoft Copilot's $30 flat rate over-charges the light-use majority and under-monetizes the AI-heavy power user. We do the opposite: under-price HQ for reach, fairly-price HQ+ for value.

*Credit allocation gives customers predictability.* Buyers want a known monthly cost. Pure PAYG creates unpredictable bills and stalls procurement. Pure flat-rate over-charges light users. The hybrid model gives a predictable baseline and a transparent overage rate.

*Consumption ceilings defend margin.* The pricing model only works if AI-heavy users pay for their consumption above the allocation. PAYG above the credit pool is the margin protection — without it, HQ+ seats run thin at $6.50.

---

## Stress Tests

| Scenario | Impact on Margin | Response |
|---|---|---|
| **Inference costs 3x** | HQ AI-tier modelled COGS rises from ~$1.90 to ~$5.70 PUPM (against $3 AI revenue — negative margin). HQ+ COGS rises from ~$5.50 to ~$16.50 (against $6.50 — heavily negative). | Tighten Zoom AI Companion 3.0 routing aggressively. Push 25%+ traffic onto lightweight path. Cap frontier model use to genuinely complex tasks only. Renegotiate pricing on the Zoom side or restructure tiers. |
| **Heavy HQ+ usage doubles** | HQ+ COGS rises from ~$5.50 to ~$11.00 against $6.50 revenue. AI tier margin goes deeply negative. | Tighten the HQ+ credit allocation. Move heavier workflows into HQ+ Enterprise / ZoomMate where the $20 price point can absorb the consumption. Communicate the change as tier refinement, not price increase. |
| **Zoom raises prices 50% (already happened pre-launch)** | Pre-launch, this forced re-tiering — heavy compute features moved up to HQ+ and HQ+ Enterprise. Post-launch, the same response is harder because customers are on contract. | Use Zoom AI Companion 3.0's federated routing to shift more traffic to lower-cost paths. Apply consumption ceilings tighter. Move new heavy-compute features into HQ+ Enterprise / ZoomMate rather than including them in lower tiers. |

---

## Board One-Pager

### Before (traditional Workvivo SaaS)
- **Current pricing (list):** $4.5 PUPM core platform
- **Current gross margin:** ~82%
- **Gross profit per user:** ~$3.70 PUPM
- **Value framed as:** Internal communications, employee engagement, content delivery, recognition.

### After (HQ AI-enabled, list pricing)
- **Proposed pricing (combined with platform):**
  - HQ: $7.5 PUPM ($4.5 platform + $3 AI tier) — *primary sales motion*
  - HQ+: $11 PUPM ($4.5 platform + $6.5 AI tier) — *upsell motion*
  - HQ+ Enterprise / ZoomMate: $24.5 PUPM ($4.5 platform + $20 AI tier) — *available on request, co-sold with Zoom*
  - PAYG above included credits
- **AI tier COGS (blended for 80/20 mid-market customer):** ~$2.62 PUPM at planned usage
- **Total customer COGS (platform + AI):** ~$3.42 PUPM
- **Expected gross margin (combined):** ~58% blended
- **Expected gross margin (AI tier alone):** ~29% blended
- **Value framed as:** AI-native HQ where every employee — frontline included — gets AI that helps them find, do, and understand. Workforce-wide AI, not desk-only.

### Net margin shift

Combined customer-level gross margin moves from ~82% (legacy SaaS) to ~58% (HQ AI-enabled at list). That's a 24-point margin shift driven by the variable AI consumption cost layered on top of the previously-margin-rich platform.

But the right comparison isn't gross margin %. It's **gross profit per workforce** and **total revenue per customer.**

### Why this is still a good business

| | Legacy Workvivo SaaS | HQ AI-enabled (80/20 customer at list) |
|---|---:|---:|
| Revenue PUPM (blended) | $4.5 | $8.20 combined ($4.5 platform + $3.70 AI tier) |
| Gross profit PUPM (blended) | $3.70 | ~$4.78 combined |
| **Gross profit uplift per user** | — | **+$1.08 PUPM (+29%)** |
| **Customer expansion math** | Static — one price point | ~$14.7M AI tier ARR added at enterprise scale (~410K HQ users), on top of platform revenue |

The bet isn't margin-per-user. It's **revenue-per-customer expansion**, **frontline reach** (which competitors structurally can't price for), and **moat density** (every-employee AI usage feeds Cross-Domain Transfer in the data flywheel).

Plus: PAYG overages on AI-heavy HQ+ users improve effective margin meaningfully beyond the planned-usage baseline. The model is designed to capture more revenue from the customers driving the most AI consumption.

### Board-ready narrative

Workvivo HQ launches with two primary AI tiers — HQ at $3 AI add-on and HQ+ at $6.5 — layered on a $4.5 PUPM core platform, built around an 80/20 workforce split. HQ is priced for reach, HQ+ for value. PAYG overages defend margin against heavy AI consumption. HQ+ Enterprise (ZoomMate) is available for customers who want full agentic surface area, but it's not our primary motion — Workvivo's commercial focus stays on HQ and HQ+, where the EX-native value sits.

At a mid-market customer scale (25K employees), blended combined margin is ~58% at list — materially lower than legacy 82% SaaS margins, but with materially higher revenue per customer (+82% blended PUPM). At enterprise scale (~410K HQ users), the AI tier alone adds ~$14.7M ARR on top of $22M+ in platform revenue — combined contract value approaches $37M at list.

The structural advantage is workforce reach. Microsoft Copilot at $30 PUPM reaches only the desk worker — 20% of the workforce. Workvivo HQ at $3 AI list reaches the frontline 80% that Copilot structurally cannot. That math is the procurement-killer argument: same workforce, fraction of the spend, broader reach.

**The bet works if...** the HQ tier drives every-employee adoption (proving the reach claim), HQ+ adoption follows from HQ exposure to AI features (proving the upsell motion), and PAYG overages plus tight Zoom AI Companion 3.0 routing hold blended AI tier margin at or above 29% at scale.

---

## Break-Even Math

**Customer-level break-even (mid-market, 25K employees, 80/20, at list):**

- Monthly AI tier revenue at planned usage: $92,500
- Modelled AI tier COGS: $65,500
- Monthly AI tier gross profit: $27,000
- Annual AI tier gross profit per customer: $324,000

**Portfolio break-even:**

Assuming $5M/year of dedicated AI engineering, infrastructure, and HITL/QA costs (Workvivo-side, not Zoom consumption):

- Annual fixed AI cost: $5M
- Break-even customer count: $5M ÷ $324K = **~15 mid-market customers** at planned usage
- At enterprise scale (~$14.7M AI ARR per customer): break-even on just **one enterprise customer**

The model breaks even quickly because the AI revenue scales with workforce size, not seat count. Two or three enterprise customers at the ~410K-user scale carry the entire AI investment.

The longer-run economics depend on PAYG overage capture and HQ+ adoption rate (customers who upgrade from HQ as their AI usage grows). HQ+ Enterprise / ZoomMate revenue, where it happens, is largely incremental — those deals come in alongside Zoom co-selling and aren't part of the core Workvivo upsell motion.
