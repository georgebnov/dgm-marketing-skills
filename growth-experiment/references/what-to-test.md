# Choose what to test

Read this file in step 1 when the user has no test surface yet, or names a goal but not a stage.

1. Map the funnel. Any model works. Example states: sessions (came to the site) → leads (gave an email) → prospects (gave card details) → customers (pay). For sales-led B2B: MQL → SQL → opportunity → proposal → negotiation → closed-won or closed-lost.
2. Write 1 baseline number next to each stage. Without baselines, you do not know where to start.
3. Find the weakest stage: the biggest drop-off and the easiest number to double. Example: 2% of visitors convert. The question is how to get to 4%. Use this table for the likely cause:

| Symptom | Likely problem |
|---|---|
| Visitors do not convert | CRO, or the channel and audience that brings them |
| Leads never convert to paid | Lifecycle or product |
| People start onboarding but do not finish | Onboarding or CRO |
| Users never buy upsells, cross-sells, or expansion | Lifecycle or customer marketing |

4. If no baselines exist, the first job is to buy data, not results. A first paid program buys data more than it buys results. Plan the buy-data program with `paid-social` (plan mode). It holds the budget numbers. The output is baseline costs. Then return to item 3. This is measurement before the experiment, not an experiment.
   - No ad budget (skill convention): skip the paid baseline. Never invent a budget. Take baselines from the traffic that exists. Sources: site analytics (GA4, Mixpanel, or PostHog), app store data, and the waitlist or email list (sign-ups per week, open rate). A stage that does not exist yet (for example purchase, before launch) gets `baseline: none (pre-launch)`. Name the weakest stage that you can measure, and mark the rest `assumed`.
5. Pick the test surface in the weakest stage. Testable areas: conversion, engagement, pricing, discounting, feature usage, ad creative, usability, messaging, onboarding, cart and forms, content, retention.
6. Look for ideas in unusual behaviour (why did they do that?) and in data anomalies (a number much higher or lower than expected).

SEO and organic social are harder to test. There you test whether Google or Meta responds, and those learnings are not persistent. Run experiments on your customers, not on algorithms. If the user asks for an SEO or organic social test, say this in the brief, and prefer a test of customer behaviour.
