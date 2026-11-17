---
name: growth-experiment
description: 'Design, run, and read a growth experiment, and return a filled experiment brief: what to test, the pre-agreed decision, hypothesis, evidence strength, method (customer interview, A/B test, false door, prototype), metrics, and result. Use for "experiment brief", "test idea", "hypothesis", "A/B test", "false door", "read this test result".'
---

# Growth Experiment

This skill turns an open business question into a filled experiment brief. Design mode writes the decision, the hypothesis, the graded evidence, the method, the metrics, and the run plan. It also writes a decision tree that the team agrees before any data. Read mode adds the result and the action that the tree gives. It does not write the page, the ad, or the email that the test uses (use `conversion-page` for a page).

## Terms

- **Experiment**: any decision activity that observes new evidence, where the team is willing and able to change its mind. Textbooks call it a small, controlled change. The size rule in step 6 wins over "small".
- **Hypothesis**: a guess that an observation and a measurement inform.
- **Evidence ladder**: the 3 levels of intent behind a piece of evidence. **Say** (survey, interview, "I much prefer this…") weighs 1 block. **Do** (mid-funnel action: signup, add to cart) weighs 2 blocks. **Purchase** (earned revenue: a completed purchase or a repurchase) weighs 5 blocks.
- **Decision metric**: the 1 metric that decides the test. **Constraint metric**: a metric with a stop number that ends the test before it causes damage. **Observation metric**: every other metric that you record.
- **MDE** (minimum detectable effect): the smallest effect that the test can detect. A bigger change reaches significance faster.
- **False door**: an offer for a thing that does not exist yet. When people try to buy, you reveal that it is not ready. **Concierge test**: you fulfil the offer by hand before you build it.

## Inputs

Collect these before step 1. Ask for all missing items in 1 message.

Required:

1. **The business**: what it sells, to whom, B2B or B2C, and how it sells (self-serve, sales-led, physical product, software).
2. **The open question**: the decision that the team argues about, or the goal that is stuck.
3. **Monthly traffic** on the surface to test (visits per month), or "unknown". Unknown traffic counts as below the A/B minimum in step 5.

Optional (continue without them, and mark each dependent field `assumed: <what you assumed>`):

4. Funnel stages with 1 baseline number each (from GA4, Mixpanel, or PostHog).
5. Evidence that exists: interviews, surveys, support tickets, past tests, historical data, third-party data.
6. Who must agree to the decision (leader, team), and the test owner.
7. The deadline for the decision, if any.
8. Read mode only: the result per variant (participants, conversions) and the brief written before the test, if one exists.

If a required input is missing, ask the user. If you cannot ask (for example, you run as a subagent), return a line that starts with `BLOCKED:` and list each missing input. Never invent a number, a quote, or a customer fact. Each gap in the brief gets `[NEEDS FROM USER: <what>]`.

## Steps

Design mode runs steps 1 to 9. Read mode runs step 10. If read mode has no brief from before the test, run steps 2 to 7 first from what the user gives, then step 10.

### 1. Choose what to test

If the user already names 1 funnel stage, its baseline, and 1 test surface, record them and go to step 2. Otherwise read `references/what-to-test.md` now and run it. It finds the weakest stage, and covers the cases with no baselines and no ad budget.

Done when: the brief names 1 funnel stage, its baseline (or `assumed`), and 1 test surface.

### 2. Write the decision and the 4 outcomes, before any data

1. Write the decision: "If X is true, we will do Y."
2. Write the decision tree. Each row gets a threshold on the decision metric (set in step 7) and an action:

| Outcome | Tree row | Action |
|---|---|---|
| Wins very big | Succeeds above | Launch it at once |
| Roughly correct | Succeeds within | Launch it in sequence, on the roadmap and the release schedule |
| Did not work | Fails within | Go back and revisit it |
| Failed badly | Fails below | Go back and try a different hypothesis |
| (none) | Inconclusive | Skill convention: treat as "did not work" and revisit with a bolder change |
| (none) | Constraint trip | Stop the test at once |

3. The user sets every threshold. Never fill a threshold yourself. A missing threshold is `[NEEDS FROM USER: threshold]`.
4. Record who agreed and when. The leaders, the test owner, and the teams agree in advance, so nobody argues about the result later. If nobody agreed yet, write `Agreed by: not agreed yet`.

Done when: the decision sentence exists, and all 6 rows have an action and a threshold or a marker.

### 3. Write the problem, the premise, and the hypothesis

1. Problem, from the customer's side: "I am <customer> trying to <job> but <obstacle> because I <cause>, which makes me feel <feeling>."
2. Premise: the belief about customers that the test checks (for example "Mobile shoppers need a delivery date before they commit to a large purchase").
3. Hypothesis, evidence first: "We know ___. We believe ___, and so we will ___ and observe ___." Always start from evidence.
4. Hypothesis, short form: "If we ___ then ___ as measured by ___." The "as measured by" part is the decision metric.
5. Test the hypothesis against 3 rules. It is measurable. It has a controlled element (a change that you own). The market can show the result. Example that passes: "If we add free returns, orders will rise by at least 8%, as measured by the checkout completion rate."
6. If the question is big, write 1 big hypothesis and split it into smaller ones. Many of the small ones fail. When one works, follow that thread with the next test. Score the small ones in step 8 and brief the top one.

Done when: both hypothesis forms exist and pass the 3 rules.

### 4. Grade the evidence

1. List each piece of evidence with its source: customer research, third-party data, early tests, MVPs and pilots, historical data, other experiments.
2. Give each piece 1 ladder level: say, do, or purchase.
   - Give each piece a target: "tested thing" or "adjacent". Evidence about the free product (installs, retention) is "adjacent" to a paid add-on. Only "tested thing" rows set the verdict. (Skill convention.)
   - The team's own text (an FAQ, a roadmap, a pitch, a plan) is not evidence. Evidence is observed data. Put team text under "Not evidence", and use it for the premise or the free-promise check.
3. Mark each piece "agrees" or "disagrees". Record both kinds.
4. Some cases have a fixed ranking: repurchase, add to cart, signups with a flat upgrade rate, returns, interview counts, and low-response surveys. For these, read `references/evidence.md` and apply it.
5. Write the evidence verdict: the highest agreeing level on the tested thing (or none), and the strongest piece that disagrees.

Done when: every piece has a level and a direction, and the verdict line exists.

### 5. Choose the method

Pick the row for what you must learn now. The brief has 1 main method. It may add an interview pre-step:

| Situation | Method |
|---|---|
| You do not understand the problem, the customer's words, or the real competitor | Customer interviews (5 to 8) |
| B2B, or traffic under tens of thousands of visits per month, and you want to test a page | Compound experiment: 4 or 5 themed changes in 1 bold variant |
| You must measure demand for a thing that does not exist yet | False door in the real purchase flow (or a concierge test if you can fulfil by hand) |
| Tens of thousands of visits per month or more, and a bold variant | A/B split test |

Read the section for the chosen method in `references/methods.md` now. It holds the run rules: recruiting, the interview script, A/B sequencing, and the false door reveal.

Conflict rules:

- When the interview row and a behaviour row both fit, use the pattern "main method + interview pre-step". The behaviour test is the main method. Run 5 to 8 interviews first (about 1 to 2 weeks) to fix the problem, the words, and the offer. Interviews give the fastest first answer.
- Traffic wins over preference. If the user wants an A/B test with traffic below tens of thousands of visits per month, choose a compound experiment or interviews. Say why in the brief.
- Interviews find the problem and the customer's words. They never fire the "succeeds" rows alone. A behaviour test (do or purchase level) decides the solution.
- Pre-launch with no traffic: a false door needs traffic that you drive to it. Plan the traffic source in the run plan.
- A false door reaches do level, not purchase level. Its placement, the pre-launch in-app variant, and the purchase-level options are in `references/methods.md`.

Prototype: pick the fidelity on the ladder sketch → wireframe → mockup → interactive prototype. Use the low end for interviews and reviews, so people talk about structure, language, and offer, not colour. Use the high end for a quantitative test. The surface is an ad, an email, a landing page, or an app feature. A rough prototype is often the best one.

Done when: the brief names 1 main method and its pre-step (interviews or `none`). It also names the table row, the evidence level reached, and the prototype fidelity and surface.

### 6. Make the change bold

1. Make the variant differ a lot from the control. Do not test button colors or a 1 or 2 character change to a title. Test big, bold changes. This rule wins over the textbook "small, controlled change".
2. Inside the chosen surface, test the most visible element first. In ads and email, test the visuals first. In email, get opens first. With no opens, the email gives no evidence.

Done when: the variant names a change that a visitor sees at once. It is the top element of the surface, or the top element is already fixed.

### 7. Assign the metrics and size the test

1. Goal metric: the company metric. It has a quantity or rate, a quality of customer, an action, and a time component.
2. Input metric: the number that the team moves every day.
3. Decision metric: exactly 1. Pivot only on it.
4. Lift or MDE: the user sets it. A count-based test with no control (false door, interviews) gets `not applicable (count-based, no control)`.
5. Constraint metrics: each with a stop number. Examples: refunds above 5% of orders, support tickets up more than 20%.
6. Observation metrics: everything else (for example cart abandonment, revenue per visitor, clicks on the new element).
7. Sample size:
   - A/B test: run an A/B sample size calculator with the baseline rate, the MDE, and the traffic. Record the visits per variant and the runtime in weeks. With no calculator, write `sample size: not measured`, and check against the traffic floors in `references/methods.md`.
   - Interviews: 5 to 8 people on 1 topic. You hear most problems by about 8. Going to 10 is fine.
   - False door: 50 to 100 results. Estimate the runtime with the formula in the false door section of `references/methods.md`. If it is longer than the deadline, apply the fix rule there.
8. Stop rule: run to the planned sample. Do not stop on a bad first day. One bad day is noise.

Done when: the brief has 1 decision metric, 1 or more constraints (stop number or marker), and a sample target or `not measured`.

### 8. Score the 4E rank

Always score the brief. Order candidates only when there are 2 or more. Score each candidate 1 to 5 on the 4E rank: Evidence, Effect, Effort, Excitement. Write a short reason next to each score (for example "Evidence 4 (demonstrated)", "Effort 3 (moderate, needs dev work)"). The source gives no total. Skill convention: score Effort so that 5 means the least effort, order by the sum, and break a tie by the Evidence score. Write the scores in the 4E table of the template, 1 row per candidate.

Done when: each candidate has 4 scores with reasons, and the top one is the brief's subject.

### 9. Write the brief

Read `references/brief-template.md` and fill every field. List the real risks in the brief: financial, lost customers, reputational, legal, technical. The lost leads in weak variants are not a risk. They are the normal cost of a test. Run the free-promise check: compare the tested offer with the site, the app listing, and the FAQ. If the test sells as paid something that the team already promises as free, record the conflict and its fix (skill's check). Fill the Checks table (section 12). Read `references/examples.md` before you write the first brief. It has 2 filled briefs.

Done when: every field has a value or a marker, and the Checks pass.

### 10. Read the result (read mode)

Read `references/read-result.md` now and run it. It fills section 11: the result table, the constraint check, the tree row and its action, and the outcome sentence. A constraint trip wins over every other row. A tree written after the data gets the `post hoc` label.

Done when: section 11 is filled, and the action is the one that the tree states.

## Output

Return the filled brief in the exact format of `references/brief-template.md`. It has 12 sections and a final Gaps line. Section 11 (Result) is `not applicable` in design mode. Section 12 holds the Checks results. Keep each field with no value as `[NEEDS FROM USER: ...]` or `assumed: ...`. Never drop a field.

## Checks before done

Mark each check pass, fail, partial, or not measured. An item that the source marks "ideally" (or optional) counts as partial when it is missing, never as fail. A field that carries a marker counts as partial. Fix every fail before you return the brief. List each partial and not measured item under Gaps.

Record each result in section 12 of the brief.

- C1: The decision sentence and all 6 tree rows exist before any result. Thresholds came from the user, or carry a marker.
- C2: Both hypothesis forms pass the 3 rules: measurable, a controlled element, a result that the market can show.
- C3: Every evidence row has a level, a target, and a direction. Team text is under "Not evidence". The verdict uses only "tested thing" rows.
- C4: The method matches the table in step 5. An A/B test below tens of thousands of visits per month is a fail.
- C5: Interview evidence alone does not fire a "succeeds" row.
- C6: Exactly 1 decision metric. At least 1 constraint metric with a stop number.
- C7: The variant is a bold change, not a button colour or a 1 or 2 character title edit.
- C8: A false door has: placement in context, a contact field, a 50 to 100 result target, reveal text, consent, and compensation. Other methods: not applicable.
- C9: The runtime fits the deadline, or the brief names the fix.
- C10: The free-promise check has a result, and each conflict has a fix. For Canada, use the `ad-law-canada` pricing.md "Free" claims rules as the check.
- C11: No invented number, quote, threshold, or customer fact. Each gap has a marker.
- C12: Read mode: the action is the tree row's action, unchanged. A post hoc tree has its label. Design mode: not applicable.
