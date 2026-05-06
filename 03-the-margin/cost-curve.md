# Cost Curve & Pricing Strategy


🏆 Leader: The feature they come for
Enterprise AI Search
_____________

🍟 Filler: Nice add, bumps ARPU
Catch me up, 
_____________

💀 Killer: Sell separately or die
Agentic execution - book time off (too expensive to bundle)
_____________

_____
Killer usage % 
10–30% of users actively use killer features in a given month. (not something our customers are screaming for, but expensive - so risky to rollout to everyone.
_____
Bundle or add-on
_____
70% rule: if Killer usage is <70%, it is probably an add-on.



| Feature                     | Complexity       | Model Tier         |    Cost / Req | Volume % |          Weighted Cost |
| --------------------------- | ---------------- | ------------------ | ------------: | -------: | ---------------------: |
| **Enterprise AI Search**    | Simple / Medium  | Small + Mid        |     **$0.05** |  **55%** |             **$0.028** |
| **Workflows**               | Medium           | Mid                |     **$0.10** |  **25%** |             **$0.025** |
| **Productivity — Edit**     | Simple / Medium  | Small + Mid        |     **$0.10** |  **10%** |             **$0.010** |
| **Productivity — Create**   | Medium / Complex | Mid + Frontier     |     **$0.50** |   **7%** |             **$0.035** |
| **Agentic Delivery / Claw** | Complex          | Frontier / Agentic | **$0.05 TBC** |   **3%** |             **$0.002** |
| **Blended**                 |                  |                    |               | **100%** | **$0.100 per request** |




| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | 2.25|Enterprise AI Search, Catch Me Up, writing, summaries, Q&A, and workflow outputs |
| Inference (cascading/triage) | $0.40|Low-cost model used to classify requests, route them to the right model tier, rewrite search queries, check confidence, and decide whether a task needs escalation. |
| Infrastructure |$0.35 | Orchestration, permissions, workflow execution layer, observability, job queues, logging, rate limits, and secure action handling.|
| Data/storage |$0.30 | Indexed Workvivo content, connected knowledge sources, workflow context, embeddings, metadata, retrieval cache, and audit logs.|
| Human-in-the-loop |$0.20 | QA sampling, customer onboarding calibration, safety reviews, workflow testing, and evaluation of high-risk outputs.|
| **Total AI COGS** | $3.50| Based on an assumed blended usage cost of approximately $0.10 per AI action and 35 AI actions per user per month.|




## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:**
**Frontier model:**
**Routing rule:**
**Expected cascade ratio:**

## Pricing Model

**Current pricing:**
**Proposed AI pricing:**
**Model:** seat-based / usage-based / outcome-based / hybrid

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | | |
| Heaviest segment doubles | | |
| Model provider raises prices 50% | | |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):**
**After (AI-enabled):**
**Net margin shift:**
