# Audit checklist

Each section is 1 tier. Run every item. Record pass, partial, fail, or not measured, with evidence. "Source" names the tool and the metric or setting. A rule value is the source value. Do not round it or replace it.

## Tier 1. Ownership and account safety

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 1.1 | The business owns the Business Portfolio | Business Portfolio settings: owner | The business is the owner | — | An agency or a person outside the business is the owner |
| 1.2 | The business owns the ad account | Ads Manager: ad account owner | Owned in the business portfolio | — | Ads run through an agency ad account, or on the agency's card in its portfolio (red flag: the agency asks for the business credit card to put it into the agency portfolio) |
| 1.3 | Agencies have admin or partner access only | Business Portfolio: users and partners | Admin or partner | — | The agency owns an asset (page, pixel, ad account) |
| 1.4 | A second ad account exists | Ads Manager: ad accounts | 2 or more | Meta does not allow a second yet | 1, and Meta allows more |
| 1.5 | The ads do not run from the hidden personal ad account | Ads Manager: ad account type | Business ad account | — | Personal ad account |
| 1.6 | No unknown pixel or tag is on the site | Wappalyzer and FB Pixel Helper on the site: every pixel ID and tag | Every ID belongs to the business or a current partner | — | An ID that nobody can name (for example a pixel from a former partner) |
| 1.7 | The ads follow Meta's ad policies | Ad copy and creative read against Meta's ad policies | No conflict | — | A conflict. Meta disables accounts immediately |

## Tier 2. Signals

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 2.1 | The pixel fires on each funnel step | FB Pixel Helper: events on each page | Every step fires | Some steps fire | No pixel |
| 2.2 | Each action sends 1 event | FB Pixel Helper: event count per action; or Meta conversions vs backend conversions | 1 event per action | — | 2 or more (a double-deployed pixel) |
| 2.3 | The events are Meta standard events | FB Pixel Helper: event names | Standard events | A mix | Custom events only |
| 2.4 | CAPI runs together with the pixel | The pixel's data source settings in the Business Portfolio; or the business's CAPI integration (for example Shopify's Facebook & Instagram app) | Both run | — | Only 1 runs (pixel only, or CAPI only) |
| 2.5 | Auto-advanced matching is on | The pixel's data source settings | On | — | Off |
| 2.6 | The pixel is seasoned | Pixel event history before the first campaign | Funnel events logged before ads started | — | Ads started on a pixel with no data |
| 2.7 | Meta and the backend agree within a small delta | Meta conversions vs GA4, PostHog, Mixpanel, or the store, same dates | Small, known delta | Delta not known yet | Gigantic delta |
| 2.8 | The pixel and CAPI respect the consent state | FB Pixel Helper in a fresh browser profile, before and after the visitor accepts the consent banner | A banner shows, ad storage is denied by default, and no event fires before acceptance | A banner shows, but events fire before acceptance | No banner. For the legal check, run `ad-law-canada` (Canada). Other markets: `[NEEDS FROM USER: privacy rule for <market>]` |

## Tier 3. Objective and optimization event

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 3.1 | The main campaign objective is Sales or Leads (App promotion for an app) | Ads Manager: campaign objective | Sales, Leads, or App promotion | — | Traffic, engagement, or awareness as the main campaign |
| 3.2 | The optimization event is ideally the purchase or the sign-up | Ads Manager: ad set optimization event | Purchase or sign-up; or a higher event while the pixel has no data | A higher event (landing page view, add to cart) on a seasoned pixel | Clicks or link clicks |
| 3.3 | Traffic campaigns optimize for landing page views | Ad set optimization event | Landing page views | — | Clicks |

## Tier 4. Structure and budget

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 4.1 | One conversion campaign holds the conversion ad sets | Ads Manager: campaign list | 1 conversion campaign | 2 or 3 | Many campaigns (some agencies build 15 to make the setup look too complex for the client) |
| 4.2 | The conversion campaign uses CBO | Campaign budget setting | CBO | — | ABO |
| 4.3 | The budget is daily | Campaign budget type | Daily | — | Lifetime |
| 4.4 | The ad sets can reach 50 conversions in 7 days, or are consolidated | Ad set conversions per 7 days vs 50 | 50 or more; or 1 broad ad set when the budget is below 50 × CPA | — | Many small ad sets (1 per interest, 1 per lookalike) below 50 each |
| 4.5 | Awareness is fixed near $10 a day | Awareness campaign daily budget | About $10 a day, or no awareness campaign | — | Awareness scaled with the budget (for example $100 a day on a $1,000 budget) |
| 4.6 | Retargeting stays at or under about 10% | Retargeting ad set spend ÷ total spend | 10% or less, or no separate retargeting (broad covers it) | — | More than about 10% |
| 4.7 | Time-based pushes are ad sets in the main campaign | Campaign list (for example a BFCM campaign) | Ad set inside the conversion campaign | — | A separate campaign |
| 4.8 | Spend is steady | Daily spend history | Steady daily amount | — | Bursts (for example $300 in 3 days) |
| 4.9 | The account does not use the Boost button | Ad source: Business Suite boosts vs Ads Manager | Ads Manager only | — | Boosted posts |

## Tier 5. Audiences and exclusions

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 5.1 | The main ad set is broad (geo only) | Ad set targeting | Broad | Interest-based, with fewer than 100 customers, a small social following, or a new pixel | Narrow interests or lookalikes only, on a seasoned pixel |
| 5.2 | Each audience is over 1 million people | Audience size in the ad set | Over 1 million | — | Under 1 million |
| 5.3 | Customers are excluded | Ad set exclusions | The "customer" of the business type (build sheet, "Business types") is excluded. DTC: purchasers for 30 or 60 days, matched to the repurchase cycle. SaaS: all customers | Exclusion exists, window does not match the cycle | No exclusion |
| 5.4 | The exclusion uses a pixel audience plus a customer list, refreshed every 6 months | Audience sources and list upload date | Both, list under 6 months old | 1 of the 2, or list older than 6 months | Neither |
| 5.5 | Awareness and traffic exclude site visitors and social engagers | Awareness and traffic ad set exclusions | Excluded | — | Not excluded |
| 5.6 | Age and gender limits are logical | Ad set age and gender, plus breakdowns | No limits, or a logical limit (for example a minimum age that the product requires) | — | A limit with no reason, while breakdowns show conversions in the excluded group |
| 5.7 | A lookalike has enough records and a value column | Customer list: matched records, value column | 100 or more matched, value column present | 100 or more matched, no value column | Under 100 matched |

## Tier 6. Creative and launch rules

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 6.1 | Each conversion ad set has at least 3 statics + 1 motion or UGC | Ad list per ad set | Met | Statics only, 3 or more | Fewer than 3 ads |
| 6.2 | The creative is plain | Ad creative | States what the business does | — | High production that hides the offer |
| 6.3 | Sizes cover the placements | Ad asset sizes | 4:5 or 1:1, plus 9:16 | 4:5 or 1:1 only | 16:9 only, or wrong crops |
| 6.4 | Asset copy and logo are on the image | Ad creative | Both | 1 of the 2 | Neither |
| 6.5 | The copy stands alone on Instagram | Instagram placement preview | The message is in the social copy and the asset copy | — | The message is only in the headline or the description |
| 6.6 | 5 primary text variations, the same 5 across a run | Ad primary text | 5 | 2 to 4 | 1 |
| 6.7 | Video hooks in the first 3 seconds, product front and center | Video, first 3 s; thumbstop column | Product shown in the first 3 s | — | Product hidden |
| 6.8 | New ads got a baseline through a spend rule | Automated rules history | Rule at about $30 or a little above CPA (max CAC ×2, min $20), deleted after every ad hit it | Rule exists but still active after all ads hit it | No rule; Meta put the spend on 1 ad |
| 6.9 | No ad went off by judgment before 72 hours | Ad on/off history vs launch time | No change before 72 h | — | Ads turned off the next day |
| 6.10 | Ads turned off for performance did not drop the campaign | Campaign results before and after each ad went off | No drop | — | Results fell after an ad went off, and it is still off |
| 6.11 | Advantage+ AI enhancements are reviewed at the ad level | Ad settings | Off, or on with a reason | — | On by default, not reviewed |

## Tier 7. Measurement

| # | Check | Source | Pass | Partial | Fail |
|---|---|---|---|---|---|
| 7.1 | The custom columns exist | Ads Manager column set | All groups in the build sheet | Some | Default columns only |
| 7.2 | Outbound CTR is used, not plain CTR | Column set | Outbound CTR | Both | Plain CTR only |
| 7.3 | Every ad has the UTM string | Ad URL parameters | Exact string, `utm_content` = ad name | String differs | No UTMs |
| 7.4 | Names follow a convention | Campaign, ad set, ad names | Convention used | Partly | No convention |
| 7.5 | View-through creep is under control | Conversions by attribution: view-through share | View-through is a minority | — | View-through dominates (for example 90%) and is reported as sales |
| 7.6 | Reports use ROAS, MER, and the backend | Ask the user for the reports to the team | All 3 | 1 or 2 | Meta numbers only |
| 7.7 | Breakdowns are read | Breakdowns: age, gender, location | Read, with an action | — | Never read |
| 7.8 | Each ad is judged against the account average | Ask the user how ads are judged | Yes | — | Judged on gut or by single days |

## Tier 8. Tests

Not errors. List each as a test with its metric.

- After 3 months: 5% to 20% of the budget in test ad sets inside the conversion campaign, with ad set spend minimums (for example an average daily minimum of 20% and a maximum of 40% per test ad set, averaged over 1 week).
- A 0–4% value-based lookalike, then a 4–7% value-based lookalike as the testing ad set.
- New creative, copy, CTA button, landing page, or message variants.
- Ads for a segment that breakdowns show (for example a group that gets little spend but gives a large share of the conversion value).
