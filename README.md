# My Strategy

> **Workvivo HQ is the experience layer for work, AI, and people.** While most vendors race to ship AI features, we're shipping the experience where AI actually lands — for the 9 million employees who already open Workvivo every day, including the 80% of the workforce Microsoft Copilot and Glean structurally can't license. AI doesn't succeed because it exists. It succeeds when people use it, trust it, and experience it in the flow of work. That's the Workvivo advantage — and HQ is how we turn it into the AI-native headquarters for every employee.

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

- **Product:** Workvivo HQ — the AI-native headquarters for every employee. Three product pillars (Communication & Engagement, Search & Knowledge, People Intelligence) on one platform, fed by an expanding connector ecosystem and user-generated content competitors structurally can't see.
- **AI Value Archetype:** Copilot (primary) — HQ is the daily AI companion for every employee, head-to-head with Microsoft Cowork. Defence isn't a different archetype; it's better reach (frontline + desk) and stronger signal (Seer + cross-pillar data).
- **Vulnerability Scores:** Moat 4/5 · Data 4/5 · Platform 3/5
- **Top Risk:** Microsoft consolidates EX into Copilot Cowork via M365 App Store partner-built skills inside 12 months — collapsing HQ from a category claim into "the thing some companies pay extra for when Microsoft is already in the building."
- **Confidence:** H (upgraded from M after Module 6 — Liquid Content repositioning, brand narrative alignment, and the Cross-Pillar moat clarity changed the picture)
- **Prototype:** https://workvivo-hq.replit.app/
- **Kill Criteria:** In any kill case, we prioritise deeper LLM extensibility — Workvivo remains the experience layer — while deprioritising spend on AI features that aren't earning their inference cost. Triggers: (a) Microsoft extends Copilot Cowork with a credible partner-built EX skill pack (recognition, journeys, sentiment, frontline) before our H2 connector pilot proves out; (b) HQ Core daily-active usage falls below 70% across the contracted base in the first 6 months; (c) Liquid Content v2 unit economics don't close in H3.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 3/5 — one active loop (Cross-Domain Transfer), one missing by design (Network Intelligence, privacy-gated), one broken (Recursive Learning), one partial (Engagement Prediction).
- **Weakest Loop:** Loop 1 — Usage → Correction. We capture corrections but don't compound them at the platform layer, because we don't train on customer content. Closure is the H3 architectural fix.
- **Top Encroachment Threat:** Microsoft Copilot Cowork extended via M365 App Store partner-built EX skills (Beekeeper, Yoobic, Firstup) — letting Microsoft own the layer and partners do the long-tail feature work.
- **Encroachment Defense:** Build on what's already working. Ask HQ already surfaces content gaps to admins — a working surface-to-surface signal flow today, just one that routes through a person. Close Loop 1 at the platform layer (retrieval, ranking, orchestration) rather than the model layer. Compound Cross-Domain Transfer between pillars so the system gets demonstrably smarter quarter-over-quarter.
- **Vendor Portability:** Partial. Zoom AI Companion runs federated routing across Anthropic and OpenAI (Anthropic via AWS Bedrock for EU). We don't independently choose model providers — Zoom does. If Zoom shifts routing or pricing, our economics shift with it. Mitigation: provider-neutral evaluation criteria so re-routing through Zoom is feasible if needed.

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):** ~82% (non-AI platform)
- **Gross Margin (AI-adjusted):** ~50% blended at $6 list. AI tier alone runs at ~6% at the $2 entry price — deliberately thin to drive adoption, not a permanent margin position.
- **Pricing Model:** Hybrid tier-based seat pricing + consumption-based overage. Customers buy seats at the tier that matches expected AI usage; each seat includes a credit allocation; usage above allocation is PAYG at per-action rates.
- **Pricing Today → Tomorrow:** $4 platform today → $4 + $2 HQ AI ($6 combined) at June 14 launch · HQ+ at $10 PUPM · HQ+ Enterprise (ZoomMate, request only) at $24 PUPM
- **Total AI COGS / unit:** ~$1.88 per HQ AI se
