# CASL checks (email and SMS)

Read this file at step 2 when the material is an email, an SMS, a signup form, or a lead-gen form.

CASL is Canada's Anti-Spam Legislation. The same rules apply to email and to text (SMS) messages. The CRTC enforces CASL. A commercial electronic message is an email or text message that you send for business purposes.

There are 2 general rules:

1. You need consent, or an exception to consent, before you send a message.
2. Each message must contain specific information and a valid unsubscribe function.

## Rule 1: consent

### Which basis applies

- **Express consent** is necessary when the business has no relationship with the recipient. Examples: an intake form, a lead-gen form, or "sign up for our newsletter".
- **Exceptions** are relationship-based. They give implied consent, so express consent is not necessary.
  - Existing business relationship. Example: a person bought the product in the last 2 years.
  - Responding to inquiries.
  - Many other exceptions exist, and some can apply. This skill has no detail on them. If the user relies on another exception, put it in "Not covered: lawyer".
  - The business still needs records that show which exception it relies on.
  - An exception usually removes only the consent requirement. The unsubscribe function is usually still necessary.

### Signup form checks (express consent)

Run each check on each signup or lead-gen form.

| Check | Level if it fails |
|---|---|
| The person gives an active yes. A request alone is not enough: the person must say yes, for example by checking an empty box next to "Yes, sign me up." | High |
| No pre-checked box. | High |
| The request names the sender (the business name). | Medium |
| The request says that the person can unsubscribe at any time. | Medium |
| The request gives the sender's contact information: a mailing address, plus 1 of a toll-free telephone number, a web address, or an email address. A hyperlink to this information is acceptable. | Medium |
| The business keeps a record of each consent. By law, the sender must prove that it had express consent, and must show the record if the CRTC asks. | High |
| A link to the privacy policy. This is a best practice from a privacy law view, not a CASL requirement. | Low |

**A form with a submit button.** The source did not say whether typing an email into a form and pressing a clearly labelled submit button is an active yes. **(skill choice)** Use this order:

1. A pre-checked box: fail at High (the source rule).
2. The form shows no consent wording at all (no sender, no unsubscribe statement): the request content checks fail at Medium. The active yes is "Not covered: lawyer".
3. The form or the button carries the consent wording (for example a button "Yes, sign me up" next to the sender name, "You can unsubscribe at any time", and the contact link): give the active yes check "Not covered: open question". Do not give it a fail. This case wins over the default in SKILL.md, which sends consent questions to a lawyer.

**The consent record.** The source said that the sender must prove the express consent and show the record if asked. It did not list the fields of the record. The fields are "Not covered: open question". The check here is only that a record exists for each consent.

Give "partial" when some, but not all, of the Medium items are present. Example: the business name is there, but no mailing address.

**Example wording of a valid express consent:** "Yes, send me the [Business] email newsletter [or text messages]. You can unsubscribe at any time. Contact us: [link]. Our privacy policy [link] says how we handle your personal information."

### Campaign checks (each message)

If the campaign has many emails or texts, map each message to its legal category: express consent or a specific named exception. Then each message is covered.

| Check | Level if it fails |
|---|---|
| Each message has a recorded basis: express consent, or a named exception with records. | High |
| No record exists, or you cannot see it. | not checked at High. Proof: "the consent record or the exception record for each recipient list". |

## Rule 2: content of each message

Run each check on each email or SMS.

| Check | Level if it fails |
|---|---|
| The sender name. | Medium |
| The contact information: a mailing address, plus 1 of email, web address, or toll-free telephone number. | Medium |
| A valid unsubscribe function. | Medium |
| The unsubscribe function is free. | Medium |
| The unsubscribe function is easy to use. | Medium |
| The unsubscribe function stays valid for 60 days. | Medium |
| The unsubscribe request takes effect within 10 (business) days. This part is critical. | Medium. If no process exists to apply the request in time: not checked, proof "the unsubscribe process and its time to take effect". |

These content rules apply also when an exception removes the consent requirement.
