---
id: ASM-PDF-IS-AUTHORITATIVE
type: assumption
status: superseded
source: inferred
memory_kind: semantic
source_tier: primary
created: 2026-02-02
updated: 2026-05-27
valid_from: 2026-02-02
valid_to: 2026-05-20
recorded: 2026-02-02
last_verified: 2026-05-27
review_due: 2026-08-25
importance: 4
supersedes: none
superseded_by: ASM-PORTAL-AMOUNT-GOVERNS
related: [DEF-INVOICE-RECORD, OBS-PORTAL-EDITS]
depends_on: [DEF-INVOICE-RECORD]
evidence: []
---

# ASM-PDF-IS-AUTHORITATIVE — (SUPERSEDED) The sent PDF matches what the client sees, so matching can rely on it

> **Invalidation sweep note, 2026-05-20.** This entry was flagged
> `needs_review: true` by the consolidation pass of 2026-05-20 (flag since
> cleared by the re-check below). Reason: DEF-INVOICE-RECORD, listed in
> this entry's `depends_on`, was superseded by DEF-INVOICE-RECORD-V2.
> Re-check requested: does the payment-matching design still hold if the
> portal version, not the PDF, is the invoice of record?
>
> **Re-check outcome, 2026-05-27.** It does not hold. OBS-PORTAL-EDITS
> shows portal amounts diverging from sent PDFs, with clients paying the
> portal amount. This assumption is superseded by
> ASM-PORTAL-AMOUNT-GOVERNS. Nothing in this entry's body was edited in
> the process — the flag, the re-check, and the replacement are the
> record. The full sequence is walked through in the paid
> editions' worked example.

## The assumption (as originally written)

Payment matching and dispute handling can rely on the sent PDF: what the
client sees, and what they owe, is the PDF generated at send time, as
defined in DEF-INVOICE-RECORD.

## What depended on it

The payment-matching design (match incoming payments against PDF totals)
and the dispute playbook (quote the PDF). Both were designed while
DEF-INVOICE-RECORD stood, and nothing in either design re-stated the
premise — which is exactly why the dependency had to be declared here, in
`depends_on`, where the sweep could find it.

## Why we believed it for now (as written in February)

The definition said the PDF governed, the portal was new, and nobody had
yet seen a case where the two disagreed. The assumption was reasonable
when filed. It stopped being reasonable the day the definition fell —
and without the sweep, nobody would have come back to ask.
