# Compounding System Design

*How Workvivo HQ learns from use — and where it doesn't yet. HQ is the AI-native employee experience platform, powered by Workvivo AI alongside Zoom AI Companion. Liquid Content is one feature inside HQ; this doc covers the compounding system across the full HQ AI surface.*

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Recursive Learning** | User feedback (thumbs up/down, free text) across every AI surface — Ask HQ, Catch Me Up, Liquid Content, Compose, Seer. Edits, regenerations, reviewer corrections, override rationales, post-publish engagement vs prediction misses. | Better drafts, sharper voice match, more accurate engagement predictions, more relevant retrieval, smarter sentiment thresholds | Y | **Broken** — we capture the signals. Workvivo AI explicitly collects user feedback for product improvement. But the signals don't reach the model fast enough to shift the next prediction. Flagged 2/5 in the data flywheel work back in Module 2. Same problem surfaced again in Module 4's confidence UX exercise. |
| **Cross-Domain Transfer** | Engagement data, sentiment scores, reaction patterns, channel performance, frontline reach data, survey responses, Ask HQ search patterns, recognition signals, Zoom collaboration signals via AI Companion | Channel recommendations, send-time predictions, audience-fit confidence, voice calibration per persona, content gap detection, sentiment-aware draft suggestions | Y | **Active** — this is genuinely our strongest loop and the moat. HQ sits across four pillar agents (Navigator, Communicator, Coach, Operator) all feeding the same platform signal. Compose feeds Ask feeds Seer feeds Catch Me Up feeds Liquid Content. Unily is a comms tool. Microsoft Copilot sees email and meetings. Glean indexes work product. We're the only platform that sees how every employee actually feels and what they engage with. Competitors structurally can't see what we see. |
| **Network Intelligence** | Anonymised, aggregated patterns across customer orgs — what comms formats land in healthcare vs manufacturing, what onboarding cadence drives 30-day retention, what sentiment patterns predict attrition across industries | Smarter defaults for new customers, industry-specific tone benchmarks, cross-customer "what works" patterns, faster time-to-value for new HQ deployments | Y | **Missing** — we haven't built this. Privacy gating isn't there yet, and honestly it shouldn't be until Loop 1 works. Zoom's zero data retention policy with third-party model providers means the foundation is in place to build it safely when the time comes. |

**System health: 1 active / 1 broken / 1 missing.** One loop out of three is actually compounding today. That's the diagnostic, not a failure — the course framework explicitly says most rows on real-product audits come back broken or missing.

## The Freeze Test

If I froze Workvivo HQ for 3 months — no updates, no model swaps, no improvements — would it still win?

Mostly yes. And that's the diagnostic, not the win.

Cross-Domain Transfer would keep working because Workvivo keeps generating engagement, sentiment, and survey data with or without the model improving. The strongest loop is structural to the platform, not to the AI tier specifically. But Recursive Learning isn't compounding, so corrections aren't sharpening predictions over time. And Network Intelligence doesn't exist yet, so there's nothing to lose there.

The moat today is distribution, the Zoom partnership, the four-pillar surface area, and the broader Workvivo platform signal — not the AI learning loop. That's an honest answer, not a comfortable one. When the freeze test becomes "yes, accuracy would visibly slip without correction inflow," we'll know Loop 1 is finally alive.

## The Broken Loop

**Loop 1 — Recursive Learning.**

User feedback is explicitly collected — per the Workvivo AI explainer, free-text feedback is used for product improvement. Every edit, override, and reviewer correction is logged with rationale across every HQ AI surface. The signals are captured. They just don't reach the model fast enough to shift the next prediction.

This is the same problem flagged 2/5 in the data flywheel work back in Module 2, and the same problem that surfaced again in Module 4's confidence UX exercise. It's not three separate problems. It's one problem showing up everywhere we look.

**Fix plan — what changes Monday morning:**

1. **Connect captures to training.** When a high-confidence prediction misses in production (we said 89%, actual was 34%), auto-generate a candidate row for the golden dataset. When a Tier 3 reviewer corrects voice or tone, feed that straight into the calibration layer. When Ask HQ logs repeated content gaps, surface them to comms managers as Liquid Content suggestions. Neither of those handoffs happens automatically today.
2. **Define what "compounding" looks like in numbers.** The override rate on medium-confidence predictions should drop quarter-over-quarter. If it's flat, the loop isn't working — no matter what else the dashboard says.
3. **Sequence matters.** This fix sits underneath almost everything else on the HQ AI roadmap. The confidence UX work, the engagement prediction story, eventually the network intelligence loop — none of them get better until Loop 1 does.
4. **Use the freeze test as the honest check.** Today, freezing the product for 3 months wouldn't visibly hurt it — because nothing in it is really learning. When that answer changes to "yes, accuracy would slip without correction inflow," we'll know the loop is alive.

This is the moat-deepening move Microsoft can't ship from the Copilot stack without giving up their own governance position. The cross-pillar orchestration we're missing is exactly the layer that compounds at the platform without training on customer data — and it's the layer Workvivo's architecture is uniquely able to build.

## Context Connectivity

**How knowledge flows today:**

Inside Workvivo HQ, the cross-pillar flow is actually pretty good. The platform has access to the company knowledge layer, employee directories, past campaigns, voice samples, engagement data, the comms calendar, and signals from Compose, Ask HQ, Surveys, Liquid Content, Catch Me Up, and Seer. That's the Cross-Domain Transfer loop doing what it's supposed to do. Microsoft Copilot sees email and meetings. Unily sees content. Glean indexes work product. We see how every employee actually engages with everything — and how they feel about it. That connectivity is the strongest part of the system.

**Where it silos:**

Comms manager corrections never reach the model fast enough. A comms manager edits a Liquid Content draft, hits publish, and the edit goes into the audit trail. The team learns something about the AI. The AI eventually learns from the feedback, but not at the speed it needs to. That's the Loop 1 problem dressed up as a connectivity problem.

Engagement data and predictions don't talk to each other daily. The broader Workvivo analytics know how content actually performed. Liquid Content has predictions about how it will perform. The closing of that loop — "we said 87%, you got 64%, here's what that taught us" — isn't running at the model level yet.

The four pillar agents don't yet share learning signals as tightly as they could. Ask HQ logs employee searches and surfaces content gaps to admins as insights — that's a working surface-to-surface flow, but it routes through a human. The automated handoff doesn't exist yet: when Seer detects a sentiment theme, Compose doesn't auto-suggest content in the right voice; when Ask HQ flags a gap, Liquid Content doesn't auto-draft a candidate; when an engagement prediction misses, the calibration layer doesn't auto-learn for next time.

Cross-customer patterns don't transfer. A healthcare customer and a manufacturing customer send fundamentally different comms. Today both start from the same baseline. We haven't built the privacy-gated aggregation layer that would let us learn across the customer base without leaking anything specific.

The pattern across all four: the data exists almost everywhere we need it. The connections don't.

## Governance Policy

**Scope:** All AI features inside Workvivo HQ — Ask HQ, Catch Me Up, Liquid Content, Compose, Seer AI, and the broader AI surface across the four pillar agents (Navigator, Communicator, Coach, Operator). HQ+ Enterprise agentic execution (ZoomMate) sits within this scope when delivered to Workvivo customers, but is also subject to Zoom's parallel governance regime for the broader ZoomMate platform.

**Autonomy boundaries:**

- **Drafting and retrieval — auto.** HQ AI can draft content, retrieve from the knowledge layer, summarise, and predict whatever a user asks for, without approval. Reading and drafting are read-only. Nothing reaches an employee until a human publishes or acts.
- **Publishing low-risk content — author approves.** Recognition posts, event reminders, routine announcements, internal newsletters. The author hits publish. No separate reviewer needed.
- **Publishing sensitive content — gated.** DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages, financial. Mandatory Tier 3 review by HR, Legal, or Comms lead depending on category. Cannot be overridden.
- **Publishing unverifiable or market-moving content — refused.** Acquisition rumors, financial authorisations, content based purely on speculation. The agent declines to generate at all. Hard rule. Already covered in golden dataset rows 3, 6, 7.
- **Scheduling — auto with a cap.** Liquid Content can schedule content within a 7-day window. Anything beyond that needs human confirmation.
- **Agentic execution (HQ+ Enterprise / ZoomMate) — gated by category.** Cross-system actions (HRIS approvals, finance system changes, regulatory disclosures) require human approval at the action point, not just at the draft point. Material business actions are Tier 4 — AI off entirely.

**Escalation triggers:**

- Confidence drops below 70%
- Content category is on the sensitive list
- The agent spots prompt injection or instruction conflict in attached source material
- User asks for human review
- Engagement prediction is suppressed (the agent has flagged this as content that shouldn't be optimised for performance)
- Three or more regeneration cycles on the same brief — that's a signal the model can't converge on what the user wants, and a human should step in
- Agentic action would write to a system of record (HRIS, finance, legal) — requires explicit human approval at the action point

The principle: confidence and appropriateness aren't the same thing. Sensitive content escalates even when the model is 95% sure. Agentic execution escalates even when the action is routine — because the cost of an automated mistake in a system of record is much higher than the cost of friction.

**Audit cadence:**

- **Weekly:** Automated eval against the 7-row golden dataset. CI/CD gated. Owner: HQ AI PM.
- **Weekly:** 50 production drafts sampled and reviewed against tone and accuracy. Owner: Workvivo QA team.
- **Monthly:** 200 production drafts audited plus every escalation from the prior month. Owner: Workvivo Comms lead with AI engineering lead.
- **Quarterly:** Full policy review with HR, Legal, Product. Owner: VP Product. Sign-off required.
- **Annually:** External review of governance posture, model cards, bias documentation. Owner: Workvivo + Zoom AI Trust & Safety.

"Weekly" without an owner is wishful thinking. Every cadence above has someone's name on it. That's the difference between a policy and a to-do list.

**Regulatory exposure:**

- **Data residency:** Customer data is processed in the
