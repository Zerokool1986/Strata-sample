---
id: ASM-PORTAL-AMOUNT-GOVERNS
type: assumption
status: assumed
source: inferred
memory_kind: semantic
source_tier: primary
created: 2026-05-27
updated: 2026-05-27
valid_from: 2026-05-20
valid_to:
recorded: 2026-05-27
last_verified: 2026-05-27
review_due: 2026-08-25
importance: 4
supersedes: ASM-PDF-IS-AUTHORITATIVE
superseded_by: none
related: [DEF-INVOICE-RECORD-V2, OBS-PORTAL-EDITS, ASM-PDF-IS-AUTHORITATIVE]
depends_on: [DEF-INVOICE-RECORD-V2, OBS-PORTAL-EDITS]
evidence: [OBS-PORTAL-EDITS]
---

# ASM-PORTAL-AMOUNT-GOVERNS — Payment matching must read the portal amount; the sent PDF is a snapshot only

## The assumption

Payment matching and dispute handling should treat the portal's current
invoice amount as the amount owed, and the sent PDF as a snapshot of what
was originally sent — usable as evidence in a dispute, never as the
matching target.

## What depends on it

The payment-matching redesign and the dispute playbook rewrite. Both now
declare this entry in their reasoning — and this entry declares its own
premises in `depends_on` (DEF-INVOICE-RECORD-V2 and the observation under
it), so the next upstream change flags this one in turn. The chain is the
point.

## Why we believe it for now

OBS-PORTAL-EDITS is a small, dispute-skewed sample. It is strong enough to
kill the old assumption — clients demonstrably pay portal amounts — but
not yet strong enough to call the new behaviour settled: whether portal
edits are common on *undisputed* invoices is unmeasured. Hence `assumed`,
with a review date, and the honest dependency list above.
