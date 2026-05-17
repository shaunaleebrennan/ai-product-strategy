# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|---|---|---|---|
| **Provider** — Zoom AI Companion | Workvivo doesn't call LLM APIs directly. We run on Zoom's federated AI layer, which itself routes to multiple underlying model providers (Anthropic, OpenAI, Zoom-hosted models, custom). Workvivo doesn't choose which provider serves which request — Zoom does. | H | Document every Zoom AI Companion endpoint HQ depends on. Map which AI surface (Liquid Content, Catch Me Up, Ask HQ, Seer) routes to which Zoom path. Identify which paths have fallback options. |
| **Abstraction** | The abstraction exists at the Zoom platform level, not at the Workvivo product level. We can't swap models independently — that decision sits with Zoom. | H | Priority: identify whether Workvivo can configure or override model routing inside Zoom AI Companion, and to what extent. Get a clear answer from Zoom AI engineering by end of week. |
| **Routing** | Workvivo has some product-level routing logic, but with limited time, budget, and engineering capacity. To hit the June 14 launch, Zoom does the heavy routing. If Zoom routes to a different underlying model, Workvivo inherits the change with no control. | H | Map the dependency chain: Workvivo → Zoom AI Companion → [underlying model]. Document explicitly what we don't control. |
| **Eval** | Workvivo's QA team monitors AI outputs. Zoom has platform-level evals for general AI Companion quality. But product-level evals for comms output (tone accuracy, channel fit, edit rate, campaign performance lift) need to be run by the Workvivo team. | M | Define 5 baseline eval criteria for HQ AI surfaces. Even a manual scorecard is better than nothing. |

## Portability Score

**Partial.**

The underlying model layer has portability because Zoom's federated architecture uses multiple providers. But Workvivo itself cannot exercise that portability independently. Any swap decision runs through Zoom, not through the Workvivo product team.

That's a meaningful distinction: the risk isn't that we're locked to one LLM. It's that we're locked to one platform (Zoom) that controls our LLM access. The kill switch sits at Zoom, not at Workvivo.

## If Zoom AI Companion doubles pricing tomorrow

We've already navigated a version of this — pre-launch. Zoom shifted to a consumption-based pricing model and raised per-call costs before HQ shipped. Customers weren't impacted directly because they didn't have the AI yet, but the change forced hard pre-launch scope decisions about what AI we could afford to deliver in HQ Core at the planned price point.

**What we did:**

1. **Audited which AI features were driving the highest consumption costs.** Deep research, agentic search across systems, long-form generation — the heavy compute paths.
2. **Mapped customer value to consumption cost for each feature.** Core to the HQ pitch vs premium use cases that didn't need to live in Core.
3. **Re-tiered the AI surface accordingly.** Heavy-compute features moved up into HQ+ and HQ+ Enterprise where the price supports them. HQ Core ships with the AI features that have strong unit economics at $2–6/user.
4. **Held the customer price.** Customers get the planned tier price. The product shape adjusted; the deal didn't.

**What we'd do if it happened again post-launch:**

The pre-launch playbook gets harder once customers are on contract. Tier shifts require notice (typically >90 days for material changes), and we can't reactively move features between tiers without breaking commitments. So the post-launch response leans on three things:

- **Consumption ceilings per tier.** Cap heavy compute usage in HQ Core. Route overflow into HQ+ at upgrade pricing rather than pulling the feature.
- **Cost optimisation at our layer.** Cache repeated retrievals. Default to smaller models for routine work. Reserve frontier models for the use cases that need them.
- **Communicate value continuity, not feature change.** "You still get what we promised — here's how you scale beyond it." Not "we changed what you got."

The lesson: Zoom's pricing decisions will hit us. We don't have control, but we have response time — and response time is the differentiator.

## If Zoom AI Companion ships a competing product

This is the kill switch question that doesn't quite apply to us — and that's worth surfacing honestly.

Workvivo isn't a third-party Zoom customer. We're a Zoom brand. Zoom doesn't ship competing products against its own brands, so the conventional version of this question (will the platform compete with us?) is the wrong question.

The real risk is the inverse. If HQ becomes the most valuable AI launch in Zoom's portfolio, the relationship dynamic changes. Zoom may want more direct control over roadmap, sales priority, or brand. Internal absorption is the kill-switch scenario for Workvivo, not external displacement.

**What's defensible:**

- **The EX surface area Zoom doesn't naturally have.** Workvivo brings 9M employees on platform, 90% adoption, comms and HR expertise, frontline reach, and brand resonance inside internal comms — places Zoom Phone and Zoom Workplace don't reach naturally.
- **The customer base and the trust we've built.** Forrester Wave Leader, Gartner MQ Leader, 96% retention. That's a brand and analyst position Zoom can't replicate by relabelling internal product.
- **The product expertise.** EX product design isn't productivity product design. The team that built Workvivo knows things Zoom Workplace teams don't — and that knowledge sits in the people, not the codebase.

**The honest answer:** Our kill switch isn't model portability. It's organisational positioning inside Zoom. We protect the bet by making HQ the clearly-defined, distinctly-valuable EX brand inside the Zoom portfolio — not by trying to be model-portable in a way the federated architecture makes impossible.

## Portability Actions

**This week:**
- Document every Zoom AI Companion endpoint HQ depends on, by surface (Liquid Content, Catch Me Up, Ask HQ, Seer, Compose).
- Get a clear answer from Zoom AI engineering: what can Workvivo configure or override at the routing level, and what is owned end-to-end by Zoom?

**This month:**
- Define the 5 product-level eval criteria for HQ AI outputs. Run a manual scorecard against current production for baseline.
- Map the consumption cost of each AI surface. Identify the top 3 cost drivers and document the trim plan we've used (and would use again).
- Formalise the tier-trimming response playbook from the recent pricing event. Turn one-time crisis response into a documented <72-hour response process for next time.

**This quarter:**
- Build product-level routing where we can — even partial control over which Zoom path each request takes is better than zero control.
- Get a written commitment from Zoom on the roadmap for product-level routing controls inside Zoom AI Companion.
- Pressure-test the "if HQ gets too successful" scenario internally. Define what brand independence inside Zoom looks like for FY28 and beyond.
