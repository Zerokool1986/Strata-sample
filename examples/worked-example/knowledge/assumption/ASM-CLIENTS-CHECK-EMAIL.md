---
id: ASM-CLIENTS-CHECK-EMAIL
type: assumption
status: assumed
source: inferred
created: 2026-01-20
updated: 2026-01-20
supersedes: none
superseded_by: none
related: [HYP-REMINDER-TIMING, OBS-LATE-PAYMENTS]
evidence: []
---

# ASM-CLIENTS-CHECK-EMAIL — Most clients read invoice email within 2 days

## The assumption

Most clients of Ledgerline's freelancers see an invoice or reminder email
within about 2 days of it being sent.

## What depends on it

The entire reminder design: reminder timing is planned in days, on the belief
that a reminder sent on day X influences behaviour around day X. If clients
actually batch their email weekly, or mostly respond on other channels,
retiming reminders is pointless — the channel is the problem.

## Why we believe it for now

Support conversations suggest small-business clients do read email promptly,
and the observed payment pattern (OBS-LATE-PAYMENTS) is consistent with it.
Consistent-with is not measured. Nobody has tracked opens for this.

## How it could be checked / what happens if false

Checkable with email open tracking, deliberately not enabled (privacy and
deliverability trade-offs, see RSK-EMAIL-DELIVERABILITY). If it proves false,
the reminder strategy entry and the hypothesis HYP-REMINDER-TIMING both need
rework, and this entry gets superseded by whatever the measurement shows.
Until then: **any plan that leans on reminder timing must name this
assumption.** The reminder-task briefing does.
