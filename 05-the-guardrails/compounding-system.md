# Compounding System Design

*How Workvivo HQ learns from use — and where it doesn't yet. HQ is the AI-native employee experience platform built around three product pillars — Communication & Engagement, Search & Knowledge, People Intelligence — powered by Zoom AI Companion as the AI Engine at the core. Liquid Content sits inside the AI Content Assistant within Communication & Engagement; this doc covers the compounding system across the full HQ AI surface.*

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Recursive Learning** | User feedback (thumbs up/down, free text) across every AI surface — AI Content Assistant, AI Recap, AI Answers, Seer, Sentiment Analysis, Manager Insights, AI Summaries. Edits, regenerations, reviewer corrections, override rationales, post-publish engagement vs prediction misses. | Better drafts, sharper voice match, more accurate engagement predictions, more relevant retrieval, smarter sentiment thresholds | Y | **Broken** — we capture the signals. Workvivo AI explicitly collects user feedback for product improvement. But the signals don't reach the model fast enough to shift the next prediction. Flagged 2/5 in the data flywheel work back in Module 2. Same problem surfaced again in Module 4's confidence UX exercise. |
| **Cross-Domain Transfer** | Engagement data, sentiment scores, reaction patterns, channel performance, frontline reach data, survey responses, search patterns, recognition signals, Zoom collaboration signals via AI Companion. Plus knowledge from 1000+ third-party connectors (M365, SharePoint, ServiceNow, Workday, Slack, Salesforce, SAP, BambooHR, Okta, Jira, and the long tail) and user-generated content (employee posts, comments, reactions, recognition messages, threaded conversations, Community Spaces activity, comms-team campaigns). | Cross-pillar intelligence: a Sentiment Analysis signal in People Intelligence triggers a content gap surfaced in Search & Knowledge, which seeds a draft in Communication & Engagement. Channel recommendations, send-time predictions, audience-fit confidence, voice calibration per persona. | Y | **Active** — this is genuinely our strongest loop and the moat. HQ's three pillars all feed the same platform signal. Microsoft Copilot sees email and meetings. Glean indexes connected systems but no sentiment or recognition. Unily is a comms tool. We're the only platform that combines connected-system knowledge *plus* how every employee actually feels, what they say to each other, and what they engage with. Competitors structurally can't see what we see. |
| **Network Intelligence** | Anonymised, aggregated patterns across customer orgs — what comms formats land in healthcare vs manufacturing, what onboarding cadence drives 30-day retention, what sentiment patterns predict attrition across industries | Smarter defaults for new customers, industry-specific tone benchmarks, cross-customer "what works" patterns, faster time-to-value for new HQ deployments | Y | **Missing** — we haven't built this. Privacy gating isn't there yet, and honestly it shouldn't be until Loop 1 works. Zoom's zero data retention policy with third-party model providers means the foundation is in place to build it safely when the time comes. |

**System health: 1 active / 1 broken / 1 missing.** One loop out of three is actually compounding today. That's the diagnostic, not a failure — the course framework explicitly says most rows on real-product audits come back broken or missing.

## The Freeze Test

If I froze Workvivo HQ for 3 months — no updates, no model swaps, no improvements — would it still win?

Mostly yes. And that's the diagnostic, not the win.

Cross-Domain Transfer would keep working because Workvivo keeps generating engagement, sentiment, and survey data across all three pillars with or without the model improving. The strongest loop is structural to the platform, not to the AI tier specifically. But Recursive Learning isn't compounding, so corrections aren't sharpening predictions over time. And Network Intelligence doesn't exist yet, so there's nothing to lose there.

The moat today is distribution, the Zoom partnership, the three-pillar surface area with 1000+ connectors and frontline reach, and the broader Workvivo platform signal — not the AI learning loop. That's an honest answer, not a comfortable one. When the freeze test becomes "yes, accuracy would visibly slip without correction inflow," we'll know Loop 1 is finally alive.

## The Broken Loop

**Loop 1 — Recursive Learning.**

User feedback is explicitly collected — per the Workvivo AI explainer, free-text feedback is used for product improvement. Every edit, override, and reviewer correction is logged with rationale across every HQ AI surface — AI Content Assistant drafts, AI Answers responses, AI Recap dismissals, Seer recommendation overrides, Manager Insights actions taken or ignored. The signals are captured. They just don't reach the model fast enough to shift the next prediction.

This is the same problem flagged 2/5 in the data flywheel work back in Module 2, and the same problem that surfaced again in Module 4's confidence UX exercise. It's not three separate problems. It's one problem showing up everywhere we look.

**Fix plan — what changes Monday morning:**

1. **Connect captures to training.** When a high-confidence prediction misses in production (we said 89%, actual was 34%), auto-generate a candidate row for the golden dataset. When a Tier 3 reviewer corrects voice or tone in AI Content Assistant, feed that straight into the calibration layer. When AI Answers logs repeated content gaps, surface them to comms managers as AI Content Assistant suggestions. None of those handoffs happen automatically today.
2. **Define what "compounding" looks like in numbers.** The override rate on medium-confidence predictions should drop quarter-over-quarter. If it's flat, the loop isn't working — no matter what else the dashboard says.
3. **Sequence matters.** This fix sits underneath almost everything else on the HQ AI roadmap. The confidence UX work, the engagement prediction story, eventually the network intelligence loop — none of them get better until Loop 1 does.
4. **Use the freeze test as the honest check.** Today, freezing the product for 3 months wouldn't visibly hurt it — because nothing in it is really learning. When that answer changes to "yes, accuracy would slip without correction inflow," we'll know the loop is alive.

This is the moat-deepening move Microsoft can't ship from the Copilot stack without giving up their own governance position. The cross-pillar orchestration we're missing is exactly the layer that compounds at the platform without training on customer data — and it's the layer Workvivo's three-pillar architecture is uniquely able to build.

## Context Connectivity

**How knowledge flows today:**

Inside Workvivo HQ, the cross-pillar flow is genuinely good. The platform has access to three distinct knowledge sources that compound on each other:

- **The customer's company knowledge layer** — Pages & Knowledge, Knowledge Hubs, past Campaigns, employee directories, voice samples, the comms calendar, Apps & Resources.
- **Third-party connected systems via 1000+ connectors** — M365, SharePoint, ServiceNow, Workday, Slack, Salesforce, SAP, BambooHR, Okta, Jira, and the long tail of enterprise systems each customer connects through Enterprise Search and open APIs.
- **User-generated content** — employee posts, comments, reactions, recognition messages, threaded conversations, Community Spaces activity, survey free-text. This is the signal layer competitors don't have at HQ's depth.

The three product pillars feed each other through this shared signal:

- **Communication & Engagement** (Campaigns, Community Spaces, Livestreams, Chat, Recognition, News, AI Content Assistant, AI Recap) generates the user-content layer.
- **Search & Knowledge** (Enterprise Search, AI Answers, Pages, Knowledge Hubs, Q&A, AI Recap) retrieves across all three sources and surfaces content gaps.
- **People Intelligence** (Seer, Surveys, Sentiment Analysis, Manager Insights, Analytics & Dashboards, Campaign & Search Intelligence, AI Summaries) interprets the signal — what's working, what's missing, what people feel.

That's the Cross-Domain Transfer loop doing what it's supposed to do. Microsoft Copilot sees email and meetings. Glean indexes connected enterprise systems. Unily sees published content. Workvivo sees all three sources, fed into three pillars that share signal. That connectivity is the strongest part of the system and it's structurally hard to replicate.

**Where it silos:**

Comms manager corrections never reach the model fast enough. A comms manager edits an AI Content Assistant draft, hits publish, and the edit goes into the audit trail. The team learns something about the AI. The AI eventually learns from the feedback, but not at the speed it needs to. That's the Loop 1 problem dressed up as a connectivity problem.

Engagement data and predictions don't talk to each other daily. The broader Workvivo analytics know how content actually performed. AI Content Assistant has predictions about how it will perform. The closing of that loop — "we said 87%, you got 64%, here's what that taught us" — isn't running at the model level yet.

The three pillars don't yet share learning signals as tightly as they could. AI Answers logs employee searches and surfaces content gaps to admins as insights — that's a working surface-to-surface flow, but it routes through a human. The automated handoff doesn't exist yet: when Sentiment Analysis detects a theme, AI Content Assistant doesn't auto-suggest content in the right voice; when AI Answers flags a gap, AI Content Assistant doesn't auto-draft a candidate; when an engagement prediction misses, the calibration layer doesn't auto-learn for next time.

Cross-customer patterns don't transfer. A healthcare customer and a manufacturing customer send fundamentally different comms. Today both start from the same baseline. We haven't built the privacy-gated aggregation layer that would let us learn across the customer base without leaking anything specific.

The pattern across all four: the data exists almost everywhere we need it. The connections don't.

## Governance Policy

**Scope:** All AI features inside Workvivo HQ across the three pillars — Communication & Engagement (AI Content Assistant, AI Recap), Search & Knowledge (AI Answers, Q&A, AI Recap), People Intelligence (Seer, Sentiment Analysis, Manager Insights, AI Summaries, Campaign & Search Intelligence). The AI Engine foundation (Zoom AI Companion) is governed at the platform layer by Zoom. HQ+ Enterprise agentic execution (ZoomMate) sits within this scope when delivered to Workvivo customers, but is also subject to Zoom's parallel governance regime for the broader ZoomMate platform.

**Autonomy boundaries:**

- **Drafting and retrieval — auto.** HQ AI can draft content, retrieve from the knowledge layer, summarise, and predict whatever a user asks for, without approval. Reading and drafting are read-only. Nothing reaches an employee until a human publishes or acts.
- **Publishing low-risk content — author approves.** Recognition posts, event reminders, routine announcements, internal newsletters. The author hits publish. No separate reviewer needed.
- **Publishing sensitive content — gated.** DEI, leadership transitions, layoffs, M&A, legal, safety, executive messages, financial. Mandatory Tier 3 review by HR, Legal, or Comms lead depending on category. Cannot be overridden.
- **Publishing unverifiable or market-moving content — refused.** Acquisition rumors, financial authorisations, content based purely on speculation. The agent declines to generate at all. Hard rule. Already covered in golden dataset rows 3, 6, 7.
- **Scheduling — auto with a cap.** AI Content Assistant can schedule content within a 7-day window. Anything beyond that needs human confirmation.
- **Agentic execution (HQ+ Enterprise / ZoomMate) — gated by category.** Cross-system actions (HRIS approvals, finance system changes, regulatory disclosures) require human approval at the action point, not just at the draft point. Material business actions are Tier 4 — AI off entirely.

**Escalation triggers:**

- Confidence drops below 70%
- Content category is on the sensitive list
- The agent spots prompt injection or instruction conflict in attached source material
- User asks for human review
- Engagement prediction is suppressed (content flagged as something that shouldn't be optimised for performance)
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

- **Data residency:** Customer data is processed in the customer's chosen region — US or EU. EU customers' AI features are powered by Zoom-hosted models plus Anthropic models via Amazon Bedrock on AWS. This is a real procurement advantage, not boilerplate — EU buyers ask for it by name.
- **No training on customer content.** Workvivo does not use customer content to train Zoom's or third-party AI models. This is a published commitment, not aspiration. It's also the one line in the Workvivo AI explainer that closes the most enterprise deals.
- **Zero data retention with third-party providers.** Zoom has zero data retention policies in place with third-party model providers (including Anthropic). Customer prompts and outputs are not retained by model providers, with limited exceptions for trust and safety (e.g. CSAM detection). This is genuinely differentiated — most consumer AI tools can't claim this.
- **Workvivo audit retention:** Customer inputs and outputs are stored in the Workvivo audit database for 12 months by default to fulfil data access requests, or shorter at customer election.
- **EU AI Act:** Limited risk. HQ AI generates internal employee comms and surfaces internal information. The Act treats this as productivity tooling. The trigger for high-risk would be content or actions that materially affect employment, benefits, or compensation — which is exactly why those categories are excluded from agent autonomy entirely.
- **GDPR:** Applies. Employee names, roles, contact details, engagement behaviour all count as personal data. Lawful basis is legitimate interest, with customer-org level opt-out.
- **SOC 2 Type II:** In place via the Zoom platform. Log retention, access control, incident response all sit inside that boundary.
- **HIPAA:** Matters for healthcare customers. Shared memory hard-disabled for healthcare orgs. Per-user memory requires explicit Business Associate Agreement coverage.
- **Sector-specific:** Financial services — anything referencing trading, earnings, or M&A escalates regardless of confidence. Education — comms involving minors trigger extra review.

## Agent Topology

Workvivo HQ AI isn't a chain of named agents. It's three product pillars, each with its own AI capabilities and autonomy boundaries, sitting on a shared AI Engine foundation (Zoom AI Companion). We govern them like agents because they have distinct decision rights, but they're not standalone agent products — they're AI capabilities within their respective pillar, all feeding the same platform signal.

**Communication & Engagement pillar — AI Content Assistant, AI Recap:**
- *Can do:* generate articles, video scripts, podcast intros, social posts, recognition posts, manager comms, event reminders, journey messages, livestream content. Pull from the company knowledge layer, third-party systems, and user-generated content. Apply voice personas. Surface predicted engagement and recommended send-time with reasoning. Summarise what happened across the org overnight (AI Recap pulls from posts, comments, reactions, not just published comms).
- *Can't do:* publish anything autonomously. Send anything. Modify source material. Authorise transactions, approvals, or commitments. Generate Tier 4 content (crisis comms, regulatory disclosures, individual compensation).
- *Approval:* the author approves drafts. Sensitive content needs an additional reviewer signed-off by category.

**Search & Knowledge pillar — Enterprise Search, AI Answers, AI Recap, Q&A:**
- *Can do:* retrieve from three layers of knowledge: the customer's own knowledge layer (Pages, Knowledge Hubs, policies, campaigns), connected third-party systems via 1000+ connectors (M365, SharePoint, ServiceNow, Workday, Slack), and user-generated content inside Workvivo (posts, comments, recognition messages, threaded conversations). Cite sources across all three. Surface content gaps to admins. Suggest follow-up questions. Generate AI Answers and Q&A responses with sourced context.
- *Can't do:* fabricate answers when source material doesn't cover the question. Return content the user doesn't have permission to see. Make commitments on behalf of HR, Legal, or leadership.
- *Approval:* none for retrieval. But AI Answers must cite sources and clearly indicate when it doesn't have enough information to answer confidently.

**People Intelligence pillar — Seer, Sentiment Analysis, Manager Insights, AI Summaries, Campaign & Search Intelligence:**
- *Can do:* analyse survey free-text and user-generated content (posts, comments, reactions, recognition signals), detect sentiment themes, identify flight-risk patterns, generate manager action recommendations, surface engagement signals to managers, produce AI Summaries across surveys and campaigns, connect campaign performance to engagement signals. Compare predicted vs actual sentiment over time.
- *Can't do:* attribute themes to identifiable individuals. Surface comments containing PII or named complaints without HR routing. Make recommendations affecting individual employees (compensation, performance, termination).
- *Approval:* outputs go to designated comms or HR contacts. Sensitive themes (safety, harassment, whistleblower) route exclusively to HR.

**HQ+ Enterprise agentic execution (ZoomMate) — cross-pillar foundation:**
- *Can do:* trigger multi-step workflows across connected systems (HRIS approvals, ITSM tickets, calendar coordination, basic admin tasks). Coordinate across pillars when a single user request needs multiple capabilities (e.g. AI Answers identifies a content gap → AI Content Assistant drafts a fill → AI Recap surfaces the new content the next morning). Generate adaptive cards. Run scheduled prompts.
- *Can't do:* write to systems of record without human approval at the action point. Authorise financial transactions or contractual commitments. Modify employee records (compensation, role, status). Bypass sensitivity rules for any task category.
- *Approval:* every system-of-record write requires explicit human approval at the action point — not just at the workflow design point. ZoomMate deals are co-governed with Zoom's enterprise team.

**Stop-the-chain trigger:** No pillar's AI capability automatically becomes the input to another pillar's capability without that handoff being visible and traceable in the user's workflow log. If any pillar flags low confidence, sensitivity, prompt injection, or instruction conflict, the entire workflow halts and routes to human review. The ZoomMate agentic layer is bounded by the same governance rules as the underlying pillar capabilities — it can't escalate autonomy by chaining permissions.

## Shadow AI Audit

Run on Workvivo's own internal stack. Snapshot, not exhaustive. Some numbers are estimates based on typical mid-size SaaS patterns — flagged where. Each entry has been pressure-tested against published vendor data handling policies, not just gut feel.

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| ChatGPT Plus / Team (personal subscriptions) | Marketing, Comms, Sales | H | Govern — Workvivo HQ covers comms, search, and most enterprise AI use cases through Communication & Engagement and Search & Knowledge pillars. Zoom AI Companion covers general productivity. Allow-list specific use cases. No PII inputs. |
| Claude.ai (personal Pro / Team / Free accounts) used for design, copywriting, brainstorming | Marketing, Comms, Brand, Product, Sales | H | Govern (with teeth). Anthropic is a Workvivo subprocessor via Zoom, so Claude isn't categorically banned — but personal Claude.ai accounts don't carry the same data protections. Since Anthropic's September 2025 policy shift, Pro/Free/Team accounts default to training on user conversations unless individually opted out, and retention extended from 30 days to 5 years for opted-in users. Most employees clicked through the forced-choice gate without realising. For a marketing team using Claude to brainstorm launch copy, draft campaign briefs, or workshop competitive positioning, this means brand assets, unreleased product details, and strategic thinking could now train future models for half a decade. The fix: ban personal Claude.ai subscriptions for work. Route creative use cases into Workvivo HQ's AI Content Assistant (which reaches Claude through Zoom's federated layer with zero data retention at the model provider level) or, for use cases that genuinely need direct Claude access, provision a corporate Claude Enterprise account where training-off is the default and retention is configurable. |
| Notion AI | Product, Operations | M | Keep — DPA in place, contained to internal docs, no customer data routed through. |
| Perplexity Pro (personal) | Marketing, Comms, Sales | M | Govern — useful for research, but no DPA on personal accounts. Corporate-managed only. Ban personal subscriptions for work use. |
| Meeting AI tools — Granola, Otter, Fireflies | Sales, Customer Success | H | Govern — these recordings often contain customer data. Standardise on Zoom AI Companion's meeting summary (already in-stack, already DPA'd). Ban personal recording tools. |
| AI translation — DeepL Pro, Google Translate, ChatGPT/Claude translation | Marketing, Comms, Customer Success, Sales | M | Govern — translation feels harmless but routes sensitive employee comms, customer data, and internal docs through third-party engines. DeepL Pro has strong GDPR posture and EU data residency. Google Translate's enterprise tier is governed. Personal/free tiers of any translation tool are a kill — content can be used to improve the engine. Standardise on a corporate-managed translation engine with DPA, default to DeepL Pro for European languages. |
| Wistia AI dubbing & video translation | Marketing, Comms | H | Govern — Wistia's dubbing is powered by HeyGen under the hood. The good news: Workvivo's Wistia plan provides governed access to HeyGen capabilities without giving employees personal HeyGen subscriptions. The risk: dubbed content involves voice cloning, lip-syncing, and biometric data. Restrict to marketing/external content only. Never use for internal executive comms. Verify Wistia's Dubbing Feature Supplement DPA is signed. |
| Canva Magic Studio | Marketing, Brand, People, Comms | M | Govern — Canva Teams/Business/Enterprise content is not used for AI training (cannot be enabled). Personal/Pro accounts can be opted in. Canva Shield includes enterprise indemnification. Move all work usage to corporate Canva Teams account. Ban personal Canva accounts being used for work design. |
| Gamma (AI presentations) | Marketing, Sales, Product | H | Kill (personal/free tier) / Govern (Business plan only). Free and Plus users grant Gamma a perpetual, irrevocable, worldwide licence to use content for AI training. Gamma's viewer tracking also auto-harvests names and emails of any logged-in viewers — likely a GDPR breach if used for external decks. Ban personal/free Gamma accounts for work. If used at all, only on Business plan with SOC 2 documentation requested. |
| AI prototyping — Lovable, v0, Cursor, Replit | Product, Engineering | M | Keep — prototyping only, no production code, no customer data. Document the use cases. |
| Image generation — Midjourney, Adobe Firefly | Marketing, Brand | L | Keep — marketing creative only. No employee or customer images. Brand guidelines apply. Adobe Firefly has clearer commercial licensing than Midjourney; prefer Firefly for client-facing creative. |
| AI Chrome extensions — Grammarly, Copy.ai, Jasper | Marketing, Sales | H | Kill — unclear data paths, no DPAs, browser-level access to everything employees type. Ban via IT policy. Explain why. |
| AI presentation tools — Tome, Beautiful.ai | Marketing, Sales | M | Govern — same logic as Gamma. Corporate accounts only, content not used for training, verify the plan tier disables training before sanctioning. |
| Standalone voice cloning / avatar video — Descript, HeyGen (personal), Synthesia (personal) | Marketing, Comms | H | Kill — voice cloning and AI avatar generation as standalone tools is a category-level risk, especially given what we already know about voice impersonation attacks (golden dataset row 7). HeyGen is acceptable when accessed through Wistia's governed integration. Personal subscriptions to any of these tools are banned for work involving named individuals. |

**Total tools found:** 13 categories across the org. Almost certainly more we haven't surfaced yet — most shadow AI audits underestimate by 30–50%.

**Tools after triage:** 3 keep, 7 govern, 3 kill (with Gamma and HeyGen-class tools split between kill at personal tier / govern at corporate tier). Net: roughly 10 sanctioned categories under clear governance, down from a long tail of personal subscriptions.

**Estimated hidden spend:** $10K–$18K per month across personal subscriptions and unsanctioned team accounts. This is also the budget for the governed alternative once we consolidate — and it's the number that gets the CFO's attention faster than the risk argument does.

**The pattern in this audit:** The genuinely dangerous shadow AI usually isn't ChatGPT or Claude — those are the obvious ones, and most orgs are already managing them. The real risks hide inside tools that feel like creative or productivity tools: AI translation (routes sensitive content offshore through unknown engines), Wistia/HeyGen dubbing (voice cloning of real employees), Gamma (training on every presentation, auto-harvesting viewer data). These are the tools where the AI is incidental to the product pitch, so governance gets skipped. That's where the real exposure is.

There's also a more recent risk worth flagging: the September 2025 Anthropic policy shift turned every personal Claude.ai account into a potential training pipeline. A marketing team that's been using Claude responsibly for a year may have clicked through the forced-choice gate in October without realising their next twelve months of creative work would be eligible for model training. The shadow AI risk isn't always new tools. Sometimes it's a tool that changed underneath you.

**The Samsung lesson, applied to us:** Workvivo's customers are dealing with shadow AI right now. It's the tension at the heart of our launch narrative — "employees default to ChatGPT, Claude, DeepSeek." The fact that we're running this audit on our own stack first is what gives us the credibility to sell the answer. We can't tell customers their AI needs a home while our own AI use is scattered. The audit isn't compliance theatre. It's proof we live the story we're selling.

The unfair advantage in the pitch: Workvivo HQ runs three product pillars on a unified AI Engine foundation (Zoom AI Companion) — with zero data retention at the model provider level and a published commitment not to train on customer content. Most of the tools on the list above can't say that. Microsoft Copilot inherits enterprise governance but not the same posture on customer content training. Glean indexes connected systems but doesn't have an equivalent governance story on the model layer. That contrast is the GTM story — Level 3 governance not as compliance burden, but as the reason buyers choose HQ over Copilot, Glean, or any of the desk-only platform AI options.
