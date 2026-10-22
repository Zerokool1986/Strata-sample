---
id: DEF-OVERDUE-30
type: definition
status: settled
source: observed
created: 2026-03-04
updated: 2026-03-04
supersedes: DEF-OVERDUE-14
superseded_by: none
related: [OBS-LATE-PAYMENTS, CON-PAYMENT-TERMS]
evidence: [OBS-LATE-PAYMENTS]
---

# DEF-OVERDUE-30 — An invoice is overdue 30 days after sending

## Summary

An invoice counts as overdue 30 days after it was sent. This definition
replaces DEF-OVERDUE-14.

## The definition

- The due date is the send date plus 30 days. Reminders before the due date
  are "upcoming" reminders; reminders after it are "overdue" reminders, with
  different wording.
- The definition is about classification. What the app *does* at each stage
  is the reminder schedule's business, which must reference this definition
  rather than restating a number of days.

## Evidence and reasoning

OBS-LATE-PAYMENTS (median payment at 23 days) showed the old 14-day line sat
below normal behaviour. 30 days was chosen to sit just above the observed
median, so "overdue" means genuinely late for this user base. If the median
moves materially, revisit this number — it is an evidence-based setting, not
a law of nature.

## Known inconsistency

The public help page still states the 14-day rule. That contradiction is
open and recorded in CON-PAYMENT-TERMS; until it is resolved, this entry and
the app behaviour (net 30) are what agents should quote.
