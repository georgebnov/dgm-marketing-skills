# Method run rules

Read only the section for the method that step 5 chose. Each section ends with the fields that it fills in the brief.

## Customer interviews

Goal: gather evidence to support or refute the hypothesis. A full round takes about 1 to 2 weeks. Interviews give the fastest first answer.

Why interview: uncover new customer pains, strengthen evidence, build a bolder prototype, de-risk investments. You are not your customer. A team can know the solution so well that it does not see the problem.

### Setup checklist

1. Review the hypothesis.
2. Set 1 research topic. Example: "why do you choose this brand of protein powder over the one you use now?" One topic, not small talk.
3. Write the outline and the script. AI may draft them.
4. Recruit 5 to 8 participants.
5. Schedule the interviews.
6. Build rapport.
7. Find patterns.

### Script questions

Use these questions on the topic. Add follow-ups.

1. "Tell me about yourself and a normal day."
2. "What do you want to achieve?"
3. "What works for you now?"
4. "What gets in the way?"
5. "Tell me more about that."

Also ask about the alternative that the customer uses today, and why they like or dislike it. A complaint about the alternative (for example "it tastes bad") can become the positioning of the new product (the one that tastes good).

### Recruiting

1. Ask the person who runs the ads for a small square ad on Facebook or Instagram.
2. Show it to 5% or 10% of the audience only.
3. Use humble copy, for example: "We want 5 to 8 people to tell us what they want from [product]. We are here to learn."
4. Link the ad to a Calendly page (a self-booking calendar).
5. Stop the ad after 5 to 10 bookings.

Do not recruit from paid panels such as usertesting.com or paid survey communities. Recruit people who are actually interested in the product. If the ad targeting is correct, the people are already in your funnel. If the user runs no ads, recruit from current customers or from the waitlist or email list. Send the same humble text with the Calendly link, and stop after 5 to 10 bookings. (Skill's choice: the source named only the ad.) B2B is a strong case for interviews: always interview B2B customers.

### Running the interview

- A human runs the interview. AI never interviews the customer.
- 1 hour is the maximum. After that, answers get rushed.
- About 30 minutes is the core of the interview. Spend the rest on rapport, clarifying questions, and thanks.
- If there is an incentive (for example a $20 gift card, or use of the product), explain it at the end.

### Analysis

1. Read the transcripts yourself first.
2. Then give the transcripts to an AI with the prompt "what patterns are we missing?" A meeting-notes tool plus an AI model works for this.
3. Pull these patterns: goals and motivations, pains and frustrations, and attempts at a solution. Also pull the competitors or alternatives named, the specific words used, and where they looked for a solution.
4. Record the surprises, for example "we are not as cheap as we thought."
5. Record the customer's words for the problem: the everyday words, not the clinical or technical term.

Evidence level: say. The result shows that a problem exists and where to look. It feeds a behaviour test. Interviews often lead to more interviews.

Brief fields: method "interviews", format "interviews", sample target "5 to 8", traffic "ad to 5% to 10% of the audience" or "current customers", decision metric "count of interviews that name <pattern>" (the user sets the threshold). Never rely on a count of interviews to launch. The count decides only whether a problem exists and what to test next. It never fires a launch row (see the say-level rule in `read-result.md`). Constraint: a metric and a stop number that the user sets.

Examples of what interviews find:

- A premium full-service offer can fail on its landing page because buyers need a thing the business does not offer (for example a phone line). If every interview asks for that thing, no page change can fix the result.
- Customers can compare the product with a different category than the team expects. That comparison can support a higher price than the first plan.

## Compound experiment

Use for B2B, or when traffic cannot support a proper A/B test.

1. Interview the business owners. Ask what they see in the market and what feature set and price set they demand. Ask which objections and questions you do not know yet.
2. Put those answers at the front and center of the page.
3. Combine 4 or 5 themed changes into 1 bold variant, for example 1 homepage.
4. Measure whether conversion goes up at the compound level.
5. Separate the parts in later tests.

A big B2B example: move from sales-led ("sign up now for a demo") to product-led or a hybrid. Ask: what MVP can you run now to see if customers like to find their own way in?

Brief fields: method "compound", variant lists the 4 or 5 changes and their theme.

## A/B split test

How it works:

1. Put 2 offers in the market (2 landing pages, 2 products, or subscription versus single purchase).
2. Send each offer to a segment of the audience.
3. Count buyers over the total sample for each offer. That is the conversion rate.
4. Average across the full run. A first-day lead can reverse by the end of the run, so a stop on day 1 can pick the wrong winner. `read-result.md` has a worked illustration.

Traffic floors: large software companies run tests for 2 to 3 weeks with about 100,000 visits per variant. Tens of thousands of visits per month is probably the absolute minimum. With that much traffic only, run the biggest, boldest, most evidence-informed test. Do not test small wording swaps such as "click now" versus "buy now" versus "shop now".

Sequence from the top. Test the most visible component first, then move down. Fix the top step until it gives enough volume.

- Ad components, in order: 1. visual hook, 2. offer, 3. CTA, 4. headline, 5. primary text.
- Email components: 1. subject and preheader, 2. format, 3. sender name, 4. offer and CTA, 5. layout, 6. drip frequency, 7. drip sequence, 8. list segments, 9. body copy.
- Example: a brand runs 6 ads with the same copy and different visuals. Earlier tests fixed the message. Now it changes only the image.

Brief fields: format "split URL" or the tool's format, sample target per variant from the calculator, runtime in weeks.

## False door

Use to find early demand for a thing that does not exist yet. It tests your ability to offer the thing, not the product. It needs a solid setup, a clean delivery, and a quick reveal.

### Setup

1. Put the offer in context: where people normally buy that kind of thing. A new product goes in the catalogue. A new offer goes where offers live, often the homepage.
   - No purchase flow yet (pre-launch, free product): put the offer where offers live on the site. That is the homepage hero, or a pricing section if the site has one. In an app, put it where the feature would live. (Skill's choice for the pricing section and the in-app spot. The source named the homepage.)
2. Do not use a survey pop-up ("rate this offer out of 10"). A survey does not get the same behaviour as a real purchase flow.
3. Always ask for contact info (name and email).
4. Plan the traffic. You must drive people to it, and that can be hard.
5. Target 50 to 100 results. The offer is not optimized. That is enough.
6. Estimate the runtime (skill convention): weeks = target results ÷ (visits per week × expected click rate). The user gives the click rate, or it gets `[NEEDS FROM USER: expected click rate]`. Arithmetic example only, not a benchmark: 50 ÷ (350 × 0.02) ≈ 7 weeks.
7. If the runtime is longer than the deadline, pick 1 fix and name it in the brief (skill convention). Drive more traffic to the offer. Or make the offer more visible in context. Or switch to a method that fits the traffic (step 5). Never lower the target or change the tree to fit the deadline.

### Pre-launch: an in-app false door at launch

A pre-launch product can test a planned paid add-on without building it (skill's choice). Ship the launch build with a button or an entry for the add-on, in the place where it would live. A tap opens the reveal and the waitlist. The add-on is not built before launch.

- Score Effort on the false door work only: the button, the reveal screen, the consent, and the event that counts taps. Do not score the work to build the add-on. (Skill convention.)
- The traffic is the launch users, so the runtime starts at launch.
- Run the free-promise check. The button must not sell as paid something that the listing or the site calls free. For Canada, use the `ad-law-canada` pricing.md "Free" claims rules as the check.

### Evidence level

A false door reaches do level: a person acts and gives contact info, but no wallet comes out. It is the step before purchase, not a purchase. The source named no pre-sale method. For purchase level, sell the real offer: a concierge test that people pay for, or an MVP, the smallest thing that will sell. (Skill's reading.)

### Reveal

1. Show the reveal at once after the attempt. Example text: "Thanks for your interest. This product is not ready yet. With your permission, we would like to add you to our waitlist."
2. Get permission before you add people to the waitlist. In Canada, permission is required. For Canada, run `ad-law-canada` on the false-door offer and the waitlist form. Copy its consent wording into the brief. For another market, check the rule, and mark it `[NEEDS FROM USER: consent rule for <market>]` if unknown.
3. Tell people that they were part of an experiment. The false door is overt.
4. Give real value. Options: early access, a future discount (for example 15% off), use of an alternative product, an extended free trial.

The reveal can upset people. The frustration can end the relationship and lose sales. A software company can give its top product free in a reveal, at little cost. For a physical product that may not work: pick a discount or early access.

### Concierge test

In a concierge test, you do fulfil the offer, by hand, before it is built. A false door offer is never available. Pick the concierge test when you can deliver by hand and you need purchase-level evidence. Example: fulfil the first 100 orders of a planned service by hand.

Brief fields: method "false door" or "concierge", and section 5b (placement, reveal text, consent, compensation). Also the traffic source, sample target "50 to 100", runtime math, lift/MDE `not applicable (count-based, no control)`. Constraint: a metric and a stop number that the user sets. The reveal can upset people and lose sales.
