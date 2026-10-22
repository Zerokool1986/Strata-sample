# Worked Example — Ledgerline

A complete miniature of the system, using one fictional project throughout:
**Ledgerline**, a small invoicing app for freelancers. A freelancer creates an
invoice, emails it to a client, the client pays, Ledgerline tracks what is owed
and sends reminders.

Everything here is fictional and illustrative. The point is not the numbers —
it is the *shape*: how entries in different categories link to each other, how
statuses behave, and how a briefing is assembled from a real store.

## What is in this example

- `knowledge/` — 10 filled entries across 4 of the kit's 14 categories,
  cross-linked the way a real store grows:
  - the assumption the reminder work quietly leans on
    (`ASM-CLIENTS-CHECK-EMAIL`, labelled `assumed`),
  - a validated finding (`FIN-PAYMENT-LINK`),
  - negative knowledge (`NEG-PDF-ONLY-INVOICES`) — the tried-and-failed
    record every project needs,
  - a **supersession chain**: `DEF-OVERDUE-14` (status `superseded`) replaced
    by `DEF-OVERDUE-30` (status `settled`) — the old definition is kept,
    marked, and linked, not edited away,
  - the everyday definitions a store accumulates (`DEF-INVOICE`,
    `DEF-INVOICE-RECORD`, `DEF-INVOICE-RECORD-V2`) and two further
    assumptions (`ASM-PDF-IS-AUTHORITATIVE`, `ASM-PORTAL-AMOUNT-GOVERNS`).
- `agent-briefing-filled.md` — a briefing for the task "move the first reminder
  to 2 days before the due date", built with `templates/agent-briefing.md`.

The full worked example — 18 entries across 11 categories, including the
invalidation chain and the context package assembled from the briefing — is
in the paid editions.

## How to read it

Start with the briefing. Notice what it pulls and — more instructively — what
it leaves out: the store holds more than this task needs, and the briefing
takes only what the task touches. Then read the supersession chain and ask
yourself what an agent *without* it would have done: it would have read the
old definition, believed 14 days, and built the reminder schedule on a due
date the project no longer uses.

## Copying this example

Do not copy Ledgerline's content into your project. Copy its *moves*: label
the assumption before building on it, file what did not work as negative
knowledge, and supersede the definition instead of editing it.

## Where this example goes next

In the paid editions, this store keeps growing — more categories fill in,
the invalidation chain plays out in full, and three of Ledgerline's
procedures are compiled from these entries into Agent Skills (Complete
edition). Every claim stays here, in the store, with its status; the
editions add the stages that work on top of it.
