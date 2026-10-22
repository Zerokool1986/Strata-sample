---
id: NEG-PDF-ONLY-INVOICES
type: negative_knowledge
status: disproven
source: observed
created: 2026-02-11
updated: 2026-02-11
supersedes: none
superseded_by: none
related: [FIN-PAYMENT-LINK, RSK-EMAIL-DELIVERABILITY]
evidence: [support thread summary, 2026-02; OBS-LATE-PAYMENTS]
---

# NEG-PDF-ONLY-INVOICES — Invoice only as a PDF attachment gets lost and distrusted

## What was tried

Ledgerline's original invoice email carried no amount, no due date, and no
link in the body. Everything was inside the PDF attachment.

## What happened

Clients on mobile mail and behind strict spam filters missed or distrusted
the messages; several freelancers reported clients claiming the invoice never
arrived; late payments clustered on exactly those invoices. The body-less
email also failed the moment a client forwarded it to their bookkeeper —
nothing in the forwarded text said what was owed.

## Why we believe it failed

The attachment was doing three jobs (record, request, payment path) and doing
the last two badly. The fix was separating the jobs — see FIN-PAYMENT-LINK.

## Retry conditions

None for the original approach. An email body that carries amount, due
date, and link *plus* the PDF is the current design, not a retry of this one.

## Standing instruction

Any template change must keep amount, due date, and payment link in the
email body. An agent proposing an attachment-only template should be pointed
at this entry.
