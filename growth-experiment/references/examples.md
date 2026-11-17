# Filled briefs (synthetic examples)

These briefs use invented businesses. Each field that the user did not give carries a marker. This is the correct behaviour: a brief shows its gaps, it does not fill them. Both briefs follow `brief-template.md` field for field. A worked section 11 (read mode) is in `read-result.md`.

## Example 1: Delivery date on the product page (A/B split, design mode)

Input: an online furniture store with 90,000 mobile visits per month. Support tickets show that mobile shoppers leave the product page to ask when a sofa will arrive. The team wants to show an estimated delivery date next to the price.

```
# Experiment brief: Delivery date on the product page
Mode: design · Contact: [NEEDS FROM USER: test owner] · Date: [NEEDS FROM USER: date]

## 1. Decision
Decision: If [NEEDS FROM USER: condition on checkout rate], we will [NEEDS FROM USER: action].
Agreed by: not agreed yet
Funnel stage: product page to checkout · baseline: [NEEDS FROM USER: current checkout rate on sofa pages] · why: mobile shoppers leave the page to ask about delivery

## 2. Problem and premise
Problem: I am a mobile shopper trying to buy a sofa before guests arrive but I cannot see when it will arrive because the page shows no delivery date, which makes me feel unsure and afraid to pay for the wrong date.
Premise: Ready-to-buy mobile shoppers need a delivery date before they commit to a large purchase.

## 3. Hypothesis
Evidence form: We know mobile shoppers send support tickets about delivery dates from sofa pages. We believe a delivery date next to the price removes that doubt, and so we will run a split URL test on mobile and observe completed checkouts over visits.
Short form: If mobile users see an estimated delivery date next to the price, then more of them complete checkout, as measured by completed checkouts over visits.
Parent hypothesis: none

## 4. Evidence
| # | Evidence | Source | Level | Target | Direction |
|---|---|---|---|---|---|
| 1 | Support tickets about delivery dates from sofa pages | customer research | say | tested thing | agrees |
| 2 | [NEEDS FROM USER: exit rate on sofa pages, mobile vs desktop] | site analytics | do | tested thing | [NEEDS FROM USER] |
Not evidence (team text): none
Verdict: strongest agreeing level on the tested thing say · strongest disagreeing: none found

## 5. Method and prototype
Method: A/B split · pre-step: none
Why: traffic of 90,000 per month is above tens of thousands of visits per month, and the variant is a bold change
Prototype: assumed: mockup · surface: landing page (product page)
Control (A): the current sofa product page
Variant (B): an estimated delivery date range next to the price, with the postal code field to refine it
Evidence level reached: purchase (completed checkouts)

## 5b. False door (false door or concierge only)
Placement: not applicable (A/B split)
Reveal text: not applicable
Consent: not applicable
Compensation: not applicable

## 6. Objectives and metrics
Strategic goal: [NEEDS FROM USER: goal metric] · input metric: conversion rate
Decision: checkout rate (sofa pages, mobile) · lift/MDE: [NEEDS FROM USER: MDE]
Constraint: support tickets about delivery up more than 20% → stop
Observation: cart abandonment, revenue per visitor, postal code field use

## 7. Setup and run plan
Channel: website · devices: mobile only · context: sofa product pages · customer: new visits
Traffic: 90,000 per month (100% exposure) · format: split URL · dates: [NEEDS FROM USER] to [NEEDS FROM USER] · runtime: [NEEDS FROM USER: weeks from the calculator]
Runtime math: not measured (no calculator output) · deadline: none · fits deadline: yes
Sample target: not measured · stop rule: run to the planned sample

## 8. Decision tree
| Row | Threshold | Action |
|---|---|---|
| Succeeds above | [NEEDS FROM USER: threshold] | Launch at once |
| Succeeds within | [NEEDS FROM USER: threshold] | Launch on the roadmap |
| Fails within | [NEEDS FROM USER: threshold] | Revisit |
| Fails below | [NEEDS FROM USER: threshold] | New hypothesis |
| Inconclusive | [NEEDS FROM USER: threshold] | Revisit with a bolder change (skill convention) |
| Constraint trip | support tickets about delivery up more than 20% | Stop the test |

## 9. 4E rank
| Candidate | Evidence | Effect | Effort | Excitement | Sum |
|---|---|---|---|---|---|
| Delivery date on the product page (this brief) | 3 (support tickets) | 3 (moderate) | 3 (moderate, needs the delivery data feed) | 4 (team favourite) | 13 |
Convention (skill): Effort 5 means the least effort. Order by the sum. A tie goes to Evidence.

## 10. Risks and links
Risks: technical: the delivery estimate must come from real stock and carrier data · [NEEDS FROM USER: other risks]
Free-promise check: [NEEDS FROM USER: site text about delivery times and fees]
Links: research [NEEDS FROM USER] · designs [NEEDS FROM USER] · ticket [NEEDS FROM USER] · test config [NEEDS FROM USER]

## 11. Result (read mode only)
not applicable (design mode)

## 12. Checks
| Check | Result | Note |
|---|---|---|
| C1 | partial | decision and 5 thresholds carry markers |
| C2 | pass | short form is measurable, owns the date element, checkout rate shows the result |
| C3 | partial | evidence row 2 carries markers |
| C4 | pass | 90,000 traffic, A/B split row |
| C5 | pass | support tickets are not the decision metric |
| C6 | pass | 1 decision metric, constraint on support tickets |
| C7 | pass | a new element next to the price, not a colour change |
| C8 | not applicable | A/B split |
| C9 | pass | no deadline |
| C10 | partial | site text not given |
| C11 | pass | all values from the input or marked |
| C12 | not applicable | design mode |

Gaps: test owner, date, decision, baseline, evidence row 2, MDE, goal metric, dates, runtime, 5 thresholds, sample size (not measured), other risks, free-promise check, links. assumed: prototype fidelity.
```

## Example 2: Subscription demand for a coffee brand (false door with an interview pre-step, design mode)

Input: a coffee brand sells beans online. It launched a subscription about 6 months ago. Most customers still choose a one-time purchase. The team uses paid ads and creator posts.

```
# Experiment brief: Subscription false door
Mode: design · Contact: [NEEDS FROM USER: test owner] · Date: [NEEDS FROM USER: date]

## 1. Decision
Decision: If [NEEDS FROM USER: number, 50 to 100 is the target] people choose the new subscription offer in the false door, we will [NEEDS FROM USER: action].
Agreed by: not agreed yet
Funnel stage: purchase to subscription · baseline: [NEEDS FROM USER: subscription share of orders] · why: customers choose a one-time purchase over the subscription

## 2. Problem and premise
Problem: I am [NEEDS FROM USER: customer] trying to have fresh coffee every morning but [NEEDS FROM USER: obstacle] because I [NEEDS FROM USER: cause], which makes me feel [NEEDS FROM USER: feeling].
Premise: [NEEDS FROM USER: belief about why customers avoid the subscription]

## 3. Hypothesis
Evidence form: We know customers choose a one-time purchase over the subscription. We believe [NEEDS FROM USER: X, the new offer] will move more customers from single purchase to subscription, and so we will run a false door for that offer and observe sign-ups, up to 100 people.
Short form: If we offer [NEEDS FROM USER: X], then more customers choose the subscription, as measured by false door sign-ups with contact info.
Parent hypothesis: By doing X, we can move more customers from single purchase to subscription.

## 4. Evidence
| # | Evidence | Source | Level | Target | Direction |
|---|---|---|---|---|---|
| 1 | Customers choose a one-time purchase over the subscription | historical sales data | purchase | tested thing | agrees (the problem exists) |
| 2 | Cancellation survey results, low response rate | customer research | say | tested thing | [NEEDS FROM USER: what the answers say] |
| 3 | Pain-point and pricing feedback | customer research | say | adjacent | [NEEDS FROM USER: what the feedback says] |
Not evidence (team text): none given
Verdict: strongest agreeing level on the tested thing purchase (for the problem, not for a solution) · strongest disagreeing: none found

## 5. Method and prototype
Method: false door · pre-step: interviews (5 to 8)
Why: the team must measure demand for an offer that does not exist yet. The interview row also fits, because the premise is unknown. Pattern: main method + interview pre-step.
Prototype: assumed: mockup · surface: landing page (the homepage, where offers live)
Control (A): not applicable (no control, count-based)
Variant (B): [NEEDS FROM USER: X, the new subscription offer], with a sign-up form for name and email
Evidence level reached: do (sign-up with contact info, no payment)

## 5b. False door (false door or concierge only)
Placement: homepage, where offers live
Reveal text: "Thanks for your interest. This offer is not ready yet. With your permission, we would like to add you to our waitlist."
Consent: waitlist only with permission (required in Canada) · [NEEDS FROM USER: market]
Compensation: [NEEDS FROM USER: early access, a discount, an alternative product, or an extended trial]

## 6. Objectives and metrics
Strategic goal: [NEEDS FROM USER: goal metric] · input metric: [NEEDS FROM USER: input metric]
Decision: false door sign-ups with contact info · lift/MDE: not applicable (count-based, no control)
Constraint: [NEEDS FROM USER: false door constraint] → stop. For the later real subscription test: [NEEDS FROM USER: cancellation stop number] → stop.
Observation: [NEEDS FROM USER: observation metrics]

## 7. Setup and run plan
Channel: website, with traffic from paid ads and creator posts · devices: [NEEDS FROM USER] · context: homepage offer area · customer: [NEEDS FROM USER: segment]
Traffic: [NEEDS FROM USER: estimate] · format: false door · dates: [NEEDS FROM USER] to [NEEDS FROM USER] · runtime: [NEEDS FROM USER: weeks]
Runtime math: 50 to 100 ÷ ([NEEDS FROM USER: visits per week] × [NEEDS FROM USER: expected click rate]) · deadline: [NEEDS FROM USER] · fits deadline: [NEEDS FROM USER]
Sample target: 50 to 100 results · stop rule: run to the planned sample

## 8. Decision tree
| Row | Threshold | Action |
|---|---|---|
| Succeeds above | [NEEDS FROM USER: threshold] | Launch at once |
| Succeeds within | [NEEDS FROM USER: threshold] | Launch on the roadmap |
| Fails within | [NEEDS FROM USER: threshold] | Revisit |
| Fails below | [NEEDS FROM USER: threshold] | New hypothesis |
| Inconclusive | [NEEDS FROM USER: threshold] | Revisit with a bolder change (skill convention) |
| Constraint trip | [NEEDS FROM USER: false door constraint] | Stop the test |

## 9. 4E rank
| Candidate | Evidence | Effect | Effort | Excitement | Sum |
|---|---|---|---|---|---|
| Subscription false door (this brief) | [NEEDS FROM USER] | [NEEDS FROM USER] | [NEEDS FROM USER] | [NEEDS FROM USER] | [NEEDS FROM USER] |
Convention (skill): Effort 5 means the least effort. Order by the sum. A tie goes to Evidence.

## 10. Risks and links
Risks: reputational and lost customers: the reveal can upset people · legal: waitlist permission, [NEEDS FROM USER: market]
Free-promise check: [NEEDS FROM USER: site text about the subscription and its price]
Links: research [NEEDS FROM USER] · designs [NEEDS FROM USER] · ticket [NEEDS FROM USER] · test config [NEEDS FROM USER]

## 11. Result (read mode only)
not applicable (design mode)

## 12. Checks
| Check | Result | Note |
|---|---|---|
| C1 | partial | decision action and all thresholds carry markers |
| C2 | partial | offer X carries a marker |
| C3 | pass | each row has a level, a target, and a direction or marker |
| C4 | pass | demand for an offer that does not exist, with an interview pre-step |
| C5 | pass | the interviews are a pre-step, the false door decides |
| C6 | partial | false door constraint carries a marker |
| C7 | partial | offer X carries a marker |
| C8 | partial | placement, contact field, target, and reveal text exist. Consent market and compensation carry markers |
| C9 | partial | traffic, click rate, and deadline carry markers |
| C10 | partial | site text not given |
| C11 | pass | all values from the input or marked |
| C12 | not applicable | design mode |

Gaps: owner, date, decision action, baseline, problem details, premise, offer X, survey and feedback content, goal and input metrics, false door constraint, cancellation stop number, observation metrics, setup details, traffic, click rate, dates, deadline, all thresholds, 4E scores, market, compensation, free-promise check, links. assumed: prototype fidelity.
```
