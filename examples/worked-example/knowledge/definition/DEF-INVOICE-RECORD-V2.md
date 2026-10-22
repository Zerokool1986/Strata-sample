---
id: DEF-INVOICE-RECORD-V2
type: definition
status: settled
source: observed
memory_kind: semantic
source_tier: primary
created: 2026-05-20
updated: 2026-05-20
valid_from: 2026-05-20
valid_to:
recorded: 2026-05-20
last_verified: 2026-05-20
review_due: 2027-05-20
importance: 4
supersedes: DEF-INVOICE-RECORD
superseded_by: none
related: [DEF-INVOICE-RECORD, OBS-PORTAL-EDITS, ASM-PORTAL-AMOUNT-GOVERNS]
depends_on: [OBS-PORTAL-EDITS]
evidence: [OBS-PORTAL-EDITS]
---

# DEF-INVOICE-RECORD-V2 — The invoice of record is the portal's current version; the sent PDF is a snapshot

## Summary

The invoice of record is the version in the client portal as it currently
stands. The PDF generated at send time is a snapshot — evidence of what was
sent, not the governing amount. This definition replaces DEF-INVOICE-RECORD.

## The definition

- Disputes, payment matching, and "what does the client owe" are answered
  from the portal's current invoice version.
- The sent PDF is kept as the snapshot of what was originally sent, and is
  cited as exactly that in any dispute.
- Portal edits after sending are versioned by the portal; the current
  version is the record.

## Evidence and reasoning

OBS-PORTAL-EDITS: in 11 of 40 sampled disputes, the portal amount differed
from the sent PDF, and in every sampled case the client paid the portal
amount. The old definition (DEF-INVOICE-RECORD) named the PDF as
governing; practice had already moved. This definition records where the
truth actually lives, and payment-matching work now reads the portal
amount — see ASM-PORTAL-AMOUNT-GOVERNS for the assumption that replaced
the one this change invalidated.
