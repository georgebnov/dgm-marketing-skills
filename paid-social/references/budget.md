# Budget

The detail for plan step P3 (budget split) and for the small-budget limits in P7 and P8. A line marked "this skill's choice" is procedural glue, not a source rule.

## Currency

The dollar numbers in this skill come from the sources, which do not state a currency. Use them at face value in the account currency. Do not convert them, and do not add a currency to them. Write the account currency next to every plan number (for example "$20 CAD per ad"). This rule is this skill's choice.

## The 5 starter questions

1. Do I have decent website traffic?
2. Has my pixel been set up for a while, and has it logged funnel events?
3. Do I have previous customers? For a pre-launch business, the waitlist or email leads that it already has count as previous customers. This reading is this skill's choice.
4. Is my budget over $100 a day?
5. Do I have videos on social and content on a blog? The question needs both. A blog without videos is "no". Record the blog anyway: it is the destination for a traffic campaign. This reading is this skill's choice.

## The split

| Answers | Conversion | Traffic | Awareness |
|---|---|---|---|
| No to all | 50%: ad set 1 broad, ad set 2 interest-based | 40%: optimize for landing page views, content views, or add to cart | 10%, about $10 a day |
| Yes to all ("brand-formance") | 80% broad | 10% broad, landing page views to blog content | 10% broad reach, exclude site visitors and social engagers |

Mixed answers: use "no to all" while question 2 is "no". Use "yes to all" when questions 2 and 3 are "yes". Write `mixed: <answers>`. This mapping is this skill's choice.

Each column is 1 campaign. The conversion campaign holds the conversion ad sets. The traffic campaign and the awareness campaign are separate campaigns next to it.

## Dropped campaigns and ad sets

Apply these in order. Each one is this skill's choice, from 2 source rules: optimize as deep in the funnel as you can, and consolidate campaigns and ad sets.

1. **Awareness.** The source fixes it near $10 a day and does not scale it. If 10% of the budget is less than about $10 a day, drop the awareness campaign.
2. **Interest ad set 2.** The learning check wins over the split. Keep ad set 2 only when the weekly conversion budget is at least 2 × 50 × CPA (enough for 2 ad sets to exit learning). Otherwise keep only ad set 1, broad. Many small ad sets are a bad idea, and broad wins.
3. **Traffic.** Drop it when the creative baseline cost is too high (see "Small budgets").
4. **Where the share goes.** A dropped campaign's share goes to the conversion campaign. A dropped ad set's share stays in the conversion campaign, because CBO spreads it.

Write each drop in the plan as `dropped: <campaign or ad set> · reason: <rule> · share to: conversion`.

## CPA when the user has none

Use the source example numbers. Mark each one `assumed: source example, not this business`.

| Conversion | Assumed CPA | Source |
|---|---|---|
| A site visit | $1 | Source baseline example |
| An email, a waitlist sign-up, a lead | $5 | Source baseline example |
| A demo sign-up | $20 | Source baseline example |
| A purchase | $10 (low case) and $100 (high case): show both | Source learning-phase arithmetic |

Replace the assumed CPA with the real CPA after the first 72 hours plus the first baselines.

## Learning check

The weekly cost to exit learning is 50 × CPA. At $10 per purchase that is $500 in 7 days. At $100 per purchase it is $5,000 a week. If the weekly conversion budget is below that, write "will not exit learning". This is acceptable: many working campaigns do not exit. Keep 1 broad conversion ad set.

## Small budgets

**Creative baseline cost.** The shut-off rule spends at least $20 per ad. Baseline cost = number of ads under the rule × the threshold. Example: 7 ads × $20 = $140. If the baseline cost is more than 1/3 of the first month's budget, warn the user in the plan and cut in this order (this skill's choice):

1. The awareness campaign and its ads.
2. The interest ad set 2 and its ads.
3. The traffic campaign and its ads. The conversion campaign then starts at the landing page view event (see SKILL.md, P4).
4. Never cut the conversion campaign below 3 static images + 1 motion or UGC (4 ads × $20 = $80).

If 4 ads × $20 is still more than 1/3 of the month, keep the 4 ads, keep the steady daily spend, and write in the plan that the first month buys only the creative baselines.

**Test budget.** After 3 months, put 5% to 20% of the budget into test ad sets. A test ad set needs its own creative baseline: at least 4 ads × $20 = $80 a month. Thus the test budget applies only when 20% of the monthly budget is at least $80, that is a monthly budget of at least $400. Below that, skip the tests and write `tests: skipped, monthly budget under $400`. This limit is this skill's choice.
