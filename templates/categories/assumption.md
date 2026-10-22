# Template — Assumption

**File it here if:** the project is relying on something that has not been tested, and work would change if it turned out false.

**Not here if:** it has been tested (promote it to validated_finding or demote it to negative_knowledge), or nothing depends on it.

Copy this template to `knowledge/assumption/ASM-SHORT-SLUG.md`, fill in the
frontmatter, and replace every guidance block. Keep the entry to one screen where
you can.

---

---
id: ASM-SHORT-SLUG
type: assumption
status: <choose from knowledge/README.md>
source: <observed | quoted | inferred>
created: YYYY-MM-DD
updated: YYYY-MM-DD
supersedes: none
superseded_by: none
related: []
depends_on: []
evidence: []
memory_kind: <semantic | episodic | procedural>
source_tier: <primary | secondary | untrusted>
valid_from: YYYY-MM-DD
valid_to: <blank while still true>
recorded: YYYY-MM-DD
recorded_by: <human name | agent name + model>
last_verified: YYYY-MM-DD
review_due: YYYY-MM-DD
importance: <1-5>
---

# [Title — one line]

## Summary

[Two or three sentences that stand on their own in a context package.]

## The assumption, stated plainly

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What depends on it

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Why we believe it for now

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## How it could be checked

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What happens if it is false

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Evidence

[Links, paths, test names, dates — or an explicit "no evidence yet" that matches
the status you chose.]

---

## Worked example (from the sample project — delete when you file a real entry)

---
id: ASM-CLIENTS-CHECK-EMAIL
type: assumption
status: assumed
source: inferred
created: 2026-01-15
updated: 2026-01-15
supersedes: none
superseded_by: none
related: []
depends_on: []
evidence: []
---

# Most clients still read invoice email within 2 days

Ledgerline's whole reminder design assumes clients see email quickly. Support reports support this for small-business clients, but it has never been measured. If it is false — if clients mainly respond to messages on other channels — the reminder schedule needs redesign, not retiming. Checkable with email open tracking, which is deliberately not enabled yet for privacy reasons; the assumption stays flagged until then.

The full set of worked examples, cross-linked as a real store, is in
`examples/worked-example/`.
