---
id: DEF-INVOICE-RECORD
type: definition
status: superseded
source: observed
memory_kind: semantic
source_tier: primary
created: 2026-01-15
updated: 2026-05-20
valid_from: 2026-01-15
valid_to: 2026-05-20
recorded: 2026-01-15
last_verified: 2026-03-10
review_due: 2027-01-15
importance: 4
supersedes: none
superseded_by: DEF-INVOICE-RECORD-V2
related: [DEF-INVOICE-RECORD-V2, ASM-PDF-IS-AUTHORITATIVE, OBS-PORTAL-EDITS]
depends_on: []
evidence: []
---

# DEF-INVOICE-RECORD — (SUPERSEDED) The invoice of record is the PDF generated at send time

> This entry is **superseded** by DEF-INVOICE-RECORD-V2. It is kept,
> unedited, as the historical record of the earlier definition. Do not use
> it.

## The definition (as originally written)

The invoice of record — the version that governs disputes, payment matching,
and what the client owes — is the PDF generated when the invoice is sent.
The portal page and the email are renderings of that PDF.

## Why it was replaced

OBS-PORTAL-EDITS (2026-05-11) showed freelancers routinely editing invoice
amounts in the portal after sending, and clients paying the portal amount.
A definition that names the PDF as governing was describing a system that
no longer existed. Superseded 2026-05-20; see DEF-INVOICE-RECORD-V2. The
supersession triggered an invalidation sweep; the full sequence is walked
through in the paid editions' worked example.
