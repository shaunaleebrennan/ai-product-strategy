# Workvivo HQ 

> Workvivo HQ is the bet that turns the platform 9 million employees already use into the experience layer where AI lands successfully — three pillars of AI capability priced at $2-6 per user per month to reach the 80% of the workforce Microsoft Copilot and Glean structurally can't license.

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** Workvivo HQ — the AI capability layer embedded across Workvivo HQ's three product pillars (Communication & Engagement, Search & Knowledge, People Intelligence). Built into the platform 9 million employees already open every day, not bolted on. Fed by an expanding connector ecosystem and user-generated content competitors structurally can't see.
- **AI Value Archetype:** Copilot (primary) — HQ AI is the daily AI companion for every employee, head-to-head with Microsoft Cowork. The defence isn't a different archetype; it's better reach (frontline + desk) and stronger signal (Seer + cross-pillar data).
- **Vulnerability Scores:** Moat 4/5 · Data 4/5 · Platform 3/5
- **Top Risk:** Microsoft consolidates EX into Copilot Cowork via the M365 App Store partner ecosystem inside 12 months — collapsing the HQ AI bet from a category claim into "the thing some companies pay extra for when Microsoft is already in the building."
- **Confidence:** H (upgraded from M after Module 6 — Liquid Content repositioning, brand narrative alignment, and Cross-Pillar moat clarity changed the picture)
- **Prototype:** https://workvivo-hq.replit.app/
- **Kill Criteria:** In any kill case, we prioritise deeper LLM extensibility — HQ remains the experience layer — while deprioritising AI features that aren't earning their inference cost. Triggers: (a) Microsoft extends Copilot Cowork with a credible partner-built EX skill pack (recognition, journeys, sentiment, frontline) before our H2 connector pilot proves out; (b) HQ AI adoption falls below 40% of HQ Core users in the first 6 months; (c) Liquid Content v2 unit economics don't close in H3.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 3/5 — one active loop (Cross-Domain Transfer), one missing by design (Network Intelligence, privacy-gated), one broken (Recursive Learning), one partial (Engagement Prediction).
- **Weakest Loop:** Loop 1 — Usage → Correction. We capture corrections but don't compound them at the platform layer because we don't train on customer content. Closure is the H3 architectural fix.
- **Top Encroachment Threat:** Microsoft Copilot Cowork extended via M365 App Store partner-built EX skills (Beekeeper, Yoobic, Firstup) — letting Microsoft own the layer and partners do the long-tail feature work.
- **Encroachment Defense:** Build on what's already working. Ask HQ already surfaces content gaps to admins — a working surface-to-surface signal flow today, just one that routes through a person. Close Loop 1 at the platform layer (retrieval, ranking, orchestration) rather than the model layer. Compound Cross-Domain Transfer between pillars so the AI gets demonstrably smarter quarter-over-quarter.
- **Vendor Portability:** Partial. Zoom AI Companion runs federated routing across Anthropic and OpenAI (Anthropic via AWS Bedrock for EU). We don't independently choose model providers — Zoom does. If Zoom shifts routing or pricing, our AI economics shift with it. Mitigation: provider-neutral evaluation criteria so re-routing through Zoom is feasible if needed.

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current, platform-only):** ~82%
- **Gross Margin (AI-adjusted):** ~50% blended at $6 list. AI tier alone runs at ~6% at the $2 entry price — deliberately thin to drive adoption, not a permanent margin position.
- **Pricing Model:** Hybrid tier-based seat pricing + consumption-based overage. Customers buy AI seats at the tier that matches expected usage; each seat includes a credit allocation; usage above allocation is PAYG at per-action rates.
- **Pricing Today → Tomorrow:** $4 platform today → $4 platform + $2 HQ AI ($6 combined) at June 14 launch · HQ+ AI at $10 PUPM · HQ+ Enterprise (full agentic, ZoomMate, request only) at $24 PUPM
- **Total AI COGS / unit:** ~$1.88 per HQ AI seat per month at the planned 20/65/15 cascade ratio
- **Cascading Strategy:** 20% lightweight (triage) / 65% standard / 15% advanced (frontier). Smart routing v1 ships in H2.
- **Net Margin Shift:** -32 points combined (82% → 50%) — but ARPU expands ~50%, and the AI tier unlocks a parallel commercial motion via Seer Standalone that doesn't require a full platform contract.
- **Break-even at:** AI tier breaks even with cascade routing v1 working at planned ratio. Blended margin trends from 50% toward 60%+ over 18–24 months as routing matures and AI tier ARR scales.

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 90% on the golden dataset, checked weekly. Zero tolerance for fabrication on policy, personnel, legal, or financial content.
- **Golden Dataset:** 7 rows, 3 adversarial. Expansion plan: 100+ rows by launch, 200+ rows within 90 days, with adversarial coverage across multilingual, sensitive content, and historical poisoning scenarios.
- **Confidence UX:** Legibility before precision. HQ AI shows confidence as a composite signal across every AI surface (Ask HQ, Catch Me Up, Seer, Compose), surfaces the data driving each prediction, and routes sensitive predictions through human review before they reach an end user.
- **HITL Architecture:** Three triggers across all HQ AI surfaces — (1) model confidence below 70%; (2) sensitive content or action (DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages); (3) any commitment that reaches a customer or writes to a system of record. Drafting and retrieval are auto. Anything that lands externally requires human approval.
- **Failure Mode Coverage:** Engagement prediction calibration (does "90% predicted" mean 90% in production?), multilingual tone validation for regional variants of sensitive content, historical data poisoning (the model learning the wrong pattern from low-quality past data), and the Air Canada precedent (every AI commitment is a company commitment).

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** Four loops — Recursive Learning (broken, H3 fix), Engagement Prediction (partial), Cross-Domain Transfer (active, the moat), Network Intelligence (missing by design, privacy-gated, pilot in H2).
- **Governance Posture:** Level 3. All AI features across three pillars run with zero data retention at model providers, no training on customer content (published commitment), federated routing through Zoom AI Companion (Anthropic + OpenAI), and EU residency via Anthropic on AWS Bedrock.
- **Autonomy Boundaries:** Drafting and retrieval — auto. Writing to a system of record, sending customer-facing content, executing multi-step agentic actions — all require human approval. Reading and drafting are read-only.
- **Escalation Triggers:** Confidence below 70% · sensitive topic detected · system-of-record write · ARR above $250K customer threshold · any executive-facing communication.
- **Audit Cadence:** Weekly automated eval against the golden dataset (CI/CD-gated, owner: HQ AI PM). Monthly 200-draft sample review. Quarterly policy review. Annual external review.
- **Shadow AI Audit (user-side):** 13 user-side workarounds found — 3 keep, 7 govern, 3 kill. Roughly 10 sanctioned AI categories now under governance, down from a long tail of personal subscriptions. Adjacent spend ~$10K–$18K/month across personal subscriptions and unsanctioned team accounts — the budget that converts into the governed alternative once we consolidate, and the number that gets the CFO's attention faster than the risk argument does.
- **Agent Boundaries:** HQ AI isn't a chain of named agents. It's three product pillars, each with its own AI capabilities and autonomy boundaries, sitting on a shared AI Engine foundation (Zoom AI Companion).
- **Regulatory Exposure:** Data residency — customer data processed in the customer's chosen region (US or EU). EU AI features powered by Zoom-hosted models plus Anthropic via Amazon Bedrock on AWS. EU AI Act exposure: low-to-medium — system supports business decisions, doesn't make legally binding decisions about individuals.

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now · 0–4 weeks):** Search & Knowledge pillar (Agentic Search across major enterprise systems — M365, ServiceNow, Workday, Google) · Communication & Engagement pillar (Catch Me Up, AI Compose across surfaces, Smart Chapters, Journey Builder, Page Builder) · People Intelligence pillar (Seer Summaries, Recommended Actions, Topic Grouping) · Seer Standalone (Glint alternative — new commercial motion sells without a full Workvivo platform contract) · Level 3 governance posture live · $2/$6/$20 AI tier pricing active.

- **Horizon 2 (Next · 1–3 months):** Connector ecosystem expansion (toward 1000+, prioritised by deal-blocking gaps) · Seer recommends actions automatically with HITL approval · Smart routing v1 (cascade routing protects AI margin at scale) · Network Intelligence pilot (10 opt-in design partners, privacy-gated cross-customer learning) · ZoomMate usage-based add-on ($20 + overages, request-only).

- **Horizon 3 (Bet · 3–6 months):** Liquid Content v2 (rebuilt as a premium-only feature in HQ+ Enterprise — scoped to 2–3 content formats that drive engagement lift) · Loop 1 fully closed (Recursive Learning compounds at the platform layer) · Cross-Domain Transfer automated between pillars (Comms → Search → Seer handoffs without human routing) · Zoom AI Docs integration (read-side first) · Connected intelligence from HRIS, L&D, and other sources · Presentations builder.

- **Board Narrative:** AI doesn't succeed because it exists. It succeeds when people use it, trust it, and experience it in the flow of work." The bet: turn Workvivo HQ into the AI experience layer for the 80% of the workforce Copilot ($30) and Glean ($45) can't license — three pillars at $2-6 per user, 15x cheaper, before Cowork goes GA. The ask: move Liquid Content out of the $2 bundle into HQ+ Enterprise as a premium upsell (the math doesn't work at entry tier); the honest gap is Loop 1 — broken today, the H3 fix is the bet I'd protect.

- **Ask:** **Deprioritise Liquid Content as a bundled feature. Move it to premium-only.** Liquid Content's unit economics don't work at $2 per user per month — multi-format generation costs more than the entry tier carries. Repositioning it to HQ+ Enterprise as a premium upsell (with optional usage-based add-on for HQ+ customers) protects launch economics, creates a clean upsell story for sales, and doesn't kill the feature — it puts it in the tier where the price can pay for the cost. Rebuild as Liquid Content v2 in H3 with this commercial frame from day one.

- **Key Strategic Change:** From single-feature bet to AI capability layer. M1 framed Liquid Content as the wedge into the broader Workvivo AI proposition. The course surfaced that (a) the AI bet is the capability layer across HQ's three pillars — not any single feature, (b) reach and signal density (Cross-Pillar Transfer) are the structural moat, not engagement prediction, and (c) Liquid Content's unit economics don't survive the $2 entry tier. Same product DNA. An order-of-magnitude bigger strategic claim. Liquid Content moves from launch wedge to H3 premium upsell.

→ Details: [`06-the-pitch/`](06-the-pitch/)
