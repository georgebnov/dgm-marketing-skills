# Build sheet

The setup, structure, naming, creative, and measurement detail for plan mode. Audit mode uses the same values as its pass rules.

## Destination

Check these before any ad sends traffic. Each item is pass or fail.

- Site description, responsive design (it works on a phone without pinching), navigation, no URL discrepancies, links off-site, image titles optimized for search, and social media icons.
- Open Graph and Twitter cards (`og:title`, `og:description`, `og:image`). These tags set the title, text, and image that show when someone shares the link.
- Social sharing, pixels for retargeting, design and layout, copy (how it feels and reads), and Google Search Console.
- The Instagram account has at least a couple of Reels that almost mirror the site, so that a visitor understands the value propositions quickly. No ad sends a click to an empty Instagram account or LinkedIn page.

## Setup

1. Never use the hidden ad account that Meta makes for every personal Facebook or Instagram account.
2. Create a Business Portfolio (business.facebook.com/create). Connect the Facebook page and the Instagram account to it.
3. Create a new ad account for the business inside the portfolio, or attach the current business ad account.
4. Create a second ad account as soon as Meta allows it. Meta can shut down an ad account with no reason and no explanation. Without a second ad account, you must abandon the whole portfolio.
5. Connect the data sources: the pixel, and the catalog for DTC. On Shopify this is 1 click through the Facebook & Instagram app.
6. The business owns the portfolio and the ad account. Agencies and freelancers get admin or partner access only. Never run ads through an ad account that the business does not own. When the partnership ends, the agency keeps the data and can turn the pixel data into lookalikes for another client.
7. Check the tags deployed on the site on a regular basis, and remove unknown ones. An unknown third-party pixel, deployed years before by a former partner, can still send every visitor's data to that third party.
8. Read Meta's ad policies, or give them to an AI tool, before you build. Meta disables ad accounts immediately for violations.

## Signals

1. Install the pixel on the site. For a non-DTC site, use Google Tag Manager. These options are free.
2. Use Meta standard events, not custom events. Map each funnel step to 1 standard event. The e-commerce ladder: landing page view → content view → add to cart → purchase. Map it to the business funnel (for example sign-up, lead, free trial).
3. Enable auto-advanced matching.
4. Enable CAPI if you can. Run the pixel and CAPI together. Do not run CAPI alone. Sometimes 1 of the 2 fails.
5. Check that each action sends 1 event. A common failure: the pixel is deployed twice, each purchase sends 2 purchase events, Meta does not deduplicate them, and the ads look twice as good as they are.
6. Season the pixel before the first campaign. If the ads start in 6 months, install all the ad tech on the site today. With no data and no sales, run a little landing page view spend first, then move down the funnel.
7. Check consent (this step is this skill's choice; the source gave no consent rule). Open the site in a fresh browser profile and run FB Pixel Helper. Record 3 facts: whether a consent banner shows, whether ad storage is denied by default before the visitor accepts, and whether the pixel fires before acceptance. Accept, and record again. CAPI must send events only for visitors whose consent state allows it. Ask the user how the CAPI integration reads the consent state. For the legal check, run `ad-law-canada` (Canada). Other markets: `[NEEDS FROM USER: privacy rule for <market>]`. This skill gives no legal rule.
8. Also install the LinkedIn Insight Tag if LinkedIn is in scope.
9. Add UTMs to every ad (see "Naming and UTMs"). Add a post-purchase survey ("Where did you hear about us?"). Pick 1 attribution model and run with it.

## Structures

Objective choice. Most businesses use Sales or Leads.

| Objective | Funnel stage |
|---|---|
| Awareness | TOFU |
| Traffic | TOFU / MOFU |
| Engagement | TOFU / MOFU / vanity |
| App promotion | BOFU |
| Leads | MOFU / BOFU |
| Sales | MOFU / BOFU |

**Starter**

The starter structure in the source has only the conversion campaign. The "no to all" budget split adds a traffic campaign and an awareness campaign next to it. The rows marked "split" come from the split, and `references/budget.md` decides when each one is dropped.

| Campaign | Ad sets | Ads |
|---|---|---|
| Conversion | Ad set 1: broad (geo only). Ad set 2 (split, only if the budget allows it): interest-based. Optional later: video viewers + social engagers. Exclude current customers. | At least 3 static images + 1 motion or UGC |
| Traffic (split, 40%) | Broad with exclusions | 3 static images. Optimize for landing page views, content views, or add to cart. |
| Awareness (split, 10%, about $10 a day) | Broad, exclude site visitors and social engagers | Motion or video |

**Intermediate**

| Campaign | Ad sets | Ads |
|---|---|---|
| Awareness | Broad with exclusions | Motion or video only, 3 of them. Upload every length you have (for example 5 s, 10 s, 15 s, 55 s). Add a link. Video builds audiences without a click (for example 3-second viewers). |
| Traffic (LPVs) | Broad with exclusions | 3 static images. Send traffic to blogs and white papers. Write the blog title on the image. Optimize for landing page views, never clicks ("clicks" counts any click anywhere). |
| Conversion | Broad (geo only) + 0–4% value-based lookalike | 3 static images + motion or UGC |

**Advanced** (the most complex version; do not plan it now). One CBO conversion campaign. Ad sets: broad (geo only), 0–4% value-based lookalike, video viewers + social engagers + site retargeting, a time-based ad set (for example BFCM 2026), and a testing ad set (4–7% value-based lookalike). Ads: 3 statics, motion, UGC, long-form video. The retargeting ad set matters for DTC: build the audience from awareness campaigns all year, then retarget it during Black Friday and Cyber Monday, when costs spike.

**Settings for every campaign**

- Campaign: CBO, daily budget. A lifetime budget of $300 must be raised again and again. A daily budget keeps a working campaign running.
- Ad set: the optimization event, English language, exclusions, lowest cost, attribution window.
- Be careful with Meta's AI enhancements (Advantage+), mainly at the ad level.
- A single conversion campaign can run for years. Add ad sets inside it, not new campaigns.

## Business types

The objective, the conversion, and the "customer" to exclude for each type. The DTC and SaaS exclusions come from the source. The other rows extend its rule "never pay to reach people you already acquired" and are this skill's choice.

| Type | Objective | Conversion (standard event) | Exclude as "customer" |
|---|---|---|---|
| DTC or e-commerce | Sales | Purchase | Purchasers for 30 or 60 days, matched to the repurchase cycle |
| SaaS | Sales or Leads | Sign-up, free trial, or purchase | All customers |
| B2B, sales-led | Leads | Lead or demo | All customers and open leads |
| Lead generation | Leads | Lead | Leads already captured |
| App in the store | App promotion | Install | Users who installed |
| Pre-launch (no product in the store yet; the goal is a waitlist or an email lead) | Leads. App promotion needs an app in the store, so it does not apply. | Lead or CompleteRegistration on the waitlist form | Every waitlist lead (the pixel audience of the sign-up event plus the uploaded waitlist) |
| Local service | Leads | Lead or booking | Customers for the repeat cycle of the service, as for DTC |

Pre-launch notes (this skill's choice): the waitlist lead is both the conversion and the "customer". After launch, change the objective and the conversion to the app or store event, and keep the waitlist excluded.

## Audiences

- **Broad**: geography only. Keep each audience over 1 million people. A smaller audience gives CPMs above average. With fewer than 100 customers, a small social following, or a new pixel, start broad, and maybe use interests to guide the algorithm. With a seasoned pixel, run broad.
- **Interests**: search them by demographics and behaviors. Competitors show up as interests only if they are large (for example a platform that spends millions on ads). Meta does not show how it builds interests.
- **Age and gender**: limit only when it is logical. A car rental service that rents only to drivers aged 24 or older sets the minimum age to 24.
- **Device or operating system**: the source gave no device rule. This skill treats it like a logical age limit: limit to a device (for example iOS for an iPhone-only app) only when the product works only on that device. The limited audience must still be over 1 million people. This rule is this skill's choice.
- **Exclusions**: DTC excludes purchasers for 30 or 60 days, matched to the repurchase cycle (a soap that takes 90 days to replenish gets 90 days). SaaS excludes all customers. A short form: exclude purchasers for 30 days, or customers for 180 days. Build the exclusion from a pixel audience (it can go back 720 days) plus the uploaded customer list. Refresh the list every 6 months. With no customer list, the exclusion is the pixel audience alone. For other business types, see "Business types".
- **Lookalike**: the only secondary audience to try. Upload at minimum first name, last name, and email. Pick a country and a percentage of its population, up to 10%. You need at least 100 matched records. The match rate is about 85%, so upload about 125 to 150 customers. About 800 emails is enough. If you have to, build the lookalike from a pixel or other custom audience (website, app, video viewers, Instagram engagers, lead forms).
- **Value-based lookalike**: add a value column. E-commerce: AOV (a $200 customer beats a $20 customer), or repeat customers. B2B and SaaS: contract value or LTV (for example customers with at least 6 months on the platform and steady monthly revenue). To keep real revenue private, upload a derived score instead of the real values.
- **Retargeting**: broad already covers it. If you break it out, cap it at about 10% of the budget.
- **B2B on Meta**: an audience cannot leave LinkedIn. Enrich instead: get ICP emails with a tool such as Gong or ZoomInfo. Upload more than 800, check the match rate, and target the list plus a 1% lookalike. Use the real countries: a 1% lookalike from 800 emails in Canada and the US is still about 1 million people, which can be more than the worldwide TAM of a niche B2B product. Target the whole company, not only the decision maker, so the people around the buyer also see the ads and talk about them. Some reach goes to people outside the ICP, but the cost is probably better. The ads can do part of the work of the sales team. Run several ads with different messages, but not too many (17 is too many). Some ads do middle-funnel work with no conversions. Take a loss on them when the campaign overall performs.
- **Audience insight under broad targeting**: use breakdowns. Example: a jewelry brand assumes that only women buy, but leaves men in the broad targeting. The breakdown shows that men get little spend but give a large share of the conversion value (engagement rings). The brand keeps broad and adds ads made for men. Insight by job title stays tricky on Meta.

## Naming and UTMs

Short forms on purpose, so that competitors cannot reverse-engineer the targeting.

- Campaign: type plus version, for example `Conversion Campaign v1`.
- Ad set: `Objective_Geography_Audience_Attribution`, for example `sales_ca_broad_7dc1dv_v1`. The attribution part is optional.
- Ad: `ad_set_name_short_form | copy version / asset-description_asset-copy | asset size and type | destination url`, for example `ca_broad_v1 | copy_v2 / demo-video_save-time | vid 4:5 | dest: /pricing`.
- UTM string. Copy it exactly. Change only `utm_content` to the ad name:
  `utm_campaign={{adset.name}}&utm_source={{site_source_name}}&utm_medium=cpm&utm_content=your_ad_name`

## Creative

- Keep it simple. Give value, and give a solution to a pain point, or identify with the target audience. Do not decorate the offer. Say the plain thing that the business does. People recognize high production as an ad.
- Plain benefit lines win: say what the customer gets and what they do (for example "We prepare your return, you sign it"). A clever abstract line (for example "Your finances, reimagined") can fail. A simple product demo video can give a low CPA. An ad that the team is sure of can also fail. You do not know until you test.
- Sizes: 4:5 works in all placements, 1:1 is also fine. Add 9:16 for Stories and Reels, and 16:9 for right-hand rail placements.
- Asset copy (text on the image) plus the brand or logo on the image. Social copy (the post text) assists the asset copy.
- Headlines and descriptions show only on Facebook placements. Write the social copy and the asset copy to stand alone on Instagram.
- Dynamic creative: 5 primary text variations and 5 headlines. Use the same 5 across a run of ads, so a breakdown shows which copy converted.
- CTA button: "Learn more" by default, "Shop now" for DTC. Test it.
- Video: the first 3 seconds (the hook) matter most. Put the product front and center and show what it does. For SaaS: show 1 surprising thing the product can do.
- UGC: content that a customer made. UGC must come from a real customer, with that person's consent. Run `ad-law-canada` step 3, item 4 on each UGC ad. The source does not recommend the influencer route.
- Research competitors in the FB Ads Library. Not everything there works.

## Custom columns

E-commerce names. Map them to the business funnel.

- Amount spent, purchase conversion value, purchase ROAS, purchases (or the primary objective: leads, free trials, registrations), cost per purchase.
- Add to cart, cost per add to cart, landing page conversion rate (purchases ÷ landing page views).
- Outbound CTR (not plain CTR; it counts only clicks that leave Meta), landing page views, cost per landing page view, content views, cost per content view.
- Impressions, reach, frequency, CPM, reactions, comments, shares.
- Thumbstop = 3-second video plays ÷ impressions. Over 30% is good.
- 3-second video plays, cost per 3-second video play, hold rate = ThruPlays ÷ 3-second video plays.

How to read them:

- The question is always: is this ad better than the account average?
- CPM, CTR, CPC, and CPLPV measure the ad and the audience. Cost per view content, cost per add to cart, and cost per purchase also measure the landing page and the checkout (or onboarding).
- Compare Meta with Google Analytics and the backend. Read ROAS and MER. Accept a small, known delta. A gigantic delta means the ad tech or the platforms are broken.
- Breakdowns (top right of Ads Manager) sort results by age, gender, location, and country. They do not show job titles.

## LinkedIn

- Cost: LinkedIn CPMs are very high, about $40 for 800 people. A typical case: $250 per lead on LinkedIn, $25 per lead on Meta. An audience cannot be exported from LinkedIn.
- Lead Generation Ads (a strong LinkedIn ad type for B2B leads): the form is pre-filled with the email, the person submits, often for a resource (a PDF or a report). The advertiser sees the industry, the person, and the employer. It captures people with high intent.
- InMail campaigns: pay to message people you are not connected with. Use them only with a specific offer: an event invitation, an important resource, or an offer.
- Company page boosts: company pages get very low organic reach. Boost the page post from time to time for an event, an offer, a sign-up, or a download.
- Thought leadership ads: sponsor a post from a person's account through the company page ("post by" the person, "promoted by" the company). Promote posts that solve a client problem, not behind-the-scenes posts. Use no call to action, except that it is easy to know how to reach out. Target the exact job title, the exact city, and the exact company size, for about $20 a day.
