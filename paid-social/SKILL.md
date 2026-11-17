---
name: paid-social
description: Plan or audit paid social ads on Meta (Facebook, Instagram), with LinkedIn ads notes. Covers the pixel, Conversion API, account ownership, campaign structure, audiences, budget split, creative brief, launch rules, metrics. Use for "plan a Meta campaign", "Facebook ads", "audit my ad account", "audit our ads agency", "LinkedIn ads".
---

# Paid Social

This skill has 2 modes. The plan mode returns a campaign plan document for a new paid social program, mainly on Meta. The audit mode returns a ranked list of fixes, each with evidence, for an ad account or an agency setup that exists. The rules come from notes on the paid social and LinkedIn sessions of the TMU Digital Growth Marketing program. The skill does not cover paid search, display or programmatic ads, landing page copy (use `conversion-page`), or organic posting.

## Terms

- **Business Portfolio**: Meta's container for users, Ads Manager, the page, the Instagram account, and the data sources (pixels, catalogs). The campaign sets the objective. The ad set sets the targeting and the optimization event. The ad sets the creative and the UTMs.
- **Signals**: the **pixel** (code on the site that reports visits and actions to Meta) plus **CAPI** (Conversion API, a server-to-server connection from the site to Meta, the safeguard when Safari blocks pixel signals).
- **Seasoned pixel**: a pixel that has logged funnel events for a while. A pixel with no data gives the algorithm nothing.
- **Broad**: no targeting except geography. **Value-based lookalike**: an audience that Meta builds from a customer list with a value column.
- **CBO**: 1 budget on the campaign, and Meta splits it across the ad sets. **ABO**: a budget on each ad set.
- **Learning phase**: an ad set exits learning at **50 conversions in a 7-day period**. Exiting cuts costs. It is not mandatory.
- **TOFU, MOFU, BOFU**: top, middle, bottom of the funnel. **CPA / CAC**: cost per acquisition, customer acquisition cost. **ROAS**: ad revenue ÷ ad spend. **MER**: total revenue ÷ total marketing spend. **Delta**: the usual gap between Meta's numbers and the backend (GA4, PostHog, Mixpanel, or the store, for example Shopify).
- **Dollars**: every $ number is a source number. The sources state no currency. Use the numbers at face value in the account currency, and write that currency in the plan (this skill's choice).
- **Buying data**: a first paid program buys data more than it buys results. The product is a set of baseline costs. For social, you buy data for at least the first month.

## Precedence

When 2 rules fire against each other, these lines decide.

1. **Signals before spend.** Fix a missing, broken, or duplicated pixel or CAPI first.
2. **Broad wins** over interests and lookalikes. An interest ad set is allowed only with fewer than 100 customers, a small social following, or a new pixel (the "no to all" starter split). A lookalike goes into the intermediate structure or a test ad set.
3. **One conversion campaign** holds every conversion ad set. The budget split decides only whether a traffic campaign and an awareness campaign exist next to it. Time-based pushes (for example BFCM) are ad sets inside the conversion campaign.
4. **Awareness is fixed near $10 a day.** Do not scale it with the budget. This skill also applies it to the "yes to all" split. If 10% of the budget is below about $10 a day, drop the awareness campaign. Its share goes to the conversion campaign (this skill's choice).
5. **Rules kill ads. Judgment waits 72 hours.** To kill weak ads quickly, use a spend rule that turns ads off. Never turn off an ad by judgment before 72 hours of data. If an ad went off and results fell, turn it back on.
6. **Shut-off threshold.** Default: about $30 of lifetime spend per ad, or a little more than the CPA. The alternative in the source is CAC ×2. The floor is $20 per ad. Using CAC ×2 as the upper limit is this skill's choice.
7. **Attribution.** Start with 7-day click + 1-day view, because it feeds the most data to the algorithm. Change to 7-day click when view-through dominates (accounts can reach 90% view-through), or when the numbers must match a last-click backend. This switch rule is this skill's choice.
8. **"Boost" means Ads Manager.** Never use the Boost button or Meta Business Suite. To amplify an organic post, put it in the awareness campaign, exclude everyone who visited the site, and spend about $10 extra on it.
9. **Never pay to reach people you already acquired.** Every conversion ad set excludes customers. Retargeting reaches visitors and engagers only, at or under about 10% of the budget.
10. **Meta before LinkedIn.** Start on Meta (or Google, for a business that people already search for). A typical case: $250 per lead on LinkedIn, $25 on Meta. LinkedIn rules apply only when the user already runs LinkedIn ads or adds LinkedIn second. Push back on a LinkedIn-first request 1 time, then plan what the user asks.

## Inputs

1. **Mode**: plan or audit.
2. **Business type**: DTC or e-commerce, SaaS, B2B sales-led, lead generation, app in the store, pre-launch (waitlist or email lead), or local service. The build sheet, "Business types", gives the objective, the conversion, and the exclusion for each.
3. **The conversion**: the 1 backend event that counts (purchase, sign-up, lead, free trial, demo, install).
4. **Answers to the 5 starter questions** (step P3).
5. **Daily budget**, and the known CPA or CAC.
6. **Customers**: the count, a list with first name, last name, and email, a value per customer (AOV, contract value, or LTV), and the repurchase cycle for DTC.
7. **Geography, language**, and any logical age, gender, or device limit.
8. **Assets**: the site URL, the Instagram account (count of Reels), videos, blog or white paper content.
9. **Ownership**: who owns the Business Portfolio, the ad account, and the pixel. Whether an agency runs the account.
10. **Audit only, access level**: best is Ads Manager with custom columns and breakdowns, plus the backend numbers for the same dates. The minimum is the site URL.

If an input is missing, ask the user. If you cannot ask (for example, you run as a subagent), apply this split (this skill's choice):

- **Block** on input 1 (mode), input 3 (the conversion), the daily budget in input 5, input 9 (ownership; never plan spend on an account that the business may not own), and input 10 in audit mode. Return a line that starts with `BLOCKED:` and list each one.
- **Assume** the rest, and mark each dependent line `assumed: <what you assumed>`. Input 2: infer it from the site. Input 4: "no" for each unknown answer. CPA: the source examples in `references/budget.md`. Input 6: 0 customers. Input 7: the country of the business. Input 8: what the site and the Instagram account show.

## Plan mode

Read `references/build-sheet.md` before step P2. It holds the setup, signals, structures, audiences, naming, UTMs, creative, columns, and LinkedIn detail.

**P1. Go or no-go.** Answer 3 questions, 1 line each:

1. Do people search for this category, and who owns that results page? Search captures intent. Social is for discovery.
2. Are retention, referrals, email, and organic in place? Paid is last.
3. Is the destination ready (build sheet, "Destination")?

A "no" on question 2 or 3 does not stop the plan. It goes first in the setup checklist. Done when: each question has a line, and the platform is named.

**P2. Setup and signals.** Write the checklist from the build sheet, "Setup" and "Signals". Install the signals today even if the launch is months away. Include the consent check (build sheet, "Signals" step 7). For the legal check, run `ad-law-canada` (Canada). Other markets: `[NEEDS FROM USER: privacy rule for <market>]`. Done when: each item has an owner and a status (done, to do, not applicable).

**P3. Budget split.** Read `references/budget.md` now. It holds the 5 starter questions, the split table, the mixed-answer mapping, the CPA to assume, the learning check, and the rules for dropped campaigns and small budgets. The core split:

- **No to all**: 50% conversion (ad set 1 broad, ad set 2 interest-based), 40% traffic, 10% awareness (about $10 a day).
- **Yes to all** ("brand-formance"): 80% broad conversion, 10% broad awareness, 10% broad traffic to blog content.

The learning check wins over the split: ad set 2 stays only when the budget lets 2 ad sets reach 50 conversions in 7 days. Done when: each campaign has a % and a $ per day, each drop has a reason and says where its share went, and the learning check has a line.

**P4. Campaign structure.** Pick the tier from the build sheet, "Structures":

- **Starter**: no seasoned pixel, or fewer than 100 customers.
- **Intermediate**: a seasoned pixel, at least 100 matched customer records, and video or blog content.
- **Advanced**: a later option only. Do not plan it now.

These tier limits are this skill's reading of the audience and lookalike rules, not a source rule.

Set the objective from the build sheet, "Business types" (Leads for a pre-launch waitlist), CBO, a daily budget, and the optimization event. The event is ideally the purchase or the sign-up. Meta finds the people who do the event that you ask for. Never optimize for clicks. With no data and no sales, start at a higher event (landing page view, then add to cart) and moves down. This skill applies that rule so (this skill's choice):

- If a traffic campaign exists, it buys the landing page views. The conversion campaign optimizes for the conversion event from day 1.
- If there is no traffic campaign, the conversion campaign starts at the landing page view event.
- Move the event 1 step down the funnel when the pixel has logged at least 50 of the next event in total, and at least 72 hours passed since the last change.

Use the build sheet names. Done when: each campaign has its objective, budget type, ad sets, optimization event, attribution window, and names.

**P5. Audiences and exclusions.** Apply the build sheet, "Audiences": broad over 1 million people, logical age, gender, or device limits only (an iOS limit for an iPhone-only product is logical), customer exclusions matched to the business type, and a lookalike only in the intermediate tier. For a B2B or LinkedIn-trained user, write the B2B variant. Before a list upload, run `ad-law-canada` ai-and-privacy.md on the purpose of the list. Done when: each ad set has its audience, size check, and exclusions.

**P6. Creative brief.** Apply the build sheet, "Creative". Each conversion ad set gets at least 3 static images and 1 motion or UGC asset. Each asset states the plain thing the business does. Ask the user for the product facts. Never invent a claim. Done when: each asset has sizes, asset copy, social copy, a CTA button, and 5 primary text variations.

**P7. Launch rule and the first 72 hours.**

1. Upload the new ads, and apply a rule that turns each ad off at the lifetime spend from Precedence 6.
2. When every ad hit the threshold, delete the rule and turn all ads back on. Now each creative has a baseline.

Baseline cost = number of ads under the rule × the threshold (7 ads × $20 = $140). If it is more than 1/3 of the first month's budget, warn the user and cut ads in the order in `references/budget.md`, "Small budgets".

Spend a steady daily amount. $10 a day every day is better than $300 in 3 days. In the first 72 hours, check only that each event fires once (FB Pixel Helper), each ad delivers, the rule fires at the threshold, and the UTMs arrive in the backend. Make no performance decision: all data takes 72 hours to reach Meta. After 72 hours, compare each ad with the account average on the custom columns. Never let a paid campaign run for a month without a look. Done when: the rule, its threshold, and the 72-hour watch list are in the plan.

**P8. Measurement and tests.** Name the custom columns, the backend, and the delta check. After 3 months, put 5% to 20% of the budget into test ad sets inside the conversion campaign, with ad set spend minimums. Skip the tests when the monthly budget is under $400 (`references/budget.md`). Set a maximum only for retargeting (about 10%). Read breakdowns for audience insight. Done when: the plan names each column, the backend, and the first test.

**P9. LinkedIn** (only when Precedence 10 allows it). Add a section from the build sheet, "LinkedIn": the Insight Tag, the ad type for the offer, and the cost warning.

## Audit mode

**A1. Collect the evidence** that the access level allows:

- Site: run FB Pixel Helper and Wappalyzer (Chrome extensions) on the home page, a product or pricing page, and the conversion step. Record each pixel ID, each tag, and the event count per action. Repeat in a fresh browser profile before you accept the consent banner.
- Ads Manager: the campaigns, ad sets, and ads with their settings, the custom columns for the last 30 days, the breakdowns, and the automated rules.
- Backend: conversions for the same dates.
- Business Portfolio: the owner, users and partners, ad accounts, and data sources.

**A2. Run the checklist.** Read `references/audit-checklist.md` now and run every item. Each item gets 1 result:

- **pass**: the evidence meets the rule.
- **partial**: part of the rule holds, or an "ideally" item has a weaker setting that the rule allows. The checklist names each partial.
- **fail**: the evidence breaks the rule.
- **not measured**: no access. Name the missing access. Never guess a result.

Evidence is a setting ("Campaign budget: ABO, 7 ad sets"), a count ("Purchase fired 2 times on 1 order"), a metric with its column and dates, a name ("pixel ID nobody can name"), or a quote of the ad copy. With site access only, tiers 1 and 2 are partly measurable from the site. Mark the rest not measured. Done when: every item has a result and evidence.

**A3. Agency variant.** Run tier 1 first. The red flag: the agency puts its own pixel on the site, runs the ads through its own ad account, and bills the business.

**A4. Rank the findings** by checklist tier. Inside 1 tier, fails come before partials, and the finding with the most spend comes first.

1. Ownership and account safety
2. Signals
3. Objective and optimization event
4. Structure and budget
5. Audiences and exclusions
6. Creative and launch rules
7. Measurement
8. Tests (not errors)

Done when: every fail and partial has 1 tier.

**A5. Write each fix** as the exact change: `Change the conversion campaign to CBO` or `Remove the second pixel snippet so Purchase fires once`. If a fix needs a number you do not have, write `[NEEDS FROM USER: ...]`.

## Output

**Plan mode**, a campaign plan document in this order:

```
# Paid social plan: <business> · <platform>
Business type: <type> · conversion: <event> · daily budget: <$ and account currency> · geo: <countries>
Go/no-go: <go | go after setup> · reasons: <1 line per P1 question>

## 1. Setup checklist
- [ ] <item> · owner: <who> · status: <done | to do | n/a>

## 2. Signals and tracking
Pixel: <status> · CAPI: <status> · events: <standard event per funnel step> · auto-advanced matching: <on | off>
Consent: banner <yes | no> · ad storage denied by default <yes | no> · pixel before acceptance <fires | silent> · legal check: <skill run>
Seasoning: <events logged so far, or "season from <date>">

## 3. Budget
Starter answers: <5 answers> → split: <no to all | yes to all | mixed: ...>
| Campaign | % | $ per day |
Dropped: <campaign or ad set> · reason: <rule> · share to: conversion
CPA: <$> · <user number | assumed: source example>
Learning check: 50 × <CPA> = <$ per week> vs <conversion $ per week> → <will exit | will not exit learning>

## 4. Campaign structure (<starter | intermediate>)
| Campaign | Objective | Budget | Ad set | Optimization event | Attribution | Name |

## 5. Audiences and exclusions
| Ad set | Audience | Size check | Exclusions |

## 6. Creative brief
| Asset | Type | Sizes | Asset copy | Social copy (5 variations) | CTA | utm_content |
Facts needed: <[NEEDS FROM USER: ...]>

## 7. Rules
Shut-off rule: lifetime spend <$> per ad · delete when every ad has a baseline
Baseline cost: <ads> × <$> = <$> of <$ month 1> → <ok | warning: cut list>

## 8. First 72 hours
- <check> · tool: <tool> · pass when: <condition>
No performance decisions before: <launch + 72 h>

## 9. Measurement and tests
Columns: <list> · backend: <tool> · review: <cadence, shorter than 1 month>
After 3 months: <test ad set, % of budget, spend minimum | tests: skipped, monthly budget under $400>

## 10. LinkedIn (only if in scope)
```

**Audit mode:**

```
Account: <ad account or site> · access: <site only | Ads Manager | full> · dates: <range>
Verdict: <1 line: the single fix that matters most>

1. [tier N · fail | partial] <check #>: <problem>
   evidence: <setting, count, metric with column and dates, name, or quote>
   fix: <exact change>
2. ...

Not measured: <check #: missing access>
Tests to run: <tier 8 items, each with its metric>
```

## Checks before done

- [ ] No recommendation runs before a signal problem is fixed (Precedence 1).
- [ ] Every number is a source number from this skill, a user number, or arithmetic on them. Each missing user fact has a `[NEEDS FROM USER]` or `assumed:` marker.
- [ ] Plan: 1 CBO conversion campaign on a daily budget, a broad ad set, exclusions, the attribution window, and at least 3 statics + 1 motion or UGC.
- [ ] Plan: the shut-off rule is at least $20 per ad, and no performance decision falls before 72 hours.
- [ ] Plan: awareness is about $10 a day or absent. Retargeting is at or under about 10%.
- [ ] Plan: each dropped campaign or ad set has its reason and its share destination. The plan has the consent line and the account currency.
- [ ] Audit: every checklist item has pass, partial, fail, or not measured, with evidence. Findings are in tier order.
- [ ] Each fix is an exact change.
