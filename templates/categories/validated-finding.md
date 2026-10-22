# Template — Validated finding

**File it here if:** a claim was tested, the test is recorded, and the result held up.

**Not here if:** the evidence is a single anecdote (use empirical_observation), or the test cannot be described (keep it a hypothesis).

Copy this template to `knowledge/validated_finding/FIN-SHORT-SLUG.md`, fill in the
frontmatter, and replace every guidance block. Keep the entry to one screen where
you can.

---

---
id: FIN-SHORT-SLUG
type: validated_finding
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

## The finding, in one sentence

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## The test that produced it

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## The evidence (links, dates, numbers)

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Scope: where this holds and where it may not

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What would change our mind

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Evidence

[Links, paths, test names, dates — or an explicit "no evidence yet" that matches
the status you chose.]

---

## Worked example (from the sample project — delete when you file a real entry)

---
id: FIN-PAYMENT-LINK
type: validated_finding
status: settled
source: observed
created: 2026-01-15
updated: 2026-01-15
supersedes: none
superseded_by: none
related: []
depends_on: []
evidence: []
---

# Invoices with a payment link in the email body are paid faster

Over a 6-week comparison in Ledgerline, invoices whose email body contained a direct payment link were paid a median of 4 days sooner than invoices where the link was only inside the PDF. Scope: single-freelancer accounts sending fewer than 50 invoices a month. Revisit if the email template changes.

The full set of worked examples, cross-linked as a real store, is in
`examples/worked-example/`.
