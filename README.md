# My Strategy

> Microsoft Copilot is AI without a home — bolted onto apps half the workforce never opens, a disconnected experience that takes years to deliver value.…

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

- **Product:**
- **AI Value Archetype:** Primary: Copilot — HQ is positioned as the daily AI companion for every employee, which makes Copilot the dominant archetype. This is also the head-to-head with Microsoft Cowork — our defence isn't a different archetype, it's better reach (frontline + desk) and stronger signal (Seer + cross-pillar data).
- **Vulnerability Scores:** Moat 4/5 · Data 4/5 · Platform 3/5
- **Top Risk:** *One line: what's the single biggest strategic risk?*
- **Confidence:** H
- **Prototype:** https://workvivo-hq.replit.app/
- **Kill Criteria:** in each kill case, we prioritise a move to deeper LMM extensibility - so Workvivo remains the epxerience layer; while deprioritsing spend on AI features that aren't landing well enought ot warrant the spend: - Microsoft extends Copilot Cowork with a credible EX skill pack (recogn…

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:**
- **Weakest Loop:** Loop 1 — Usage → Correction
- **Top Encroachment Threat:**
- **Encroachment Defense:** Build on what's already working. Ask HQ already surfaces content gaps to admins — that's a working surface-to-surface signal flow, just one that routes through a person.…
- **Vendor Portability:** Partial.

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):**
- **Gross Margin (AI-adjusted):**
- **Pricing Model:** Hybrid tier-based seat pricing + consumption-based overage. Customers buy seats at the tier that matches the user's expected AI usage. Each seat includes a credit allocation. Usage above the allocation is PAYG at per-action rates.
- **Pricing Today → Tomorrow:**
- **Total AI COGS / unit:**
- **Cascading Strategy:** ratio 20% lightweight / 65% standard / 15% advanced.
- **Net Margin Shift:**
- **Break-even at:**

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 90% on the golden dataset, checked weekly. Zero tolerance for fabrication on policy, personnel, legal, or financial content.
- **Golden Dataset:** 7 rows, 3 adversarial
- **Confidence UX:** Legibility before precision. Workvivo HQ shows confidence as a composite signal across every AI surface — Ask HQ, Catch Me Up, Seer, Compose, Liquid Content — surfaces the data driving each prediction, and routes sensiti…
- **HITL Architecture:** **When a human steps in:** Three triggers, applied across all HQ AI surfaces. The model's confidence falls below 70%. The content or action is sensitive — DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages, anythin…
- **Failure Mode Coverage:** Engagement prediction calibration (does "90% predicted" actually mean 90% in production?); multilingual tone validation for regional variants of sensitive content; historical data poisoning (model learning the wrong pattern from low-quality…

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | **Recursive Learning** | User feedback (thumbs up/down, free text) across every AI surface — AI Content Assistant, AI Recap…
- **Governance Posture:** All AI features inside Workvivo HQ across the three pillars — Communication & Engagement (AI Content Assistant, AI Recap), Search & Knowledge (AI Answers, Q&A, AI Recap), People Intelligence (Seer, Sentiment Analysis, Ma…
- **Autonomy Boundaries:** - **Drafting and retrieval — auto.** HQ AI can draft content, retrieve from the knowledge layer, summarise, and predict whatever a user asks for, without approval. Reading and drafting are read-only.…
- **Escalation Triggers:** - Confidence drops below 70%
- **Audit Cadence:** - **Weekly:** Automated eval against the 7-row golden dataset. CI/CD gated. Owner: HQ AI PM.
- **Shadow AI Audit (user-side):** 13 workarounds found · 3 keep, 7 govern, 3 kill (with Gamma and HeyGen-class tools split between kill at personal tier / govern at corporate tier). Net: roughly 10 sanctioned categories under clear governance, down from a long tail of personal subscriptions. build candidates · adjacent spend $10K–$18K per month across personal subscriptions and unsanctioned team accounts. This is also the budget for the governed alternative once we consolidate — and it's the number that gets the CFO's attention faster than the risk argument does.
- **Agent Boundaries:** Workvivo HQ AI isn't a chain of named agents. It's three product pillars, each with its own AI capabilities and autonomy boundaries, sitting on a shared AI Engine foundation (Zoom AI Companion).…
- **Regulatory Exposure:** - **Data residency:** Customer data is processed in the customer's chosen region — US or EU. EU customers' AI features are powered by Zoom-hosted models plus Anthropic models via Amazon Bedrock on AWS.…

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):** **Search & Knowledge pillar AI** — Agentic Search and AI Search & Retrieval across the customer's knowledge layer (Pages, Knowledge Hubs, policies, past campaigns), user-generated content (posts, comments, recognition), and an initial set of major enterprise connectors (M365, SharePoint, ServiceNow, Workday, Slack, Salesforce, etc.). Foundation for the full connector ecosystem rolling out in H2. · **Communication & Engagement pillar AI** — Catch Me Up (AI Recap), AI Compose integrated across surfaces (Posts, Chat, Pages, Journeys, etc.), AI Compose Profile with Persona / Emotional / Style Controls, AI Compose Posts, AI Compose in Chat, AI Livestream Summaries, Livestream Smart Chapters, AI Chat Summaries, AI Journey Builder, AI Page Builder, AI Widget Builder, AI Podcasts from Articles. · **People Intelligence pillar AI** — Seer AI Summaries, Seer AI Recommended Actions, Seer AI Topic Grouping, AI Insights in Advanced Analytics. · **Seer Standalone — Glint replacement** (new commercial motion, sells without core Workvivo platform contract)
- **Horizon 2 (Next):** **HQ+ Enterprise / ZoomMate full agentic execution** — multi-step workflows across HRIS, ITSM, finance, calendar; cross-system task completion; co-sold with Zoom enterprise team. Powered by the **full 1000+ connector ecosystem for agentic orchestration** (extending the launch connector set into the long tail of enterprise systems). · **Automated actions in Seer** — Seer moves from recommending interventions to executing them with human-in-the-loop approval. Detected sentiment themes trigger manager outreach, journey assignment, content suggestions automatically. · **Network Intelligence loop activated** — privacy-gated cross-customer learning, industry-specific defaults (healthcare, manufacturing, financial services tuned baselines). Aggregated patterns inform new-customer setup and benchmarking without exposing customer-specific data.
- **Horizon 3 (Bet):** **AI Liquid Content — the campaign orchestrator** — multi-format content generation from a single brief, predicted engagement scoring, optimal send-time recommendation, AI reasoning surfaced per recommendation. The next-level campaign tier Workvivo led with in the original product strategy course. · **Presentations builder** — AI-generated presentation decks from briefs, comms calendar events, or campaign source material. Bridges the gap between comms creation and the formats execs actually consume. · **Zoom AI Docs integration** — full integration with Zoom Docs as a cross-platform knowledge source and creation surface. Signal flows both directions — Workvivo HQ surfaces Zoom Docs context; comms created in HQ surface in Zoom Docs. · **Connected intelligence from HRIS, L&D, and other sources** — deeper People Intelligence by integrating workforce data beyond engagement: skills, learning paths, role transitions, retention signals. Maps engagement to other key initiatives (DEI, learning outcomes, manager development) for a complete view of company and people health. · **Loop 1 fully closed — Recursive Learning compounds** (corrections feed model improvement at the speed the product needs; freeze test answer flips from "we'd still win" to "accuracy would visibly slip") · **Cross-Domain Transfer fully automated between pillars** — three pillars share learning signals without human routing
- **Board Narrative:** Workvivo HQ is the AI-native headquarters for every employee — three product pillars on one platform, fed by an expanding connector ecosystem (major enterprise systems at launch, 1000+ in H2) plus user-generated content competitors structurally can't see, priced at $6 combined to…
- **Ask:** Accelerate Loop 1 closure from H3 into H2. The roadmap shows Loop 1 fully closed as a 9–18 month outcome, which is the right ambition — but our H2 bets all depend on it working sooner.…
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)
