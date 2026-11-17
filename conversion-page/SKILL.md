---
name: conversion-page
description: 'Audit or write a page whose job is to convert: a homepage, topic page, landing page, or e-commerce product page. Covers headline, hero image, CTA, form, trust, proof, product images and names. Use for "audit my landing page", "why does this page not convert", "write landing page copy", "product page", "homepage copy".'
---

# Conversion Page

This skill audits or writes a page that must get a click: a sign-up, an add to cart, a booked demo, a sample request. The audit mode returns a ranked list of concrete fixes, each with evidence from the page. The write mode returns a page specification with copy, built only from facts that the user supplies. It does not cover Google ranking, ad copy, or email sequences. For ranking, `helpful-content` owns content and E-E-A-T.

## Terms

- **Conversion**: the 1 action that the page exists to get (for example "appointment booked", "add to cart").
- **CTA** (call to action): a button or link that asks the visitor to act. The **primary CTA** is the button for the conversion.
- **Fold**: the bottom edge of the first screen, before the visitor scrolls. The first screen gets smaller on phones. Check it at phone width.
- **Sticky CTA**: a CTA that stays pinned on the screen when the visitor scrolls, ideally in the top right corner.
- **Hero**: the large main image or video at the top of the page.
- **Floor**: 1 content section below the fold. Each extra floor gives less return.
- **Squint test**: sit back, squint at the page, and say what the business does. On a product thumbnail, this is the **thumbnail test**: is the image clear on a phone?
- **E-E-A-T**: Experience, Expertise, Authoritativeness, Trustworthiness. Google, AI tools, and visitors judge a page by these signals.
- **The 5 drivers**: the 5 influences that control every purchase, in this order: **Trust → Suitability → Usability → Perceived costs → Fulfillment**. Clear a lower driver before you build on the next one. Emotion starts the purchase. Logic justifies it after.
- **Claim → Power → Proof**: the benefit structure of a page. The claim is at the top. Power (why you can do it and the big competitors cannot) is under it. Proof (reviews, numbers, logos, press, case studies, awards) is at the bottom.

## Inputs

Collect these before step 1. Both modes need the first 4.

1. **Mode**: audit or write.
2. **The page**: a URL or a file (audit). The planned URL path (write).
3. **The conversion**: the 1 real event that counts. Count the business event (for example "Appointment Booked"), not clicks or views.
4. **The traffic source**: organic, site links, or a campaign. For a campaign, get the ad copy. The heading and supporting copy must match it.
5. **The user group**: who the page is for, in the customer's own words. One page serves 1 user group.
6. **Write mode only**: the facts in step W1.

If an input is missing, ask the user. If you cannot ask (for example, you run as a subagent), return a line that starts with `BLOCKED:` and list each missing input. In audit mode, you may continue without inputs 3 to 5. Mark each finding that depends on them "assumed: <what you assumed>".

## Steps

### Step 1 (both modes): classify the page

Give the page exactly 1 type. Use this table. Several rules change with the type.

| Type | Funnel stage | Job | CTAs | KPI |
|---|---|---|---|---|
| Homepage (a hub that routes visitors) | Awareness, consideration | Show the brand offer, show E-E-A-T, send each visitor to the right part of the site | Many: Products, Services, Plans, About Us, FAQs, Testimonials, plus 1 point of conversion | Bounce rate, engagement, clicks |
| Topic page | Consideration, intent | Inform, educate, address problems and barriers, show specific facts | A middle step (download research, email sign-up, book a demo) and the full conversion. No dead ends. | Engagement, conversion rate |
| Landing page (the close) | Intent, purchase | Get 1 specific click, nothing else. About 4 or 5 elements. | 1 CTA type (Sign-Up, Add To Cart, Contact-Us), repeated. Not a middle step. | Conversion rate |
| Product page | Purchase | Make the product easy to find, easy to buy, and relevant | Add to cart, always visible and clickable | Conversion rate, cart abandonment rate |

**A page with 2 jobs.** Some pages hold 2 types. Example: a pre-launch homepage that is also the only conversion page (a waitlist). Classify it as `homepage + landing page`. Judge the conversion parts (heading, supporting copy, hero, primary CTA, form) by the landing page rules. Judge the navigation parts (nav, links to other pages) by the homepage rules. On such a page, the waitlist sign-up is the conversion. The landing page rule against a middle step (an email sign-up) applies only when a bigger conversion exists.

Then check the page count rule. Make 1 landing page for each goal, each user group, and each campaign. If 1 page tries to convert 2 goals, 2 user groups (for example residential and commercial), or 2 campaign messages, the first finding is: split it. Each offer gets its own page and URL.

**Homepage exemption.** The navigation role of a homepage sends different user groups to different pages. Those links are paths, not competing conversions. Thus the split rule and the "1 primary CTA type" check count only the CTAs that ask for the conversion. They do not count the navigation links.

Done when: the page has 1 type (or `homepage + landing page`), 1 conversion, and 1 user group for the conversion, or the split is the first finding.

### Audit mode

**A1. Capture the page.** For a URL, capture 3 things: the full page text, a screenshot at desktop width, and a screenshot at phone width (also shrink the window to half a screen). Use the browser tool that the session allows. For a URL with no browser, fetch the HTML, and read the text and the source order. Mark the visual items (fold position, order on a phone, colors, look of the CTA) "not measured", unless the CSS states them (for example a media query that changes the order). For a file, read the source, and mark the visual items and the load time "not measured".

To measure speed, run PageSpeed Insights (Google's free page test) on the URL, with the mobile setting. The "Technical" section of `references/checklists.md` says which values to report. If the user has heatmap or journey data (Hotjar, Content Square, a Sankey diagram from Google Analytics), use it as evidence: where attention drops, where people bounce or click back.

**A2. Check every element against the checklist of its page type.** Read `references/checklists.md` now. Run every item of the section for this page type, plus the "Every page" section. For each item, record 1 mark, with evidence:

- **pass**: the page meets the item fully.
- **fail**: the page does not meet the item.
- **partial**: the page meets part of the item. Say which part fails. Rank the failed part as a fail.
- **not measured**: the captured material cannot show it. Say why.

An item marked "(ideally)" in the checklist is not a fail when it is missing. Record it as a test idea (tier 7).

Evidence is 1 of these:

- a quote of the exact page text: `"Smart Inventory Platform"`
- a count: "10 form fields", "3 CTA texts: Get a demo, Book a demo, Request a demo"
- a position: "primary CTA is 1.4 screens below the fold at 390 px width"
- a look: "top CTA is green, bottom CTA is black"
- a measurement: "page load 2.8 s"

Done when: every checklist item for the type has a line.

**A3. Check the copy against the drivers and Claim → Power → Proof.**

1. Find the claim. If the heading answers "what is it?" or "how does it work?", it is a feature, not a claim. A heading that only names the product says nothing about why it is good. A curiosity heading (a tease that names neither the product nor a benefit) also fails. The heading must tell what you offer and your main benefit, and the page must pass the squint test. Clarity beats cleverness.
2. Look for a buried claim. The best claim is often already on the site, in the body copy or near the bottom. Quote it, and propose it as the new heading.
3. Check the order. Proof at the top with no claim above it is a finding. Proof tells the visitor that you can do the thing. It does not tell them why the thing matters to them.
4. Check each driver, lowest first:
   - **Trust**: the "Trust" section of `references/checklists.md` (a way to reach the business, facts that agree), plus a conventional layout and no jargon. Borrowed trust: partner or customer logos, ratings, press.
   - **Suitability**: the problem in the customer's words, not the category name (for example "my back hurts when I sit", not the clinical term). An answer to "will it fit?" and "will it connect?" before the CTA.
   - **Usability**: 1 clear next step. Explicit inclusions: say what comes in the box or the plan, and what the buyer must supply.
   - **Perceived costs**: the effort and time around the product. A time-to-success statement (how long until the result), not a time-to-start statement (how long until the setup is done). A form longer than about 5 steps is split into parts, with the reward shown.
   - **Fulfillment**: 1 element that lets the buyer see themselves with the result (a trial, a sample, a demo video, a before-and-after). Urgency, if any, comes from the customer's real looming problem (for example a storm in the forecast for a roofing offer), not from fake scarcity.
5. Check vague claims. "We can help you do this faster" is generic. "We cut setup time by 30%" or "save up to 15%" is specific. "The future of ___" is generic.

Done when: the claim, the order, and each of the 5 drivers have a line with evidence.

**A4. Rank the findings** in this order. Each section of `references/checklists.md` names its tier. Inside 1 tier, put the most visible finding first.

1. **Wrong job**: the page serves several goals, user groups, or campaigns, or the page type does not fit the traffic (a paid campaign that lands on the homepage).
2. **Speed**: slow load. Speed comes before every other element. A heavy hero image or video that slows the page is not worth it.
3. **No path to the conversion**: no primary CTA above the fold, no sticky CTA, a CTA that cannot be found on a phone, a form with non-necessary fields.
4. **Above-the-fold copy and hero**: heading, supporting copy, hero image. The top section is the most critical part of the page.
5. **Driver gaps**, in driver order: trust, suitability, usability, perceived costs, fulfillment. Contradictory facts on the page (2 different numbers for the same thing) are a trust gap.
6. **Lower floors**: benefits, how it works, proof sections, FAQs, design consistency, URL path.
7. **Test ideas**: changes that are not errors, to test with a tool such as VWO.

Done when: every fail from A2 and A3 has 1 rank.

**A5. Write each fix.** A fix names the exact change. Write `Change the heading to "Count your stock in 10 minutes, not 2 hours."` or `Cut the form to name, email, and phone`. Do not write "make the heading more compelling". When the fix needs a fact that you do not have (a number, a review count), write `[NEEDS FROM USER: ...]`.

### Write mode

Read `references/write-mode.md` now. It holds the full question list, the claim structures, and the landing page order.

**W1. Ask for the inputs that only the user has.** Ask all the W1 questions of `references/write-mode.md` in 1 message. If the user has no proof, say in the output that the page has no proof floor yet.

**W2. Write the claim.** Draft 6 claims, 1 per claim structure. Keep only claims that the user can stand behind. A claim with a number needs that number from W1. Clarity beats cleverness. Write the benefit, not the feature.

**W3. Build the page** in the order of its type: the landing page order in `references/write-mode.md`, or the section list of the type in `references/checklists.md`.

**W4. Mark every gap.** Each place that needs a fact you do not have gets `[PROOF NEEDED: <what>]`. Never write a number, a review, a testimonial, a logo, an award, or a case study that the user did not give.

**W5. Write the test plan.** About 9 heading variants, and CTA variants that change 1 variable each (the "CTA cheat sheet" in `references/checklists.md`). Give each test idea to `growth-experiment`. It sets the method, the sample, and the stop rule. Judge every test on the conversion, not on clicks.

## Output

Next review: the homepage rhythm (once a quarter) assumes that the site has other conversion pages. A page that is the only conversion point (for example `homepage + landing page`) gets the landing page rhythm.

**Audit mode:**

```
Page: <URL or file> · type: <type> · conversion: <event> · user group: <group>
Verdict: <1 line: the single change that matters most>

1. [<tier number 1 to 7 from A4>] <element>: <problem>
   evidence: "<quote>" | <count, position, look, or measurement>
   fix: <exact change>
2. ...

Keep: <elements that pass and must stay, each with a short reason>
Not measured: <items, and why>
Tests to run: <test ideas from tier 7, each with its metric>
Next review: <landing page: weekly or biweekly · homepage: once a quarter · topic page: once a year>
```

**Write mode:**

```
Page: <URL path> · type: <type> · conversion: <event> · user group: <group> · traffic: <source>

Above the fold
- Heading: <text>
- Supporting copy: <text>
- Hero brief: <subject, person and eye line, brand cue, size limit>
- Primary CTA: <text> · sticky: yes/no · nav: kept/stripped

Floors (in order)
1. <section name>: <copy>
   CTA: <text>
...

Form: <fields> · after submit: <text>
Gaps: <each [PROOF NEEDED] item>
Test plan: <9 heading variants> · <CTA variants> · metric: <conversion>
```

## Checks before done

- [ ] The page has 1 type (or `homepage + landing page`), 1 conversion, and 1 user group for the conversion, or the split is the first finding.
- [ ] Audit: every finding has evidence from the page (a quote, a count, a position, a look, or a measurement). No finding says "consider" or "improve" without the exact change.
- [ ] Audit: the findings follow the 7 tiers of A4. Items that you could not measure are in "Not measured", not guessed.
- [ ] Write: every number, review, logo, testimonial, and case study came from the user. Each gap has a `[PROOF NEEDED]` marker.
- [ ] The heading is a claim (what changes for the customer), not a description of the product or the mechanism.
- [ ] The page has 1 primary CTA type with 1 text and 1 color, above the fold and repeated lower. Secondary CTAs look secondary. Homepage navigation links do not count.
- [ ] For material that targets Canada, run `ad-law-canada` before it ships.
