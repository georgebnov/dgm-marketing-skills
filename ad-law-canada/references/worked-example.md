# Worked example

Read this file before you write the review (SKILL.md, "Output"). Your review uses the same fields in the same order.

Input: a B2C landing page for all of Canada, in English only. It has the headline "Spring Sale: Now $10, Was $20", a $1.50 booking fee at checkout, "Our bottles are 100% eco-friendly", "Opens in two taps" in the feature list, an email signup with a pre-checked box, and a footer that names a competitor in plain text ("Also sold next to BrandX"). No price history or test report was supplied. No AI was used.

```
NOT LEGAL ADVICE. Information from course notes on Canadian advertising law. High and "Not covered: lawyer" items go to a lawyer before publishing.

Material: spring-sale landing page · type: landing page, signup form · audience: B2C · reach: all of Canada, Quebec yes · AI used: no
General impression: "The bottle costs $10 total, half its usual price, and it does not harm the environment."
Verdict: lawyer first: drip pricing, an unproven regular price, an untested green claim, and consent without an active yes.

1. [High] "$1.50 booking fee" added at checkout
   kind: practice
   rule: Competition Act · drip pricing (Cineplex: $39 million consent agreement, 2024, on appeal)
   result: fail
   fix: Show "$11.50" as the first price on the page, or remove the fee.
2. [High] "Was $20"
   kind: price · material
   rule: Competition Act · regular price time test (51% of days in the 6 months) and good faith
   result: not checked
   proof: 6 months of daily price history at $20 or higher on at least 51% of days, for each day of the sale, plus availability, a price audit, and sales volume at $20.
3. [High] "Our bottles are 100% eco-friendly"
   kind: green · material
   rule: Competition Act · June 2024 greenwashing provisions, product claim
   result: not checked
   proof: adequate and proper testing of the general impression "does not harm the environment", reproducible, done before publishing.
4. [High] Email signup with a pre-checked box
   kind: practice
   rule: CASL · CRTC · express consent
   result: fail
   fix: Remove the pre-check. Add an empty checkbox with "Yes, send me the [Business] email newsletter. You can unsubscribe at any time. Contact us: [link]." Record each consent.
5. [Medium] English-only page that reaches Quebec
   kind: practice
   rule: Quebec language laws · French prominence by medium
   result: fail
   fix: Add French copy that meets the prominence rules for a web page.
6. [Medium] "Opens in two taps"
   kind: performance · not material
   rule: Competition Act · substantiation before publishing
   result: not checked
   proof: a recorded test of the open flow on the shipped build, dated before publishing.
7. [Low] No privacy policy link in the consent request
   kind: practice
   rule: privacy law · best practice
   result: partial
   fix: Add "Our privacy policy [link] says how we handle your personal information."

Open questions: "Also sold next to BrandX" names a competitor in plain text, with no claim and no logo. Ask a lawyer if the name needs permission.
Passed: no contest · no gift card or loyalty terms
Assumed: the site uses only essential cookies (no cookie list supplied)
```
