# Data Flywheel Map

## Flywheel Loops

### Loop 1: Usage → Correction loop: 
**Score: 2/5**
*How does usage generate proprietary data?*
Every time a comms manager uses the Campaign Builder, it generates signal — what was prompted, what the AI produced, what got edited, what got published. The Edit and Regenerate buttons show the product knows a correction happened. The problem is it doesn't learn from it. Those edit deltas aren't being captured and fed back to improve future drafts.
What does work: content created by the agent gets stored in the platform as a knowledge doc, which AI Search then pulls from. If a comms manager publishes a policy update via the agent, that becomes the source a frontline worker gets when they search for it later. If the content was wrong, the bad search result surfaces the gap — someone fixes it, and the better answer re-enters the system. That's a real correction loop, even if it runs through humans rather than the model itself.

### Loop 2: Signal → Preference loop
**Score: 2/5**
*How does that data improve the model?*
The Predictive Analytics feature — recommending Friday 9AM for posts, Tuesday 2PM for articles, flagging 97% predicted success, is genuinely useful and more than most competitors offer. The product is learning when to send.
But the agent doesn't yet know your CEO writes in short punchy sentences, that your frontline workers tune out corporate tone, or that this comms manager always rewrites formal language into plain English. Timing is learned. Voice, tone, and audience register are not.

### Loop 3: Model → Experience
**Score: 4/5**
*How does the better model improve UX?*
As the knowledge corpus grows and timing predictions sharpen, the product starts to feel less like a writing tool and more like a comms strategist. Campaigns land better. Channel recommendations prove right. The gap between Workvivo and a generic AI tool widens with every campaign run through the platform.
Honest caveat: Loop 3 is ceiling-capped by Loops 1 and 2. If corrections aren't captured and preferences aren't learned, the experience improvement is real — but it plateaus early.

### Loop 4: Experience → Usage
**Score: __/5**
*How does better UX drive more usage?*
When timing predictions are right and campaigns perform better, comms teams trust it more and use it for more. It stops being a shortcut and becomes the default. Over time, usage spreads beyond central comms to HR, leadership, and department heads — which brings in more varied signal and strengthens the loop.
Honest caveat: comms teams are small. That expansion doesn't happen on its own — it needs deliberate activation, not just a better product

**Total Flywheel Score: __/20**
**Weakest Loop:Loop 1 — Correction Loop**
**Fix for weakest loop: When someone edits or regenerates a draft, capture what changed. Not just that it happened — what specifically was wrong. Feed that back into how the agent generates content next time. Right now every edit is treated as a user action. It should be treated as a signal the model missed.**

---

## Competitive Positioning


**Axis X:**
**Axis Y:**

| Competitor | Vector | Time-to-threat | % of value at risk |
|-----------|-----------|-----------|-------|
|Workvivo AI Content Agent | | | |
|Microsoft| Bundle Copilot drafting + Viva Amplify + Viva Engage + Viva Insights, into one native comms workflow — no new product needed, just integration of existing pieces|12–18 months |60% — drafting, scheduling, and basic channel recommendations are replicable. The engagement moat, adoption, and frontline reach are not. |
|Unily Liquid Content|Unily Glass — their AI layer — is being built specifically for enterprise internal comms and EX. They're going deeper on content intelligence, personalisation, and search within a dedicated intranet platform. They don't need to win the whole EX category, just own the comms and knowledge layer better than anyone else.|Less than 6 months, Unily Glass is already in market and maturing | 35% — they're comms-native, enterprise-credible, and their entire product is competing directly with what Workvivo's AI Content Agent is trying to do. Customers evaluating both will ask why they need Workvivo if Unily does comms AI deeper.|
|Canva|Add internal comms publishing ("post to your intranet") to an AI content creation tool 200M people already use and love — distribution via the comms manager's existing personal tool|18–24 months to be credible at enterprise scale | 30% — they own the creation workflow and have brand trust enterprise software can't buy. They don't need the analytics to win the drafting moment.|

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*
ho Attacks You, From Where, With What?
Three threat vectors. Name the attacker. Estimate the timeline. Quantify the damage.

⚡
1. Platform Encroachment
Which platform (OpenAI, Google, Apple, Microsoft) could ship your core feature natively? How long would it take? What % of your value disappears?

2. Vertical Competitor
Which startup is building the same thing but deeper in one niche? What data do they have that you don't?
Unily Glass — their AI layer — is purpose-built for enterprise internal comms. They're going deeper on content intelligence, personalisation, and knowledge search within a dedicated intranet. They don't need to win the whole EX category, just own the comms and knowledge layer better than anyone else. Their pitch to buyers: we do what Workvivo's AI Content Agent does, but it's our whole product not one feature.

4. Adjacent Expansion
Which company next door could add your feature as "one more thing"? What's their distribution advantage?
Fill in: Attacker · Vector · Time-to-threat · % of value at risk
**Attacker: Platform Encroachment - Microsoft**

**Attack vector: Copilot already drafts in Outlook and Teams. Viva already has engagement analytics. Connecting them into a native comms campaign workflow is integration work, not invention. They bundle it into M365 at no extra cost and pitch IT on consolidation.**

**Your defense:Microsoft sees what employees do in Outlook. Workvivo sees how employees feel — reactions, comments, what content gets shared, what gets ignored, what questions go unanswered. That engagement signal is what makes the AI Content Agent smarter over time and what Copilot has no equivalent of. Second line: frontline workers. Microsoft's entire product assumes a desk and a licence. Workvivo's mobile-first deskless reach is structurally hard for them to replicate. Win the frontline, stay safe from the bundle.**


**Attacker: Vertical Competitor - Unily**

**Attack vector:** Unily Glass — their AI layer — is purpose-built for enterprise internal comms. They're going deeper on content intelligence, personalisation, and knowledge search within a dedicated intranet. They don't need to win the whole EX category, just own the comms and knowledge layer better than anyone else. Their pitch to buyers: we do what Workvivo's AI Content Agent does, but it's our whole product not one feature.

**Your defense:** Unily is a comms tool trying to become a platform. Workvivo is a platform where comms is one of many signals. That matters because the AI Content Agent gets smarter from employee behaviour — how people search, what they engage with, what knowledge gaps emerge — not just comms manager behaviour. Unily can't see any of that. Their AI is trained on content creation workflows. Workvivo's is trained on the full employee experience. That's a compounding advantage Unily can't close without rebuilding from scratch.

**Attacker:** Adjacent Expansion - Canva

**Attack vector:** Canva already owns the content creation workflow for comms teams — brand kits, templates, multi-format publishing, 200M+ users. They've been shipping AI aggressively. Adding an internal comms publishing layer ("post directly to your intranet") with AI-generated copy is within their capability and stated direction. They don't sell into IT — they're already in the room via the comms manager's personal tool of choice.

**Your defense:Canva can help you make beautiful content. It has no idea if anyone read it. Workvivo closes the loop — create, publish, measure, improve — in one system. The moment a comms manager asks "did that land?", Canva has no answer. That's where Workvivo wins and where the conversation needs to be anchored. Tactically: embed deeply with comms and HR buyers before Canva's bottom-up adoption reaches IT procurement. Make Workvivo the system of record for comms performance before Canva becomes the system of record for comms creation.**
