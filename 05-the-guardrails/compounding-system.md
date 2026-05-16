# Compounding System Design

*How Liquid Content learns from use — and where it doesn't yet. Liquid Content is the multi-format comms agent inside the Workvivo AI platform, powered by Workvivo AI alongside Zoom AI Companion.*

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Recursive Learning** | User feedback (thumbs up/down, free text), edits, regenerations, reviewer corrections, override rationales, post-publish engagement vs prediction misses | Better drafts, sharper voice match, more accurate engagement predictions | Y | **Broken** — we capture the signals. Workvivo AI explicitly collects user feedback for product improvement. But the signals don't reach the model fast enough to shift the next prediction. Flagged 2/5 in my data flywheel work back in Module 2. |
| **Cross-Domain Transfer** | Engagement data, sentiment scores, reaction patterns, channel performance, frontline reach data, survey responses, Zoom collaboration signals via AI Companion | Channel recommendations, send-time predictions, audience-fit confidence, voice calibration per persona | Y | **Active** — this is genuinely our strongest loop. Liquid Content sits inside Workvivo AI, which sits inside the wider Workvivo platform. Compose feeds Ask feeds Employee Insights feeds Liquid Content. Unily is a comms tool. We're a platform with a comms feature. Competitors structurally can't see what we see. |
| **Network Intelligence** | Anonymised, aggregated patterns across customer orgs — what comms formats land in healthcare vs manufacturing, what onboarding cadence drives 30-day retention | Smarter defaults for new customers, industry-specific tone benchmarks, cross-customer "what works" patterns | Y | **Missing** — we haven't built this. Privacy gating isn't there yet, and honestly it shouldn't be until Loop 1 works. Zoom's zero data retention policy with third-party model providers means the foundation is in place to build it safely. |

**System health: 1 active / 1 broken / 1 missing.** One loop out of three is actually compounding today. That's the diagnostic, not a failure — the course framework explicitly says most rows on real-product audits come back broken or missing.

## The Freeze Test

If I froze Liquid Content for 3 months — no updates, no model swaps, no improvements — would it still win?

Mostly yes. And that's the diagnostic, not the win.

Cross-Domain Transfer would keep working because Workvivo keeps generating engagement and survey data with or without the model improving. But Recursive Learning isn't compounding, so corrections aren't sharpening predictions over time. And Network Intelligence doesn't exist yet, so there's nothing to lose there.

The moat today is distribution, the Zoom partnership, and the broader Workvivo AI platform signal — not the loop. That's an honest answer, not a comfortable one. When the freeze test becomes "yes, accuracy would visibly slip without correction inflow," I'll know Loop 1 is finally alive.

## The Broken Loop

**Loop 1 — Recursive Learning.**

User feedback is explicitly collected — per the Workvivo AI explainer, free-text feedback is used for product improvement. Every edit, override, and reviewer correction is logged with rationale. The signals are captured. They just don't reach the model fast enough to shift the next prediction.

This is the same problem I flagged 2/5 in my data flywheel work back in Module 2, and the same problem that surfaced again in Module 4's confidence UX exercise. It's not three separate problems. It's one problem showing up everywhere I look.

**Fix plan — what changes Monday morning:**

1. **Connect captures to training.** When a high-confidence prediction misses in production (we said 89%, actual was 34%), auto-generate a candidate row for the golden dataset. When a Tier 3 reviewer corrects voice or tone, feed that straight into the calibration layer. Neither happens today.

2. **Define what "compounding" looks like in numbers.** The override rate on medium-confidence predictions should drop quarter-over-quarter. If it's flat, the loop isn't working — no matter what else the dashboard says.

3. **Sequence matters.** This fix sits underneath almost everything else on the Liquid Content roadmap. The confidence UX work, the engagement prediction story, eventually the network intelligence loop — none of them get better until Loop 1 does.

4. **Use the freeze test as the honest check.** Today, freezing the product for 3 months wouldn't visibly hurt it — because nothing in it is really learning. When that answer changes to "yes, accuracy would slip without correction inflow," I'll know the loop is alive.

## Context Connectivity

**How knowledge flows today:**

Inside Liquid Content, the flow is actually pretty good. The feature sits on the Workvivo AI platform, which sits inside the wider Workvivo product — so it has access to the company knowledge layer, employee directories, past campaigns, voice samples, engagement data, the comms calendar, and signals from Compose, Ask, Surveys, and Employee Insights. That's the cross-domain loop doing what it's supposed to do. Unily is a comms tool. Microsoft Copilot sees email and meetings. We see how people actually engage with everything. That connectivity is the strongest part of the system.

**Where it silos:**

Comms manager corrections never reach the model fast enough. A comms manager edits a Liquid Content draft, hits publish, and the edit goes into the audit trail. The team learns something about the AI. The AI eventually learns from the feedback, but not at the speed it needs to. That's the Loop 1 problem dressed up as a connectivity problem.

Engagement data and predictions don't talk to each other daily. The broader Workvivo analytics know how content actually performed. Liquid Content has predictions about how it will perform. The closing of that loop — "we said 87%, you got 64%, here's what that taught us" — isn't running at the model level yet.

Liquid Content and the other Workvivo AI features don't yet share learning signals as tightly as they could. Ask, Compose, Liquid Content, Employee Insights — each is improving. They aren't yet compounding into each other. When Ask consistently surfaces a policy question that doesn't have a clear answer in the knowledge base, that signal should flow back to Liquid Content as a content gap to fill — and to Employee Insights as a sentiment indicator. Today, those features ship separately rather than learning together.

Cross-customer patterns don't transfer. A healthcare customer and a manufacturing customer send fundamentally different comms. Today both start from the same baseline. We haven't built the privacy-gated aggregation layer that would let us learn across the customer base without leaking anything specific.

The pattern across all four: the data exists almost everywhere we need it. The connections don't.

## Governance Policy

**Scope:** All content generated by Liquid Content — the multi-format comms agent inside the Workvivo AI platform. Covers drafting, channel recommendation, send-time prediction, multi-format generation, voice persona work. Sits within the broader Workvivo AI governance posture (which also covers Compose, Surveys, Ask, and Employee Insights). The underlying Zoom AI Companion model layer is governed separately by Zoom under its federated AI architecture.

**Autonomy boundaries:**

- **Drafting anything — auto.** Liquid Content can draft whatever a user asks for, without approval. Drafting is read-only. Nothing reaches an employee until a human publishes.
- **Publishing low-risk content — author approves.** Recognition posts, event reminders, routine announcements. The author hits publish. No separate reviewer needed.
- **Publishing sensitive content — gated.** DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages, financial. Mandatory Tier 3 review by HR, Legal, or Comms lead depending on category. Cannot be overridden.
- **Publishing unverifiable or market-moving content — refused.** Acquisition rumors, financial authorisations, content based purely on speculation. The agent declines to generate at all. Hard rule. Already covered in golden dataset rows 3, 6, 7.
- **Scheduling — auto with a cap.** Liquid Content can schedule content within a 7-day window. Anything beyond that needs human confirmation.

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

- **Data residency:** Customer data is processed in the customer's chosen region — US or EU. EU customers' AI features are powered by Zoom-hosted models plus Anthropic models via Amazon Bedrock on AWS. This is a real procurement advantage, not boilerplate — EU buyers ask for it by name.

- **No training on customer content.** Workvivo does not use customer content to train Zoom's or third-party AI models. This is a published commitment, not aspiration. It's also the one line in the Workvivo AI explainer that closes the most enterprise deals.

- **Zero data retention with third-party providers.** Zoom has zero data retention policies in place with third-party model providers (including Anthropic). Customer prompts and outputs are not retained by model providers, with limited exceptions for trust and safety (e.g. CSAM detection). This is genuinely differentiated — most consumer AI tools can't claim this.

- **Workvivo audit retention:** Customer inputs and outputs are stored in the Workvivo audit database for 12 months by default to fulfil data access requests, or shorter at customer election.

- **EU AI Act:** Limited risk. Liquid Content generates internal employee comms, which the Act treats as productivity tooling. The trigger for high-risk would be content that materially affects employment, benefits, or compensation — which is exactly why those categories are excluded from agent autonomy entirely.

- **GDPR:** Applies. Employee names, roles, contact details, engagement behaviour all count as personal data. Lawful basis is legitimate interest, with customer-org level opt-out.

- **SOC 2 Type II:** In place via the Zoom platform. Log retention, access control, incident response all sit inside that boundary.

- **HIPAA:** Matters for healthcare customers. Shared memory hard-disabled for healthcare orgs. Per-user memory requires explicit Business Associate Agreement coverage.

- **Sector-specific:** Financial services — anything referencing trading, earnings, or M&A escalates regardless of confidence. Education — comms involving minors trigger extra review.

## Agent Topology

Liquid Content isn't a chain of independent agents. It's one feature inside Workvivo AI doing several different jobs. But the jobs are different enough that it's worth governing them as if they were separate agents.

**Draft Generator:**
- *Can do:* generate articles, video scripts, podcast intros, social posts, recognition posts, manager comms, event reminders. Pull from the company knowledge layer (via the Workvivo AI platform). Apply voice personas. Surface predicted engagement and recommended send-time with reasoning.
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

Run on Workvivo's own internal stack. Snapshot, not exhaustive. Some numbers are estimates based on typical mid-size SaaS patterns — flagged where. Each entry has been pressure-tested against published vendor data handling policies, not just gut feel.

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| ChatGPT Plus / Team (personal subscriptions) | Marketing, Comms, Sales | H | Govern — Liquid Content covers comms; Zoom AI Companion covers general use. Allow-list specific use cases. No PII inputs. |
| Claude.ai (personal Pro / Team / Free accounts) used for design, copywriting, brainstorming | Marketing, Comms, Brand, Product, Sales | H | Govern (with teeth). Anthropic is a Workvivo subprocessor via Zoom, so Claude isn't categorically banned — but personal Claude.ai accounts don't carry the same data protections. Since Anthropic's September 2025 policy shift, Pro/Free/Team accounts default to training on user conversations unless individually opted out, and retention extended from 30 days to 5 years for opted-in users. Most employees clicked through the forced-choice gate without realising. For a marketing team using Claude to brainstorm launch copy, draft campaign briefs, or workshop competitive positioning, this means brand assets, unreleased product details, and strategic thinking could now train future models for half a decade. The fix: ban personal Claude.ai subscriptions for work. Route creative use cases into Workvivo AI (which reaches Claude through Zoom's federated layer with zero data retention at the model provider level) or, for use cases that genuinely need direct Claude access, provision a corporate Claude Enterprise account where training-off is the default and retention is configurable. |
| Notion AI | Product, Operations | M | Keep — DPA in place, contained to internal docs, no customer data routed through. |
| Perplexity Pro (personal) | Marketing, Comms, Sales | M | Govern — useful for research, but no DPA on personal accounts. Corporate-managed only. Ban personal subscriptions for work use. |
| Meeting AI tools — Granola, Otter, Fireflies | Sales, Customer Success | H | Govern — these recordings often contain customer data. Standardise on Zoom AI Companion's meeting summary (already in-stack, already DPA'd). Ban personal recording tools. |
| AI translation — DeepL Pro, Google Translate, ChatGPT/Claude translation | Marketing, Comms, Customer Success, Sales | M | Govern — translation feels harmless but routes sensitive employee comms, customer data, and internal docs through third-party engines. DeepL Pro has strong GDPR posture and EU data residency. Google Translate's enterprise tier is governed. Personal/free tiers of any translation tool are a kill — content can be used to improve the engine. Standardise on a corporate-managed translation engine with DPA, default to DeepL Pro for European languages. |
| Wistia AI dubbing & video translation | Marketing, Comms | H | Govern — Wistia's dubbing is powered by HeyGen under the hood. The good news: Workvivo's Wistia plan provides governed access to HeyGen capabilities without giving employees personal HeyGen subscriptions. The risk: dubbed content involves voice cloning, lip-syncing, and biometric data. Restrict to marketing/external content only. Never use for internal executive comms. Verify Wistia's Dubbing Feature Supplement DPA is signed. |
| Canva Magic Studio | Marketing, Brand, People, Comms | M | Govern — Canva Teams/Business/Enterprise content is not used for AI training (cannot be enabled). Personal/Pro accounts can be opted in. Canva Shield includes enterprise indemnification. Move all work usage to corporate Canva Teams account. Ban personal Canva accounts being used for work design. |
| Gamma (AI presentations) | Marketing, Sales, Product | H | Kill (personal/free tier) / Govern (Business plan only). Free and Plus users grant Gamma a perpetual, irrevocable, worldwide licence to use content for AI training. Gamma's viewer tracking also auto-harvests names and emails of any logged-in viewers — likely a GDPR breach if used for external decks. Ban personal/free Gamma accounts for work. If used at all, only on Business plan with SOC 2 documentation requested. |
| AI prototyping — Lovable, v0, Cursor | Product, Engineering | M | Keep — prototyping only, no production code, no customer data. Document the use cases. |
| Image generation — Midjourney, Adobe Firefly | Marketing, Brand | L | Keep — marketing creative only. No employee or customer images. Brand guidelines apply. Adobe Firefly has clearer commercial licensing than Midjourney; prefer Firefly for client-facing creative. |
| AI Chrome extensions — Grammarly, Copy.ai, Jasper | Marketing, Sales | H | Kill — unclear data paths, no DPAs, browser-level access to everything employees type. Ban via IT policy. Explain why. |
| AI presentation tools — Tome, Beautiful.ai | Marketing, Sales | M | Govern — same logic as Gamma. Corporate accounts only, content not used for training, verify the plan tier disables training before sanctioning. |
| Standalone voice cloning / avatar video — Descript, HeyGen (personal), Synthesia (personal) | Marketing, Comms | H | Kill — voice cloning and AI avatar generation as standalone tools is a category-level risk, especially given what we already know about voice impersonation attacks (golden dataset row 7). HeyGen is acceptable when accessed through Wistia's governed integration. Personal subscriptions to any of these tools are banned for work involving named individuals. |

**Total tools found:** 13 categories across the org. Almost certainly more we haven't surfaced yet — most shadow AI audits underestimate by 30-50%.

**Tools after triage:** 3 keep, 7 govern, 3 kill (with Gamma and HeyGen-class tools split between kill at personal tier / govern at corporate tier). Net: roughly 10 sanctioned categories under clear governance, down from a long tail of personal subscriptions.

**Estimated hidden spend:** $10K–$18K per month across personal subscriptions and unsanctioned team accounts. This is also the budget for the governed alternative once we consolidate — and it's the number that gets the CFO's attention faster than the risk argument does.

**The pattern in this audit:** The genuinely dangerous shadow AI usually isn't ChatGPT or Claude — those are the obvious ones, and most orgs are already managing them. The real risks hide inside tools that feel like creative or productivity tools: AI translation (routes sensitive content offshore through unknown engines), Wistia/HeyGen dubbing (voice cloning of real employees), Gamma (training on every presentation, auto-harvesting viewer data). These are the tools where the AI is incidental to the product pitch, so governance gets skipped. That's where the real exposure is.

There's also a more recent risk worth flagging: the September 2025 Anthropic policy shift turned every personal Claude.ai account into a potential training pipeline. A marketing team that's been using Claude responsibly for a year may have clicked through the forced-choice gate in October without realising their next twelve months of creative work would be eligible for model training. The shadow AI risk isn't always new tools. Sometimes it's a tool that changed underneath you.

**The Samsung lesson, applied to us:** Workvivo's customers are dealing with shadow AI right now. It's the tension at the heart of our launch narrative — "employees default to ChatGPT, Claude, DeepSeek." The fact that we're running this audit on our own stack first is what gives us the credibility to sell the answer. We can't tell customers their AI needs a home while our own AI use is scattered. The audit isn't compliance theatre. It's proof we live the story we're selling.

The unfair advantage in the pitch: Liquid Content runs on Workvivo AI, powered by Zoom AI Companion's federated architecture — with zero data retention at the model provider level and a published commitment not to train on customer content. Most of the tools on the list above can't say that. That contrast is the GTM story — Level 3 governance not as compliance burden, but as the reason buyers choose us.
