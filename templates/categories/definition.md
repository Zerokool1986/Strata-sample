# Template — Definition

**File it here if:** a term, invariant, or interface has a settled meaning the whole project should share.

**Not here if:** the meaning is still being debated (use hypothesis or unresolved_question), or it is a how-to (use execution_knowledge).

Copy this template to `knowledge/definition/DEF-SHORT-SLUG.md`, fill in the
frontmatter, and replace every guidance block. Keep the entry to one screen where
you can.

---

---
id: DEF-SHORT-SLUG
type: definition
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

## The definition

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What it includes

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## What it explicitly does not include

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Where it applies

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Examples (one clear, one borderline)

[Guidance: write this section for a reader who was not there. Be specific; link evidence instead of pasting it.]

## Evidence

[Links, paths, test names, dates — or an explicit "no evidence yet" that matches
the status you chose.]

---

## Worked example (from the sample project — delete when you file a real entry)

---
id: DEF-INVOICE
type: definition
status: settled
source: inferred
created: 2026-01-15
updated: 2026-01-15
supersedes: none
superseded_by: none
related: []
depends_on: []
evidence: []
---

# An invoice is a request for payment, not a receipt

In the sample project (Ledgerline, an invoicing app for freelancers), an *invoice* is the document that requests payment for work already agreed. A *receipt* is issued after payment arrives. The two are never the same record, and the app never edits an invoice after it is sent — corrections are new documents linked to the original.

The full set of worked examples, cross-linked as a real store, is in
`examples/worked-example/`.
