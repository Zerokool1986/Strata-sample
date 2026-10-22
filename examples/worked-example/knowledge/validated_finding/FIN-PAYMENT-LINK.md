---
id: FIN-PAYMENT-LINK
type: validated_finding
status: settled
source: observed
created: 2026-02-25
updated: 2026-02-25
supersedes: none
superseded_by: none
related: [OBS-LATE-PAYMENTS, NEG-PDF-ONLY-INVOICES, MET-BEFORE-AFTER-COMPARISON]
evidence: [comparison record, 2026-02-25; OBS-LATE-PAYMENTS]
---

# FIN-PAYMENT-LINK — A payment link in the email body gets invoices paid faster

## The finding

Invoices whose email **body** contained a direct payment link were paid a
median of **4 days sooner** than invoices where the link existed only inside
the PDF attachment.

## The test

Six-week comparison run under the standard method
(MET-BEFORE-AFTER-COMPARISON), on invoices sent before and after the email
template changed to include the link in the body. Amount, due date, and link
in the body are now the standing template rule.

## Scope

Observed on single-freelancer accounts sending fewer than about 50 invoices
a month, in the user base as it existed at the time. Not measured for agency
accounts or for very high volumes.

## What would change our mind

A later comparison after any email-template redesign that fails to reproduce
the gap, or evidence that the effect was driven by a deliverability change
rather than the link itself (see RSK-EMAIL-DELIVERABILITY).
