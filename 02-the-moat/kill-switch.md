# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** Zoom AI Companion|Workvivo doesn't call LLM APIs directly, it runs on Zoom's federated AI layer which itself uses multiple underlying model providers (Anthropic, Open AI, Custom AI, others)| H | Document which Zoom AI Companion endpoints the AI Content Agent actually depends on, and assess what backup options are available to us.|
| **Abstraction** |Abstraction exists at the Zoom platform level, not at the Workvivo product level. Workvivo can't swap models independently, that decision sits primarily with Zoom.| H |We are currently working to identify whether Workvivo can configure or override model routing within the Zoom AI Companion layer, and to what extent - make this a priority. |
| **Routing** |Workvivo-level can do some of its own model routing, but with limited time, budget, and resources to execute. So Zoom is going to be our core routing if we want to GTM on time. If Zoom routes to a different underlying model, Workvivo inherits that change with no control. | H | Map the dependency chain: Workvivo → Zoom AI Companion → [underlying model]. Know what you don't control.|
| **Eval** | Workvivo QA team will monitor outputs. Zoom has platform-level evals, but product-level evals for comms output quality, tone accuracy, and campaign performance will need to be ran through the Workvivo team.| M | Define 5 baseline eval criteria for AI Content Agent output (tone accuracy, channel appropriateness, readability score, edit rate, campaign performance lift) — even a manual scorecard is better than nothing|

## Portability Score
<!-- Partial -->
The underlying model layer has some portability because Zoom's federated architecture uses multiple providers. But Workvivo itself cannot exercise that portability independently. Any swap decision runs through Zoom, not through the Workvivo product team. That's a meaningful distinction: the risk isn't that you're locked to one LLM, it's that you're locked to one platform (Zoom) that controls your LLM access.

## If Zoom AI Companion doubles pricing tomorrow:
<!-- What's your 48-hour response? -->
This is an actual issues we are dealing with right now, Zoom introduced a new consumption model, and pushed their price up - essenrtially locking our customers out of the solution being affordable. Our action plan invovled reviewing what portion of the product our customers don't need and that are most expensive - this is primialry deep research and compute. We have managed to find a middle ground which allows us to still offer valuet to customers, while still adopting comsumption based pricing model.

## If Zoom AI Companion ships a competing product:
<!-- What's defensible that they can't replicate? -->
We are that model for Zoom, as we are a Zoom brand - the risk is that it will be so succesful that they want more roadmap and sales 
