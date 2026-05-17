# Data Flywheel Map

## Flywheel Loops

### Loop 1: Usage → Correction

**Score: 2/5**

*How does usage generate proprietary data?*

Every AI surface in HQ collects feedback. Liquid Content sees thumbs up/down and edits. Catch Me Up sees what gets dismissed. Ask HQ sees thumbs-down on bad answers. Seer sees which recommendations managers act on. All of it goes into the audit trail.

But we don't use any of it to train the AI. That's a deliberate choice — Workvivo and Zoom have a published commitment that customer content is not used to train Zoom's or third-party AI models. It's the same commitment that gives us the trust story we sell on in enterprise deals.

So the flywheel has to compound somewhere other than the model. And it does — just not as strongly as it should yet.

What works today:
- **Your content makes your search smarter.** Anything created in Workvivo AI goes into your own knowledge base. Ask HQ retrieves from it. If a comms manager publishes a wrong policy, the bad search result surfaces the gap. A human fixes the source. The next answer is right.
- **Leadership voice is configurable.** AI Compose Profiles let admins set how each leader writes. Not automatic, but a real preference layer.
- **Timing gets smarter at the customer level.** Catch Me Up and send-time predictions adapt to how your audience actually behaves.
- **Your feedback ships as features.** Thumbs-down on an answer doesn't fine-tune the model — it goes to our product team and ships as an improvement for everyone.

Score 2/5 because the framework expects a fast learning loop. We have something different — slower, but defensible — and we haven't yet wired it as a deliberate flywheel.

---

### Loop 2: Signal → Preference

**Score: 2/5**

*How does that data improve the model?*

Timing is learned. Voice is configured. Surface-to-surface signal exists in places — but it's partial and routes through humans, not the model.

Catch Me Up and send-time predictions adapt to each customer's audience patterns. Compose Profiles let admins set leadership voice samples — not learning, but a real preference layer.

What does work today: Ask HQ logs every employee search and surfaces content gaps to admins as insights — "people keep asking about X and we don't have good content backing it." Admins can then create the content via Compose or Liquid Content to fill the gap. So one surface-to-surface signal flow already exists. It just routes through a person making a decision, not directly into auto-suggested drafts.

What's missing: the automated version. When Seer detects a theme employees care about, Compose doesn't yet auto-suggest content in the right voice. When Ask HQ flags a content gap, Liquid Content doesn't yet auto-draft a candidate for admin review. These would compound without training the model on customer data — it's our own surfaces handing off to each other inside the customer's instance. We just haven't automated it yet.

Score 2/5: configuration works, customer-level timing works, human-routed handoff partially works (Ask HQ → admin insights → manual fill), auto-handoff doesn't.

---

### Loop 3: Model → Experience

**Score: 4/5**

*How does the better model improve UX?*

This is the strongest loop and the real moat.

Microsoft sees what employees do in Outlook. Unily sees what gets published. Workvivo sees how every employee feels, what they ask, what they engage with, and what they ignore — all on one platform. That's the asymmetry no point tool can match.

As each customer uses HQ more, their own content corpus grows, their engagement data deepens, their sentiment signal sharpens. Catch Me Up gets sharper because Seer gets sharper. Liquid Content gets sharper because engagement data does. Ask HQ gets sharper because the content is richer. Compose feeds Catch Me Up feeds Seer feeds Search feeds Insights.

Honest caveat: this loop is capped by Loops 1 and 2. If we don't wire the surfaces together properly, the experience improvement is real but plateaus early.

---

### Loop 4: Experience → Usage

**Score: 4/5**

*How does better UX drive more usage?*

HQ already has the daily habit other AI tools are still trying to earn. 9M employees reached. 90% adoption. 96% retention. Catch Me Up makes HQ the morning surface for every employee. Ask HQ becomes the default reflex for "where do I find...?" Liquid Content gets used more as predictions land — campaigns spread, frontline reach widens, more pillars get touched.

This is structural. HQ Core touches every employee daily by design — which means signal feeds back faster, from more people, in more contexts. If we wired Loops 1 and 2 up properly, the whole flywheel would accelerate.

Honest caveat: high usage without a coherent flywheel is just more data, not more learning. The habit is huge. The fact that it isn't yet feeding the platform intelligence faster is what keeps the total score below 15/20.

---

**Total Flywheel Score: 12/20**

**Weakest Loop:** Loop 1 — Usage → Correction

**Fix for weakest loop:**

Build on what's already working. Ask HQ already surfaces content gaps to admins — that's a working surface-to-surface signal flow, just one that routes through a person. The next move is to keep that flow honest and automate more of it where it makes sense.

When Seer flags a sentiment theme, Compose should auto-draft a candidate response in the customer's preferred voice. When Ask HQ identifies a content gap, Liquid Content should auto-draft a fill for admin review. When an engagement prediction misses, the platform should learn it for that customer's next campaign.

None of this needs us to train AI on customer data. It's Workvivo surfaces talking to each other inside one customer's boundary. Microsoft can't ship this from the Copilot stack without giving up their own governance position — which is the moat we should be building.

Same gap shows up in M4 and M5. One problem, three modules, one fix.

---
## Competitive Positioning

**X-axis: What the AI sees** — limited EX measurement (left) → full EX signal: sentiment + engagement + recognition (right)
**Y-axis: Workforce coverage** — desk-only (bottom) → everyone, frontline + desk (top)

|                                       | **← Limited EX measurement**            | **Full EX signal →**                              |
| ------------------------------------- | --------------------------------------- | ------------------------------------------------- |
| **↑ Everyone**<br>**(frontline + desk)** | Unily                                   | **★ Workvivo HQ**                                 |
| **↓ Desk-only**                       | Glean                                   | Microsoft (Viva + Cowork)                         |

**Reading the chart:**

- **Top-right — Workvivo HQ.** The only platform with full EX signal *and* every-employee reach. Seer's always-on sentiment, engagement, recognition, comments, frontline mobile — all in one place, used by 90% of contracted users daily.
- **Top-left — Unily.** EX-built and reaches the workforce, but lighter on EX measurement. Engagement data and some sentiment in Glass/Indy/Liquid Content, but no equivalent of Seer's always-on listening engine.
- **Bottom-right — Microsoft (Viva + Cowork).** Microsoft does have EX measurement capability — Viva Glint for surveys, Viva Insights for engagement analytics, Viva Pulse for quick check-ins. The structural problem is reach: it all lives in the M365 stack, which means it never reaches the 80% of the workforce without an M365 Copilot license.
- **Bottom-left — Glean.** Enterprise AI search and assistant. Indexes work product (documents, messages, tickets, meetings) — no sentiment, no engagement layer. Sold to IT for desk workers across the connected enterprise stack.

**Why HQ is alone in the top-right:**

EX signal at depth and frontline reach are *correlated investments*. You don't end up with both unless you built deliberately for both. Microsoft has the data but didn't invest in reaching everyone. Unily and Staffbase reach everyone but didn't invest in sentiment at Seer's depth. Glean has neither.

**Sales line:** *"Microsoft sees what your people do. We see how they feel — and we reach all of them."*

## 90-Day Encroachment Plan

*Three threat vectors. Name the attacker. Estimate the timeline. Quantify the damage. Plan the defence.*

### 1. Platform Encroachment — Microsoft (Viva + Cowork)

**Attack vector:** Microsoft already has all the pieces. Cowork just shipped in Frontier preview — agentic AI across M365, built on Claude, extensible via skills and plugins. Viva already covers sentiment (Glint), engagement (Insights), and comms (Amplify, Engage). The risk isn't them building something new — it's them integrating what they already own and bundling it into M365 E5. Once Cowork goes GA, the pitch to enterprise IT is: "you already pay for this. Why pay extra for Workvivo?"

**Time-to-threat:** 6–12 months to Cowork GA. Another 6–12 months for a coherent Viva + Cowork integration with EX skills built by partners via the M365 App Store.

**% of value at risk:** 50–60%. Drafting, scheduling, basic search, and surface-level sentiment are replicable. Cross-pillar signal density, frontline reach, and our governance posture are not.

**Your defence:**

*Microsoft sees what people do. We see how they feel — and reach the people doing the work.* Microsoft has sentiment in Viva Glint and engagement in Viva Insights, but they live separately from Cowork. The AI coworker runs on the Microsoft Graph (email, calendar, docs), not on EX signal. HQ runs on both, in one place, woven together.

*Microsoft reaches the desk. We reach everyone.* Cowork needs an M365 Copilot license. HQ reaches the 80% of the workforce that doesn't have one — and Viva's sentiment data, even where it exists, doesn't reach them either.

*Microsoft wins procurement. We win product.* IT defaults to Microsoft because the contract is signed. We win when EX has its own buying centre — 3-4x higher adoption than Viva proves the product gap is real. Push EX into its own procurement track wherever possible.

---

### 2. Vertical Competitor — Unily

**Attack vector:** Unily is the EX-native vertical competitor. Their AI suite — Glass, Indy, and Liquid Content — is purpose-built for enterprise internal comms and intranet experience. They're going deep on content intelligence, personalisation, knowledge search, and multi-format generation (their own feature also called "Liquid Content"). Their pitch: "we do what Workvivo's AI does for comms, but as our whole product, not one feature among many."

**Time-to-threat:** Less than 6 months. Glass is already in market; Indy and Liquid Content are maturing fast.

**% of value at risk:** 30%. Comms workflows are contested. Frontline reach, the Zoom partnership, Seer-grade sentiment, and platform-wide signal are not.

**Your defence:** Unily is a comms tool trying to become a platform. Workvivo is a platform where comms is one of five surfaces. HQ's AI gets smarter from how people search, engage, surface knowledge gaps, shift sentiment — not just from how comms managers work. Unily's AI is trained on content creation workflows. Workvivo's is trained on the whole employee experience. That's compounding they can't catch without rebuilding from scratch.

Sales line: *"Unily is comms with AI. Workvivo is the AI-native HQ where comms is one surface among five, all feeding each other."*

---

### 3. Adjacent Expansion — Glean

**Attack vector:** Glean is enterprise AI search that has already moved into the assistant and agent layers. They're sold to IT, deployed across the same connected systems HQ+ would integrate with (M365, Slack, Salesforce, Workday), and they've publicly positioned around Glean Apps and Glean Agents — building toward an agentic platform for enterprise. Their pitch to a buyer who already has them: "we already do enterprise AI assistant and search — why pay extra for Workvivo's version?"

**Time-to-threat:** Less than 6 months for the Ask HQ overlap (they're already in market). 12–18 months for a credible EX extension that touches comms, recognition, or journeys.

**% of value at risk:** 35–40%. They directly compete with Ask HQ and Enterprise AI Search today, and could extend into adjacent EX surfaces over the next year. Engagement signal, frontline reach, Seer-grade sentiment, and the comms creation surface stay safer.

**Your defence:**

*Glean sees what people do. We see how they feel.* Glean indexes documents, messages, tickets, and meetings — the work product. Workvivo sees employee sentiment, recognition patterns, engagement signal, and what content actually lands. That's the difference between a productivity assistant and an experience platform.

*Glean is for the desk. HQ is for everyone.* Glean lives where the connected enterprise systems live — and most of those systems don't reach the 80% of the workforce that doesn't sit at a desk. HQ reaches them on day one.

*Glean answers questions. HQ closes loops.* When Ask HQ surfaces a content gap, the platform also has the comms surface to fill it (Liquid Content), the engagement layer to measure it (Insights), and the sentiment signal to know if it landed (Seer). Glean is one surface. HQ is the experience layer where all of them meet.

Tactically: position HQ as the EX platform that *includes* enterprise search, rather than letting Glean position HQ as a comms tool that includes a worse Glean. Anchor the conversation on the four pillars (Navigator, Communicator, Coach, Operator), not on any single feature comparison.
