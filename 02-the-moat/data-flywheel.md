# Data Flywheel Map

## Flywheel Loops

### Loop 1: Usage → Correction loop: 
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


### Loop 2: Signal → Preference loop
**Score: 2/5**
*How does that data improve the model?*

Timing is learned. Voice is configured. Surface-to-surface signal exists in places — but it's partial and routes through humans, not the model.

Catch Me Up and send-time predictions adapt to each customer's audience patterns. Compose Profiles let admins set leadership voice samples — not learning, but a real preference layer.

What does work today: Ask HQ logs every employee search and surfaces content gaps to admins as insights — "people keep asking about X and we don't have good content backing it." Admins can then create the content via Compose or Liquid Content to fill the gap. So one surface-to-surface signal flow already exists. It just routes through a person making a decision, not directly into auto-suggested drafts.

What's missing: the automated version. When Seer detects a theme employees care about, Compose doesn't yet auto-suggest content in the right voice. When Ask HQ flags a content gap, Liquid Content doesn't yet auto-draft a candidate for admin review. These would compound without training the model on customer data — it's our own surfaces handing off to each other inside the customer's instance. We just haven't automated it yet.

Score 2/5: configuration works, customer-level timing works, human-routed handoff partially works (Ask HQ → admin insights → manual fill), auto-handoff doesn't.


### Loop 3: Model → Experience
**Score: 4/5**
*How does the better model improve UX?*
This is the strongest loop and the real moat.

Microsoft sees what employees do in Outlook. Unily sees what gets published. Workvivo sees how every employee feels, what they ask, what they engage with, and what they ignore — all on one platform. That's the asymmetry no point tool can match.

As each customer uses HQ more, their own content corpus grows, their engagement data deepens, their sentiment signal sharpens. Catch Me Up gets sharper because Seer gets sharper. Liquid Content gets sharper because engagement data does. Ask HQ gets sharper because the content is richer. Compose feeds Catch Me Up feeds Seer feeds Search feeds Insights.

Honest caveat: this loop is capped by Loops 1 and 2. If we don't wire the surfaces together properly, the experience improvement is real but plateaus early.

### Loop 4: Experience → Usage
**Score: 4/5**
*How does better UX drive more usage?*
HQ already has the daily habit other AI tools are still trying to earn. 9M employees reached. 90% adoption. 96% retention. Catch Me Up makes HQ the morning surface for every employee. Ask HQ becomes the default reflex for "where do I find...?" Liquid Content gets used more as predictions land — campaigns spread, frontline reach widens, more pillars get touched.

This is structural. HQ Core touches every employee daily by design — which means signal feeds back faster, from more people, in more contexts. If we wired Loops 1 and 2 up properly, the whole flywheel would accelerate.

Honest caveat: high usage without a coherent flywheel is just more data, not more learning. The habit is huge. The fact that it isn't yet feeding the platform intelligence faster is what keeps the total score below 15/20.

**Total Flywheel Score: 12/20**

**Weakest Loop:** Loop 1 — Usage → Correction

**Fix for weakest loop:**

Build on what's already working. Ask HQ already surfaces content gaps to admins — that's a working surface-to-surface signal flow, just one that routes through a person. The next move is to keep that flow honest and automate more of it where it makes sense.

When Seer flags a sentiment theme, Compose should auto-draft a candidate response in the customer's preferred voice. When Ask HQ identifies a content gap, Liquid Content should auto-draft a fill for admin review. When an engagement prediction misses, the platform should learn it for that customer's next campaign.

None of this needs us to train AI on customer data. It's Workvivo surfaces talking to each other inside one customer's boundary. Microsoft can't ship this from the Copilot stack without giving up their own governance position — which is the moat we should be building.

Same gap shows up in M4 and M5. One problem, three modules, one fix.

---

## Competitive Positioning

**Axis X:** AI surface depth — single AI feature (left) ←→ AI platform with cross-pillar signal (right)

**Axis Y:** Workforce coverage — desk-only (bottom) ←→ every employee, frontline + desk (top)

| Quadrant | Who lives there | Why |
|---|---|---|
| **Top-right: Platform AI for everyone** | **Workvivo HQ** | Cross-pillar signal + 80% workforce reach + daily-active habit |
| **Top-left: Single-pillar AI for everyone** | Staffbase, Simpplr, early Unily Glass | EX-built but smaller AI surface and shallower workforce signal |
| **Bottom-right: Platform AI for desk-only** | Microsoft Copilot Cowork, Salesforce + Agentforce, ServiceNow Now Assist | Big platform but desk-only; EX is bolted on, not built in |
| **Bottom-left: Single-pillar AI for individuals** | Canva AI, ChatGPT/Claude (personal), Gamma | Strong creation, no measurement, no platform signal, no enterprise reach |

| Competitor | Vector | Time-to-threat | % of value at risk |
|---|---|---|---|
| **Workvivo HQ** | Defending top-right quadrant. Cross-pillar signal + frontline reach + governance. | N/A | — |
| **Microsoft Copilot Cowork** | Already shipped in Frontier preview, built on Claude, agentic across M365, extensible via skills + plugins. Microsoft has 78 things named Copilot; EX gaps get filled by partners via the M365 App Store. | 6–12 months to GA; 12 months for EX skill pack | 50–60% — drafting, scheduling, basic search are replicable. Sentiment, frontline reach, governance posture are not. |
| **Unily Glass** | Purpose-built for internal comms. Going deeper on content intelligence, personalisation, and search. Pitch: we do what HQ does, but as our whole product. | Less than 6 months — already in market | 30% — comms-native and credible. Can't see what Seer sees, can't reach frontline at our depth. |
| **Canva** | Owns the creation workflow. 200M+ users, AI shipping fast. Adding an "internal comms publishing" layer is within reach. Bottom-up distribution via the comms manager's personal tool. | 18–24 months to enterprise scale | 25–30% — owns the creation moment, can't close the measurement loop. |

---

## 90-Day Encroachment Plan

*Three threat vectors. Name the attacker. Estimate the timeline. Quantify the damage. Plan the defence.*

### 1. Platform Encroachment — Microsoft 365 Copilot Cowork

**Attack vector:** Cowork is already shipping in Frontier preview. Built on Claude (same AI we use via Zoom). It runs multi-step tasks across M365 — email, calendar, docs, Teams. It's extensible via skills and plugins, so Microsoft doesn't need to build EX features themselves — partners will via the M365 App Store. Once Cowork goes GA and gets bundled into M365 E5, the pitch to IT is: "you already pay for this. Why pay extra for Workvivo?"

**Time-to-threat:** 6–12 months to GA. Another 6 months for a credible EX skill pack.

**% of value at risk:** 50–60%. Drafting, scheduling, and basic search are replicable. Sentiment, frontline reach, and our governance posture are not.

**Your defence:**

*Microsoft sees what people do. We see how they feel.* That sentiment signal is what makes HQ smarter and what Cowork has no equivalent of.

*Microsoft reaches the desk. We reach everyone.* Cowork needs an M365 license. HQ reaches the 80% of the workforce that doesn't have one.

*Microsoft wins procurement. We win product.* IT defaults to Microsoft because the contract is signed. We win when EX has its own buying centre — 3-4x higher adoption than Viva proves the product gap is real.

---

### 2. Vertical Competitor — Unily Glass

**Attack vector:** Unily Glass is purpose-built for internal comms. Going deep on content intelligence, personalisation, search. Their pitch: "we do what Workvivo's AI does, but as our whole product, not one feature."

**Time-to-threat:** Less than 6 months — already in market.

**% of value at risk:** 30%. Comms workflows are contested. Frontline reach, the Zoom partnership, Seer, and platform-wide signal are not.

**Your defence:** Unily is a comms tool trying to become a platform. Workvivo is a platform where comms is one of five surfaces. HQ's AI gets smarter from how people search, engage, surface knowledge gaps, shift sentiment — not just from how comms managers work. Unily's AI is trained on content creation. Workvivo's is trained on the whole employee experience. That's compounding they can't catch without rebuilding from scratch.

Sales line: "Unily is comms with AI. Workvivo is the AI-native HQ where comms is one surface among five, all feeding each other."

---

### 3. Adjacent Expansion — Canva

**Attack vector:** Canva owns the creation workflow — brand kits, templates, 200M+ users, AI shipping fast. Adding an "internal comms publishing" layer with AI copy is within reach. Distribution is bottom-up via the comms manager's personal tool.

**Time-to-threat:** 18–24 months to be enterprise-credible.

**% of value at risk:** 25–30%. They own the creation moment. They can't close the measurement loop.

**Your defence:** Canva can help you make beautiful content. It has no idea if anyone read it. Workvivo closes the loop — create, publish, measure, improve — in one system. The moment a comms manager asks "did that land?", Canva has no answer.

Tactically: embed with comms and HR buyers before Canva's bottom-up adoption reaches IT. Make Workvivo the system of record for comms performance before Canva becomes the system of record for comms creation. Then Canva stays the place creation happens; Workvivo is the platform that connects everything.
