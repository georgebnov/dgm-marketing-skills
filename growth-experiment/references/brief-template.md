# Experiment brief template

Return the brief in this exact format. Read it in step 9 and step 10. Read mode adds section 11. Keep a field with no value as `[NEEDS FROM USER: ...]` or `assumed: ...`. A field that does not apply to the method gets `not applicable (<reason>)`. A `not applicable` field is not a gap.

```
# Experiment brief: <short name>
Mode: design | read · Contact: <owner> · Date: <date>

## 1. Decision
Decision: If <X is true>, we will <Y>.
Agreed by: <names or roles, date> | not agreed yet
Funnel stage: <stage> · baseline: <number> · why: <drop-off or symptom>

## 2. Problem and premise
Problem: I am <customer> trying to <job> but <obstacle> because I <cause>, which makes me feel <feeling>.
Premise: <belief about customers>

## 3. Hypothesis
Evidence form: We know <fact>. We believe <change and effect>, and so we will <test> and observe <metric>.
Short form: If <change> then <effect> as measured by <decision metric>.
Parent hypothesis: <big hypothesis> | none

## 4. Evidence
| # | Evidence | Source | Level | Target | Direction |
|---|---|---|---|---|---|
| 1 | <fact> | <source> | say / do / purchase | tested thing / adjacent | agrees / disagrees |
Not evidence (team text): <FAQ, roadmap, pitch, plan | none>
Verdict: strongest agreeing level on the tested thing <level | none> · strongest disagreeing: <item | none found>

## 5. Method and prototype
Method: <interviews | compound | false door | concierge | A/B split> · pre-step: <interviews (5 to 8) | none>
Why: <table row from step 5, plus any conflict rule used>
Prototype: <fidelity> · surface: <ad / email / landing page / app feature>
Control (A): <description | not applicable (no control)>
Variant (B): <description of the bold change>
Evidence level reached: <say / do / purchase>

## 5b. False door (false door or concierge only)
Placement: <where the offer sits | not applicable (<method>)>
Reveal text: <text shown at once after the attempt | not applicable>
Consent: <how people agree to the waitlist, and the rule for the market | not applicable>
Compensation: <early access / discount / alternative product / extended trial | not applicable>

## 6. Objectives and metrics
Strategic goal: <goal metric> · input metric: <metric>
Decision: <1 metric> · lift/MDE: <value | not applicable (count-based, no control)>
Constraint: <metric> <stop number> → stop
Observation: <metrics>

## 7. Setup and run plan
Channel: <> · devices: <> · context: <page or flow> · customer: <segment>
Traffic: <estimate> · format: <split URL / interviews / false door / ...> · dates: <start> to <end> · runtime: <weeks>
Runtime math: <target ÷ (visits per week × click rate) = weeks | calculator output | not applicable> · deadline: <date | none> · fits deadline: <yes | no, fix: <step 7 option>>
Sample target: <number per variant | number of results | not measured> · stop rule: run to the planned sample

## 8. Decision tree
| Row | Threshold | Action |
|---|---|---|
| Succeeds above | <> | Launch at once |
| Succeeds within | <> | Launch on the roadmap |
| Fails within | <> | Revisit |
| Fails below | <> | New hypothesis |
| Inconclusive | <> | Revisit with a bolder change (skill convention) |
| Constraint trip | <constraint> | Stop the test |

## 9. 4E rank
| Candidate | Evidence | Effect | Effort | Excitement | Sum |
|---|---|---|---|---|---|
| <name> (this brief) | <1-5> (<reason>) | <1-5> (<reason>) | <1-5> (<reason>) | <1-5> (<reason>) | <sum> |
Convention (skill): Effort 5 means the least effort. Order by the sum. A tie goes to Evidence.

## 10. Risks and links
Risks: <financial / lost customers / reputational / legal / technical>
Free-promise check: <no conflict | conflict: "<site, listing, or FAQ text>" → <fix>>
Links: research <> · designs <> · ticket <> · test config <>

## 11. Result (read mode only)
Outcome: The hypothesis was <successful / unsuccessful / inconclusive> in demonstrating the premise.
| Treatment | Participants | Conversions | Rate | Index |
|---|---|---|---|---|
| Control (A) | <> | <> | <> | 100 |
| Variant (B) | <> | <> | <> | <> |
Constraint check: <metric = value, tripped / not tripped>
Tree row hit: <row> → action: <action>
Observations: <including disagreeing evidence>
Learning: <one sentence> · Next: <next experiment>

## 12. Checks
| Check | Result | Note |
|---|---|---|
| C1 | pass / fail / partial / not measured | <evidence or gap> |
| C2 ... C12 | (1 row each) | |

Gaps: <each NEEDS FROM USER, assumed, partial, and not measured item>
```

In design mode, section 11 is `## 11. Result (read mode only)` followed by `not applicable (design mode)`.
