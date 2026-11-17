# Read the result (read mode)

Read this file in step 10. Fill section 11 of `references/brief-template.md`.

1. Fill the result table: participants, conversions, rate, and index per treatment. Index = rate ÷ control rate × 100 (control = 100). This formula is a skill convention.
2. Check the constraint metrics first. A constraint trip wins over every other row.
3. Find the row of the decision tree that the decision metric hits. Write its action, unchanged.
4. Write the outcome sentence: "The hypothesis was [successful / unsuccessful / inconclusive] in demonstrating the premise."
5. Write the observations, including the evidence that disagrees.
6. If the tree was written after the data, label the result `post hoc: decision tree written after the data`. Give the action only if the user set the thresholds. Otherwise mark it `[NEEDS FROM USER: thresholds]`. Recommend a rerun with a tree agreed in advance.
7. If the decision metric is say-level (interviews), a "succeeds" row does not launch. Its action becomes: run a behaviour test (do or purchase level) on the solution.
8. Write the learning and the next experiment. A fast, clear loss is a useful result: take it apart and move on.

Present the result as a short read-out to the people who agreed to the decision. Much of experimentation is communication. Show the idea, the evidence, and the action.

Done when: the result block is filled, and the action is the one that the tree states.

## Worked example: section 11

A synthetic A/B illustration. Two offers ran for 10 days with 10 people per offer each day (100 per offer). Offer A is the control. The tree was not written before the test, so the result carries the post hoc label.

```
## 11. Result (read mode only)
Outcome: The hypothesis was successful in demonstrating the premise.
| Treatment | Participants | Conversions | Rate | Index |
|---|---|---|---|---|
| Control (A) | 100 | 20 | 20.0% | 100 |
| Variant (B) | 100 | 26 | 26.0% | 130 |
Constraint check: [NEEDS FROM USER: no constraint was set], not tripped
Tree row hit: [NEEDS FROM USER: thresholds] → action: post hoc: decision tree written after the data. Recommend a rerun with a tree agreed in advance.
Observations: on day 1, B was 3/10 (30%) and A was 0/10 (0%). A stop on day 1 would pick B on noise, before the data could show it.
Learning: the full-run average, not 1 day, decides the winner · Next: [NEEDS FROM USER: next experiment]
```

The brief's Gaps line then lists: constraint, thresholds, next experiment, and the post hoc label.
