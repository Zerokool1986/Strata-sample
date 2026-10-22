# Template — Negative knowledge

**File it here if:** something was tried, in practice, and did not work — and a future agent or person might plausibly try it again.

**Not here if:** it was rejected on reasoning alone without being tried (use rejected_hypothesis), or it failed for a one-off external reason that says nothing about the approach.

Copy this template to `knowledge/negative_knowledge/NEG-SHORT-SLUG.md`, fill in the
frontmatter, and replace every guidance block. Keep the entry to one screen where
you can.

---

---
id: NEG-SHORT-SLUG
type: negative_knowledge
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

## What was tried

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Context: when, where, at what scale

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What happened

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Why we believe it failed

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Conditions under which it could be retried

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What we did instead

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Evidence

[Links, paths, test names, dates — or an explicit "no evidence yet" that matches
the status you chose.]

---

## Worked example (from the sample project — delete when you file a real entry)

---
id: NEG-PDF-ONLY-INVOICES
type: negative_knowledge
status: disproven
source: observed
created: 2026-01-15
updated: 2026-01-15
supersedes: none
superseded_by: none
related: []
depends_on: []
evidence: []
---

# Sending the invoice only as a PDF attachment loses clients

For Ledgerline's first months, invoice emails contained no amounts or links in the body — everything was in the PDF attachment. Result: clients on mobile mail and behind strict spam filters missed or distrusted the mails, and late payments clustered on those invoices. Retried only if the body always carries amount, due date, and link — which is the current design, so the original approach stays retired.

The full set of worked examples, cross-linked as a real store, is in
`examples/worked-example/`.
