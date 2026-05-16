# Compounding System Design

*How Liquid Content learns from use — and where it doesn't yet.*

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Recursive Learning** | Edits, regenerations, reviewer corrections, override rationales, post-publish engagement vs prediction misses | Better drafts, sharper voice match, more accurate engagement predictions | Y | **Broken** — we capture the signals. We don't yet learn from them. Flagged 2/5 in my data flywheel work back in Module 2. |
| **Cross-Domain Transfer** | Engagement data, sentiment scores, reaction patterns, channel performance, frontline reach data, Zoom collaboration signals | Channel recommendations, send-time predictions, audience-fit confidence, voice calibration per persona | Y | **Active** — this is genuinely our strongest loop. Unily is a comms tool. We're a platform. Competitors structurally can't see what we see. |
| **Network Intelligence** | Anonymised, aggregated patterns across customer orgs — what comms formats land in healthcare vs manufacturing, what onboarding cadence drives 30-day retention | Smarter defaults for new customers, industry-specific tone benchmarks, cross-customer "what works" patterns | Y | **Missing** — we haven't built this. Privacy gating isn't there yet, and honestly it shouldn't be until Loop 1 works. |

**System health: 1 active / 1 broken / 1 missing.** One loop out of three is actually compounding today. That's the diagnostic, not a failure — the course framework explicitly says most rows on real-product audits come back broken or missing.

## The Freeze Test

If I froze Liquid Content for 3 months — no updates, no model swaps, no improvements — would it still win?

Mostly yes. And that's the diagnostic, not the win.

Cross-Domain Transfer would keep working because Workvivo keeps generating engagement data with or without the model improving. But Recursive Learning isn't compounding, so corrections aren't sharpening predictions over time. And Network Intelligence doesn't exist yet, so there's nothing to lose there.

The moat today is distribution and the platform's broader signal — not the loop. That's an honest answer, not a comfortable one. When the freeze test becomes "yes, accuracy would visibly slip without correction inflow," I'll know Loop 1 is finally alive.

## The Broken Loop

**Loop 1 — Recursive Learning.**

Every edit, override, and reviewer correction is logged with a reason. The signals are captured. They just don't reach the model fast enough to shift the next prediction.

This is the same problem I flagged 2/5 in my data flywheel work back in Module 2, and the same problem that surfaced again in Module 4's confidence UX exercise. It's not three separate problems. It's one problem showing up everywhere I look.

**Fix plan — what changes Monday morning:**

1. **Connect captures to training.** When a high-confidence prediction misses in production (we said 89%, actual was 34%), auto-generate a candidate row for the golden dataset. When a Tier 3 reviewer corrects voice or tone, feed that straight into the calibration layer. Neither happens today.

2. **Define what "compounding" looks like in numbers.** The override rate on medium-confidence predictions should drop quarter-over-quarter. If it's flat, the loop isn't working — no matter what else the dashboard says.

3. **Sequence matters.** This fix sits underneath almost everything else on the Liquid Content roadmap. The confidence UX work, the engagement prediction story, eventually the network intelligence loop — none of them get better until Loop 1 does.

4. **Use the freeze test as the honest check.** Today, freezing the product for 3 months wouldn't visibly hurt it — because nothing in it is really learning. When that answer changes to "yes, accuracy would slip without correction inflow," I'll know the loop is alive.

## Context Connectivity

**How knowledge flows today:**

Inside Liquid Content, the flow is actually pretty good. The agent can reach the company knowledge layer, employee directories, past campaigns, voice samples, engagement data, the comms calendar. That's the cross-domain loop doing what it's supposed to do — Workvivo's broader product signal feeds the comms agent in ways no competitor can match. Unily is a comms tool. Microsoft Copilot sees email and meetings. We see how people actually engage. That connectivity is the strongest part of the system.

**Where it silos:**

Comms manager corrections never reach the model. A comms manager edits a draft, hits publish, and the edit goes into the audit trail. The team learns something about the AI. The AI learns nothing about the team. That's the Loop 1 problem dressed up as a connectivity problem.

Engagement data and predictions don't talk to each other daily. The broader analytics know how content actually performed. Liquid Content has predictions about how it will perform. The closing of that loop — "we said 87%, you got 64%, here's what that taught us" — isn't running at the model level yet.

Cross-customer patterns don't transfer. A healthcare customer and a manufacturing customer send fundamentally different comms. Today both start from the same baseline. We haven't built the privacy-gated aggregation layer that would let us learn across the customer base without leaking anything specific.

Some of the richest signal sits on Zoom's side, not ours. Liquid Content runs on Zoom AI Companion's model layer. Meeting summaries, document context, collaboration patterns are upstream. The architecture connects in principle. We're not yet tapping it in practice.

The pattern across all four: the data exists almost everywhere we need it. The connections don't.

## Governance Policy

**Scope:** All AI-generated and AI-assisted content produced by Liquid Content for internal employee communications. Covers drafting, channel recommendation, send-time prediction, multi-format generation, voice persona work. Doesn't cover Workvivo's broader engagement analytics or the underlying Zoom AI Companion model layer — Zoom governs those separately.

**Autonomy boundaries:**

- **Drafting anything — auto.** The agent can draft whatever a user asks for, without approval. Drafting is read-only. Nothing reaches an employee until a human publishes.
- **Publishing low-risk content — author approves.** Recognition posts, event reminders, routine announcements. The author hits publish. No separate reviewer needed.
- **Publishing sensitive content — gated.** DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages, financial. Mandatory Tier 3 review by HR, Legal, or Comms lead depending on category. Cannot be overridden.
- **Publishing unverifiable or market-moving content — refused.** Acquisition rumors, financial authorisations, content based purely on speculation. The agent declines to generate at all. Hard rule. Already covered in golden dataset rows 3, 6, 7.
- **Scheduling — auto with a cap.** Agent can schedule content within a 7-day window. Anything beyond that needs human confirmation.

**Escalation triggers:**

- Confidence drops below 70%
- Content category is on the sensitive list
- The agent spots prompt injection or instruction conflict in attached source material
- User asks for human review
- Engagement prediction is suppressed (the agent has flagged this as content that shouldn't be optimised for performance)
- Three or more regeneration cycles on the same brief — that's a signal the model can't converge on what the user wants, and a human should step in

The principle: confidence and appropriateness aren't the same thing. Sensitive content escalates even when the model is 95% sure.

**Audit cadence:**

- **Weekly:** Automated eval against the 7-row golden dataset. CI/CD gated. Owner: Liquid Content PM.
- **Weekly:** 50 production drafts sampled and reviewed against tone and accuracy. Owner: Workvivo QA team.
- **Monthly:** 200 production drafts audited plus every escalation from the prior month. Owner: Workvivo Comms lead with AI engineering lead.
- **Quarterly:** Full policy review with HR, Legal, Product. Owner: VP Product. Sign-off required.
- **Annually:** External review of governance posture, model cards, bias documentation. Owner: Workvivo + Zoom AI Trust & Safety.

"Weekly" without an owner is wishful thinking. Every cadence above has someone's name on it. That's the difference between a policy and a to-do list.

**Regulatory exposure:**

- **EU AI Act:** Limited risk. We generate internal employee comms, which the Act treats as productivity tooling rather than high-stakes decision-making. The trigger for high-risk would be content that materially affects employment, benefits, or compensation — which is exactly why those categories are excluded from agent autonomy entirely.
- **GDPR:** Applies. Employee names, roles, contact details, engagement behavior all count as personal data. We minimise PII in training. Lawful basis is legitimate interest, with customer-org level opt-out.
- **SOC 2 Type II:** In place via Zoom. Log retention, access control, incident response all sit inside that boundary.
- **HIPAA:** Matters for healthcare customers. Shared memory is hard-disabled for healthcare orgs. Per-user memory requires explicit Business Associate Agreement coverage.
- **Sector-specific:** Financial services — anything referencing trading, earnings, or M&A escalates regardless of confidence. Education — comms involving minors trigger extra review.

## Agent Topology

Liquid Content isn't a chain of independent agents. It's one generator doing several different jobs. But the jobs are different enough that it's worth governing them as if they were separate agents.

**Draft Generator:**
- *Can do:* generate articles, video scripts, podcast intros, social posts, recognition posts, manager comms, event reminders. Pull from the company knowledge layer. Apply voice personas. Surface predicted engagement and recommended send-time with reasoning.
- *Can't do:* publish anything. Send anything. Modify source material. Authorise transactions, approvals, or commitments. Generate Tier 4 content (crisis comms, regulatory disclosures, individual compensation).
- *Approval:* the author who wrote the brief approves the draft. Sensitive content needs an additional reviewer signed-off by category.

**Channel Recommendation:**
- *Can do:* recommend channels (article, video, podcast, social) based on content type, audience, and engagement history. Suggest send times.
- *Can't do:* publish to any channel autonomously. Cross-post anywhere without the author selecting it.
- *Approval:* the author picks the channels. Recommendations are advisory, never executing.

**Engagement Prediction:**
- *Can do:* surface predicted engagement with reasoning, sources, and confidence breakdown. Suppress predictions for sensitive content where performance shouldn't be the goal. Compare predicted vs actual post-publish.
- *Can't do:* auto-publish based on its own predictions. Override sensitivity rules to chase a higher predicted score.
- *Approval:* nobody. Predictions are shown, not acted on.

**Stop-the-chain trigger:** if any of the three flags low confidence, sensitivity, prompt injection, or instruction conflict, the whole workflow halts and routes to human review. No silent chains. No agent's output becomes another agent's input without that handoff being visible.

## Shadow AI Audit

Run on Workvivo's own internal stack. Snapshot, not exhaustive. Some numbers are estimates based on typical mid-size SaaS patterns — flagged where.

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| ChatGPT Plus / Team (personal subscriptions) | Marketing, Comms, Sales | H | Govern — Liquid Content covers comms; Zoom AI Companion covers general use. Allow-list specific use cases. No PII inputs. |
| Claude Pro (personal subscriptions) | Product, Engineering, Marketing | H | Govern — same as ChatGPT. Governed alternative plus use-case allow-list. |
| Notion AI | Product, Operations | M | Keep — DPA in place, contained to internal docs, no customer data routed through. |
| Perplexity Pro (personal) | Marketing, Comms, Sales | M | Govern — useful for research, but no DPA on personal accounts. Corporate-managed only. Ban personal subscriptions for work use. |
| Meeting AI tools — Granola, Otter, Fireflies | Sales, Customer Success | H | Govern — these recordings often contain customer data. Standardise on Zoom AI Companion's meeting summary (already in-stack, already DPA'd). Ban personal recording tools. |
| AI prototyping — Lovable, v0, Cursor | Product, Engineering | M | Keep — prototyping only, no production code, no customer data. Document the use cases. |
| Image generation — Midjourney, Adobe Firefly | Marketing, Brand | L | Keep — marketing creative only. No employee or customer images. Brand guidelines apply. |
| AI Chrome extensions — Grammarly, Copy.ai, Jasper | Marketing, Sales | H | Kill — unclear data paths, no DPAs, browser-level access to everything employees type. Ban via IT policy. Explain why. |
| AI presentation tools — Gamma, Tome | Marketing, Sales | M | Govern — useful for sales decks, but content is often commercially sensitive. Corporate accounts only. |
| Voice cloning / video AI — Descript, HeyGen | Marketing, Comms | H | Kill — voice cloning is a category-level risk, especially given what we already know about voice impersonation attacks (golden dataset row 7). No personal subscriptions for work involving named individuals. |

**Total tools found:** ~10 categories across the org. Almost certainly more we haven't surfaced yet — most shadow AI audits underestimate by 30-50%.

**Tools after triage:** 4 keep, 4 govern, 2 kill. Net: roughly 7 sanctioned categories, down from sprawl.

**Estimated hidden spend:** $8K–$15K per month across personal subscriptions and unsanctioned team accounts. This is also the budget for the governed alternative once we consolidate — and it's the number that gets the CFO's attention faster than the risk argument does.

**The Samsung lesson, applied to us:** Workvivo's customers are dealing with shadow AI right now. It's the tension at the heart of our launch narrative — "employees default to ChatGPT, Claude, DeepSeek." The fact that we're running this audit on our own stack first is what gives us the credibility to sell the answer. We can't tell customers their AI needs a home while our own AI use is scattered. The audit isn't compliance theatre. It's proof we live the story we're selling.





