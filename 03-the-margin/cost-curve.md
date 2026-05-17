# Cost Curve & Pricing Strategy — Workvivo HQ

**Pricing assumption:** All numbers use list pricing. Beta and early-access customers may have negotiated terms, but we model on list for stress-testing margin and the broader strategy. Workvivo platform list = $4 PUPM; HQ AI tier list = $2 PUPM add-on; HQ+ AI tier list = $6 PUPM add-on; HQ+ Enterprise (ZoomMate) = $20 PUPM AI add-on (see ZoomMate note in Pricing Model section).

**Strategic note on the $2 HQ AI tier:** $2 is deliberately low — it's an adoption-first price designed to put HQ AI in the hands of every employee on every workforce. Microsoft Copilot is $30. Glean is $45. We are 15x cheaper than Copilot at entry — and that's the procurement-killer math. AI-tier margin at $2 is thin by design. The model relies on three things to work: high-margin platform underneath, HQ+ upgrades as AI usage matures, and PAYG overages on heavy users.

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
| HQ | $4 | $2 | $6 PUPM |
| HQ+ | $4 | $6 | $10 PUPM |
| HQ+ Enterprise (ZoomMate) | $4 | $20 | $24 PUPM |

That 80/20 split is the strategic core of the pricing model. Microsoft Copilot prices the whole workforce at $30/user (Copilot license only — on top of M365 base). Workvivo prices the bulk of the workforce at $6 combined and the AI-heavy minority at $10 combined — which is how we reach everyone for a fraction of what desk-only competitors charge.

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

At a $2 PUPM HQ AI tier price, this yields ~5% AI gross margin at planned usage. Razor-thin by design. The HQ tier is priced for adoption, not for AI-tier profitability. Margin recovery comes from the platform layer underneath, HQ+ upgrades, and PAYG overages on heavy users.

### HQ+ tier cost model (per user / month at planned usage)

HQ+ adds Conversation, Productivity (Create + Edit), and Delivery to the HQ surface. Full AI surface.

| Action | Usage / month | Modelled COGS |
|---|---:|---:|
| Search | 20 queries | $1.00 |
| Workflows | 15 runs | $0.90 |
| Productivity — Edit | 16 edits | $1.60 |
| Productivity — Create | 4 creations | $2.00 |
| **Total at planned usage** | — | **~$5.50 modelled COGS** |

At a $6 PUPM HQ+ tier price, this yields ~8% AI gross margin at planned usage. Slightly healthier than HQ but still tight. HQ+ relies on consumption ceilings and selective frontier-model routing to defend margin. Translation, Custom Avatar, and Deep Research are not in base HQ+ usage — those are PAYG above the included credit pool or unlocked at the HQ+ Enterprise / ZoomMate tier.

### Blended COGS model (per typical customer)

Mid-market customer profile: 25,000 employees, 80/20 split (20,000 on HQ + 5,000 on HQ+).

| Tier | Users | AI revenue PUPM | Monthly AI revenue | Modelled AI COGS | AI gross margin |
|---|---:|---:|---:|---:|---:|
| HQ | 20,000 | $2.00 | $40,000 | $38,000 | 5.0% |
| HQ+ | 5,000 | $6.00 | $30,000 | $27,500 | 8.3% |
| **Blended AI tier** | **25,000** | — | **$70,000** | **$65,500** | **6.4%** |

Adding the platform layer (list $4 PUPM, ~$0.80 platform COGS, ~80% platform margin):

| Layer | Blended monthly revenue | Blended monthly COGS | Blended margin |
|---|---:|---:|---:|
| Platform (list $4 × 25,000) | $100,000 | $20,000 | 80% |
| AI tier | $70,000 | $65,500 | 6.4% |
| **Combined customer** | **$170,000** | **$85,500** | **49.7%** |

Total customer-level gross margin at list pricing is ~50% blended. The AI tier alone is near break-even (6.4%), but the AI is doing strategic work it doesn't have to be profitable to do: driving daily-active adoption that locks in the high-margin platform underneath and creates the upgrade path into HQ+.

### Enterprise customer benchmark — illustrative

A representative enterprise customer scenario: 512,000 employees, 80% on HQ (409,600) / 20% on HQ+ (102,400). At launch, contracted at HQ only — 100% HQ penetration, HQ+ penetration 0%, blended 80% of the total workforce.

All numbers assume list pricing throughout: $4 platform + $2 HQ AI tier = $6 combined PUPM.

| Metric | Value |
|---|---:|
| Contracted HQ users | 409,600 |
| Combined list price PUPM (platform + HQ AI tier) | $6.00 |
| **Monthly contract value at list** | **$2,457,600** |
| **Annual contract value at list** | **$29,491,200** |
| — of which platform revenue (at $4 PUPM) | $19,660,800 |
| — of which AI tier revenue (at $2 PUPM) | $9,830,400 |

The AI tier alone is ~$9.8M ARR — meaningful, but the bigger story is the $29.5M combined contract. The AI tier's job at this price is to unlock platform expansion (every employee contracted, not just the desk knowledge workers) and create the HQ+ upgrade path as AI usage matures.

This is the proof of the pricing thesis. Reaching the frontline 80% at $2 AI list unlocks revenue that desk-only AI tools cannot capture — Microsoft Copilot at $30/user would price out the 80% frontline majority of this deal. At $2 vs $30, the procurement-killer math gets sharper, not softer.

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

At the $2 HQ AI tier price point, cascade discipline matters more than ever. Pushing routine work onto the lightweight path is the single biggest margin lever we control.

---

## Pricing Model

### Tier structure (AI tier add-on, on top of $4 platform list)

| AI Tier | Price PUPM (AI add-on) | Combined with platform | Above-threshold | Includes |
|---|---:|---:|---|---|
| **HQ** | $2 | $6 | PAYG via credits | Search, Workflows, Agentic Retrieval. Lightweight AI surface for the frontline majority. |
| **HQ+** | $6 | $10 | PAYG via credits | Everything in HQ + Conversation, Productivity (Create + Edit), Delivery. Full AI surface for AI-heavy users. |
| **HQ+ Enterprise (ZoomMate)** | $20 (with 2,200 credits upfront) | $24 | PAYG | Everything in HQ+ + Deep Research, Custom Avatar, Agentic execution across connected systems. For power users running multi-step agentic workflows. |

### A note on HQ+ Enterprise

HQ+ Enterprise at $20 PUPM is functionally Zoom's complete **ZoomMate** application with full agentic scope — cross-system execution, multi-step workflows, deep research, custom avatar generation, and the broader Zoom agentic surface area.

It's available to Workvivo customers if requested, but **it's not Workvivo's primary sales motion**. Our commercial focus is HQ ($2 AI tier) and HQ+ ($6 AI tier), where the EX-native value sits and where Workvivo's product investment is concentrated. ZoomMate is the Zoom-platform extension for customers who want full agentic capabilities on top of their HQ deployment — same federated AI architecture, broader scope, Zoom-led roadmap.

That distinction matters for the GTM motion. Workvivo's sales team leads with HQ and upgrades into HQ+ when AI usage justifies it. HQ+ Enterprise / ZoomMate enters the conversation only when a customer explicitly asks for agentic execution across their connected stack — and even then, the deal often gets co-quarterbacked with Zoom's enterprise team because ZoomMate sits inside the broader Zoom agentic platform, not inside Workvivo's product surface.

**Model:** Hybrid tier-based seat pricing + consumption-based overage. Customers buy seats at the tier that matches the user's expected AI usage. Each seat includes a credit allocation. Usage above the allocation is PAYG at per-action rates.

**
