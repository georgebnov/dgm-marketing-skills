---
name: ad-law-canada
description: Canadian ad law risk review before marketing ships. Covers ad copy, landing pages, email and SMS (CASL consent, unsubscribe), contests and giveaways, sale prices and fees, green claims, health claims, testimonials, influencers, AI images. Use when material for Canada must pass a legal risk check.
---

# Canadian Advertising Law Review

This skill returns a risk review of marketing material for Canada, B2C and B2B. The review lists each claim or practice, the rule it touches, the risk level, and the fix or the proof that must exist before publishing. It does not write new copy, and it does not replace a lawyer.

**Not legal advice.** The rules in this skill come from notes on an advertising law session (given by a Canadian advertising lawyer) in the TMU Digital Growth Marketing program. The skill gives information, not legal advice. Each business must get legal advice for its own circumstances. Put the "NOT LEGAL ADVICE" line at the top of every review. Send every High item to a lawyer before publishing. This area of law moves fast and can change after the notes were made.

Text marked **(skill choice)** is the procedure of this skill, not a rule from the source.

## Terms

- **Representation**: a statement to the public about your product. Every ad is a representation. Copy, images, prices, an email, a post, and a testimonial are all representations.
- **Claim**: a representation that describes the product, for example "this is a sale", "there is a discount", or "this product is better for the environment".
- **General impression**: what the ad says to a credulous and technically inexperienced consumer: an ordinary person in a rush, who does not read closely. The literal words are not the test.
- **Substantiation**: the proof that supports a claim. The legal standard is adequate and proper testing, done before you publish.
- **Material**: able to change a decision to buy. The statutes prohibit representations that are false or misleading in a material respect. Price is always material.
  - **(skill choice)** For a free product or a waitlist, the decision is the sign-up, the download, or the gift of personal data. A claim is material when it can change that decision. Examples: the headline benefit, a user or waitlist count, "free", a launch date.
  - A minor detail in a feature list ("two taps to share") is not material.
- **Competition Act**: the federal misleading advertising statute, B2B included. **Consumer Protection Acts**: provincial statutes, B2C only, with the right to rescind (cancel the purchase).

## Inputs

Collect these before step 1:

1. **The material**: the full text, the images, the fine print, and every link target. For a landing page, also the checkout flow and every form.
2. **The material type**: ad, landing page, email, SMS, signup form, contest, product page, app store page, or social post. One review can cover several types.
3. **The audience**: B2C, B2B, or both.
4. **The reach** **(skill choice)**: where the business targets the material, not every place where a public page can load. Decide it from 3 facts:
   - who it targets: the stated market, the app store countries, the service area,
   - its language,
   - where the business promotes it: ad geo-targeting, email lists, posts.

   Quebec is "yes" when the material targets all of Canada or Quebec. The EU, California, or New York is "yes" only when the targets or the promotion name them. If a fact is unknown, write "reach: unknown" and list the Quebec or EU check under "Open questions".
5. **The product category**: is it food, a cosmetic, a drug, a natural health product, a cleaner, or a plastic package? Is there a co-promotion partner?
6. **The proof that exists**: test reports, 6 months of price history, consent records, contest rules, product authorizations, the source of each count.
7. **How the material was made**: was AI used for text or images?

If an input is missing, ask the user. If you cannot ask (for example, as a subagent), continue, and write "assumed: <what you assumed>" on each finding that depends on it. For missing proof, do not guess.

## Result scale

Give each check 1 result:

- **pass**: the material meets the rule, and the proof exists.
- **partial**: the material meets some parts of the rule. Example: the signup form shows the business name but no mailing address.
- **fail**: the material breaks the rule. Also a fail: proof that does not support the general impression, or proof made after publishing.
- **not checked**: you cannot see the proof (for example, no price history). The finding names the proof that must exist.

A best practice item (the source calls it "best practice" or "advises") is never a fail. When it is missing, give it the result "partial" at Low.

## Risk levels

| Level | Meaning | Rules at this level | Why |
|---|---|---|---|
| **High** | Lawyer before publishing | Contests without a skill test or with a forced purchase. Drip pricing. A "regular", "was", or "compare at" price without the time and good faith proof. A green claim without testing. A health claim outside the product authorization, or an unclear product category. Email or SMS without express consent or a recorded exception. A material claim without proof. An AI image that shows the product falsely. | Criminal Code (contests can be an illegal lottery). Competition Act: a penalty up to the greater of $10 million ($15 million for a repeat order) and 3 times the benefit, or 3% of annual worldwide gross revenue when the benefit cannot be determined. Pricing and green claims are enforcement priorities. Consumer class actions. |
| **Medium** | Fix before publishing | Mini rules missing details. A message without the sender name, contact information, or a valid unsubscribe function. No French for Quebec. Critical terms hidden in long terms and conditions. Missing cookie consent. AI output that misrepresents people or is not accessible. A breach of platform terms. Use of a competitor's IP or disparagement. **(skill choice)** A claim that is not material, without proof. | CRTC (CASL). Competition Act (mini rules). Courts do not enforce buried terms. Privacy Commissioners. Competitor actions. Platform contracts. The prohibition is for material claims. |
| **Low** | Recommended | Best practice items: a privacy policy link in the consent request, long contest rules, a watch on EU or US AI disclosure rules for material that stays in Canada. | No penalty in the source. They lower risk. |
| **Not covered: lawyer** **(skill choice)** | Lawyer before publishing | A practice without a rule in this skill that touches a price, a contest, a health or green claim, consent to messages, personal data, or a material claim. | The source gave no rule, and the area carries the High remedies. |
| **Not covered: open question** **(skill choice)** | List it, ask the user or a lawyer | Every other practice without a rule in this skill. Example: a demo card that shows a real business name. | The source gave no rule. Do not invent one. |

A finding takes the level of its rule. A "partial" or "not checked" result keeps the same level as a "fail". When 1 finding touches 2 rules, give it the higher level.

## Steps

### Step 1: general impression and substantiation (every review)

Run this step first, for every material type. It is the most important step of the review.

1. Write the general impression in 1 sentence. Read the material as a credulous, inexperienced consumer in a rush, with no technical background. Include the images and the headline.
2. List every claim in the general impression. Include claims that images, names, counts, or a layout make, not only the words. Give each claim 1 kind: price, free, performance, green, health, contest, comparative, endorsement, or other. Mark each claim material or not material (see Terms).
3. For each claim, ask: does adequate and proper testing exist, and was it done before publishing? A claim that is true is still a problem if the proof did not exist before publishing. Give the result from the result scale:
   - no proof supplied: "not checked",
   - proof made after publishing, or proof that does not support the general impression: "fail".
   
   The level is High for a material claim and Medium for a claim that is not material.
4. Check the claims against each other. **(skill choice)** 2 different numbers for the same thing (for example 2 waitlist counts) make the general impression false for at least 1 of them. Give the result "fail".
5. Check the fine print. Critical conditions must be up front, in clear, basic words, not in long, complex legal text. Courts do not enforce critical information that is buried in long terms and conditions.

Done when: the general impression is 1 sentence, and each claim has a kind, a materiality mark, a result, and a level.

### Step 2: route each claim and practice

Read each reference file whose condition matches. Run every check in it. Each file states the winner when 2 of its rules conflict.

| Condition | Read |
|---|---|
| A price, a sale, "was", "regular", "compare at", a fee, a checkout, "free", a planned price, or a paid add-on | `references/pricing.md` |
| An email, an SMS, a signup form, a waitlist form, or a lead-gen form | `references/casl.md` |
| Any prize, giveaway, draw, sweepstakes, or "chance to win" | `references/contests.md` |
| A claim about the environment, emissions, net zero, "natural", recyclable, or compostable | `references/green-claims.md` |
| Food, a cosmetic, a drug, a natural health product, a cleaner, a personal care product, or a health benefit | `references/health-claims.md` |
| AI-made text or images, personal data collection, cookies, or automated decisions about people | `references/ai-and-privacy.md` |
| A gift card, a loyalty program, or telemarketing | `references/programs.md` |

Read `references/enforcement.md` at step 5, to write the "rule" line of each finding.

Done when: every claim from step 1 has a reference file or a line in step 3.

### Step 3: checks for every material

Run these checks on every review. Each line names its level.

1. **Quebec (Medium).** If the reach includes Quebec, local language laws usually require French. The rules on the prominence of French are very prescriptive and change with the medium. Flag each medium for a check.
2. **Platform terms (Medium).** The terms and conditions of a third-party platform govern the use of that platform. Meta, Google, ad tech, and programmatic platforms usually make the advertiser responsible for the ad content. Name the platform and the guideline area that the material touches. **(skill choice)** App stores (the Apple App Store, Google Play) are third-party platforms, so this check applies. The source gave no rule on store badges or store terms: list them as "Not covered: open question".
3. **Comparative claims.** Competitors can enforce their rights when comparative advertising uses their IP (for example their trademarks or logos) or disparages them. That use is Medium. A comparative claim ("faster than X") is a claim: step 1 gives its proof result and level. A competitor name in plain text, with no claim and no logo, is "Not covered: open question".
4. **Testimonials and influencer posts.** A testimonial or an influencer post is a representation. Run step 1 on it: the general impression and the proof of each claim in it. Check the platform terms. The source gives no rule on endorsement disclosure: "Not covered: lawyer" when the post makes a material claim, else "Not covered: open question".
5. **Real third-party businesses in demo or mock content.** The source gave no rule. **(skill choice)** Run step 1: if the general impression says that the business is a customer, a partner, or an endorser, that is an endorsement claim that needs proof. The use of the name itself is "Not covered: open question".
6. **Self-regulation (Low, or Medium for a missing broadcast preclearance).** Name the Ad Standards code or the industry code that applies. The details are in `references/enforcement.md`.

### Step 4: rule conflicts

When 2 rules point different ways, apply this table.

| Conflict | Winner |
|---|---|
| A true, substantiated health claim that Canada did not authorize for that ingredient | The authorization. Remove the claim. |
| An exception to CASL consent applies | The exception removes only the consent requirement. The unsubscribe function and the message content rules still apply. |
| A claim is true, but the general impression says more than the proof shows | The general impression. Substantiate the general impression, not the literal words. |
| The AI made the false image or claim | The advertiser is liable. "The AI made it" is not a legal defense. |
| The business is B2B only | The Competition Act still applies. The Consumer Protection Acts and consumer rescission do not apply. |

### Step 5: rank and write

1. Sort the findings: High, then Not covered: lawyer, then Medium, then Low. Inside 1 level, put the most visible claim first (headline before fine print). Put "Not covered: open question" items in "Open questions", not in the numbered list.
2. Write each fix as an exact change. Write `Remove "Was $20" until the price history proves it` or `Add "You can unsubscribe at any time." under the checkbox`. Do not write "review the wording".
3. When the fix is proof, name the exact record: "6 months of daily price history for SKU X", "a reproducible test report under consumer-use conditions, dated before publishing".
4. Set the verdict **(skill choice)**:
   - **lawyer first**: 1 or more High or "Not covered: lawyer" findings.
   - **fix first**: 1 or more Medium findings, and no High or "Not covered: lawyer".
   - **publish**: only Low findings and open questions, or none.

## Output

Read `references/worked-example.md` before you write the review. Match its fields.

```
NOT LEGAL ADVICE. Information from course notes on Canadian advertising law. High and "Not covered: lawyer" items go to a lawyer before publishing.

Material: <name or URL> · type: <types> · audience: <B2C | B2B | both> · reach: <provinces, Quebec yes/no/unknown, other> · AI used: <yes/no/unknown>
General impression: "<1 sentence>"
Verdict: <lawyer first | fix first | publish>: <1 line>

1. [<High | Not covered: lawyer | Medium | Low>] "<claim or practice, quoted>"
   kind: <price | free | performance | green | health | contest | comparative | endorsement | other | practice> · <material | not material>
   rule: <law or regulator> · <test or requirement>
   result: <fail | partial | not checked>
   fix: <exact change> | proof: <record that must exist before publishing>
2. ...

Open questions: <each "Not covered: open question" item, with the question to ask>
Passed: <checks with result pass, separated by ·>
Assumed: <each assumption from a missing input>
```

The kind "practice" is a finding that is not a claim (a form, a fee flow). It has no materiality mark.

## Checks before done

- [ ] The "NOT LEGAL ADVICE" line is the first line of the review.
- [ ] Step 1 ran: the general impression is 1 sentence, and each claim has a kind, a materiality mark, a result, and a level.
- [ ] Every reference file whose condition matched was read, and every check in it has a result.
- [ ] Every finding has a level, a kind, a rule with the law or regulator name, a result, and a `fix:` or a `proof:`.
- [ ] Every "not checked" names the exact proof that must exist.
- [ ] No rule or number in the review comes from outside this skill. Practices without a rule are "Not covered: lawyer" or "Not covered: open question".
- [ ] The verdict follows step 5.4.
