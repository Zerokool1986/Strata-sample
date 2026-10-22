> **Sample note:** This sample includes the Remember core; sections describing the full store apply to the paid editions.

# Quickstart — Your First Hour With Strata

This walkthrough takes a real (fictional) project from nothing to a working wiki in
about an hour. The project is **Ledgerline**, a small invoicing app for freelancers.
Every filled-in result mentioned here is in `examples/worked-example/` so you can
compare your output against it as you go.

**Already have a giant `CLAUDE.md` or `AGENTS.md`?** Do not start here —
start with `guides/rescue-and-migration.md`, which migrates what you have
instead of asking you to start over. Come back to this walkthrough once the
monolith is inventoried.

You do not need the whole kit in your head. You need: one narrative document, three
knowledge entries, and one briefing. Everything else grows from use.

## 0. Copy the kit in (5 minutes)

Copy these four folders into the root of your project repo:

- `knowledge/` — your typed knowledge store (Tier 1)
- `docs/wiki/` — your narrative project wiki
- `templates/` — the templates you will copy from as you file entries
- `inbox/` — the capture lane for mid-task notes you are not ready to judge yet
- `skills/` — the compiled-procedures layer (v1.3). It starts empty and
  fills later, as procedures graduate; copy it now so the folder exists
  when the first promote-to-skill proposal is approved

Then copy `templates/AGENTS.md` to the repo root as `AGENTS.md` (if your project
already has one, merge the wiki sections into it instead of replacing it).

## 1. Fill in the North Star (10 minutes)

Open `docs/wiki/01_system_north_star.md` and answer its sections briefly. For
Ledgerline, the finished version reads, in summary:

- **Purpose:** help freelancers get paid without chasing clients by hand.
- **Non-goals:** it is not an accounting system, not a bank, and does not do taxes.
- **Principles:** the freelancer's client relationships come before enforcement;
  every automated message must be one a human would be comfortable sending.

One page is enough. This document is what every later argument defers to, so vague
is worse than short.

## 2. File your first three entries (20 minutes)

Use `templates/knowledge-entry.md`, or the per-category templates in
`templates/categories/`. For hour one, file exactly these three kinds — they are
the ones that pay off fastest:

1. **A definition** for the term your project argues about most.
   Ledgerline filed `DEF-INVOICE`: an invoice is a request for payment, not a
   receipt — the confusion between the two had caused real bugs.
2. **An assumption** your project leans on without having tested.
   Ledgerline filed `ASM-CLIENTS-CHECK-EMAIL`: the reminder design assumes clients
   read email within 2 days. Never measured. Now it is written down, flagged
   `status: assumed`, and every entry that depends on it links to it.
3. **A negative knowledge** entry for something already tried that failed.
   Ledgerline filed `NEG-PDF-ONLY-INVOICES`: invoices sent only as PDF attachments
   got lost and distrusted. Retired, on record, never to be silently retried.

Notice what the frontmatter does while you file these: you must state a **status**
and a **source** for each. If you cannot honestly say `settled`, the entry is
`assumed` or `testing` — that honesty is the entire point.

## 3. Run one briefing (15 minutes)

Pick the next real task on the project. For Ledgerline it was: *"Change the first
reminder to go out 2 days before the due date."*

Copy `templates/agent-briefing.md` and fill it in:

- **Task** and what done looks like.
- **Relevant knowledge**: pull `OBS-LATE-PAYMENTS` (median payment at 23 days),
  `HYP-REMINDER-TIMING` (the claim being tested), `ASM-CLIENTS-CHECK-EMAIL`
  (flagged as an assumption), and `CON-PAYMENT-TERMS` (the open contradiction:
  help text says net 14, the app enforces net 30 — relevant because reminder
  timing hangs off the due date).
- **Boundaries**: do not change the due-date rule itself; that contradiction is
  not this task's to resolve.

Assemble the actual text you will hand the agent with
`templates/context-package.md`: the briefing plus the full text of those four
entries, nothing else. (A finished context package appears in the paid
editions' worked example.)

## 4. File back afterwards (10 minutes)

When the task is done, run `templates/end-of-task-filing.md`:

- What was learned? (Ledgerline: the early reminder was implemented; the comparison
  window was set per `MET-BEFORE-AFTER-COMPARISON`.)
- What status changed? (`HYP-REMINDER-TIMING` stays `testing` until the comparison
  window closes — finishing the code does not validate the claim.)
- What new questions opened? (Whether reminder wording should differ when the
  contradiction on payment terms is resolved.)

That filing step is the difference between a wiki and a folder of good intentions.

## After hour one

- File entries as you learn things, in the moment, using the category templates —
  or, mid-task, capture them in `inbox/` and let the consolidation pass judge
  them (`guides/deferred-adjudication-inbox.md`). Capturing is cheap on
  purpose; judging is batched on purpose.
- Skim `guides/keeping-it-alive.md` once — it is short, and it is the anti-rot plan.
- Skim `guides/write-path-security.md` before your agent works in anyone else's
  repo, or ingests anything from messages or the web.
- Start a Tier 2 index only when finding entries by folder and search starts to
  hurt; `guides/tier2-index-and-sqlite-mirror.md` explains the trigger points.
- Revisit the categories after a month of real use and adapt them with
  `guides/adapting-the-categories.md`.
- When a procedure has recurred twice, read
  `guides/procedures-as-skills.md` and let the next consolidation pass
  propose compiling it into a skill under `skills/`. The three finished
  examples in `examples/skills-example/` show the target shape. Do not
  rush this: a skill compiled from a lesson seen once is a guess with a
  folder around it.

## The five mistakes to avoid from day one

1. Filing conclusions without evidence links. A finding with no evidence is an
   opinion wearing a uniform.
2. Marking things `settled` because they feel true. Use `assumed`. It is not a
   demotion; it is a label that protects you.
3. Editing an old entry when knowledge changes. Supersede it instead — the chain
   is the audit trail.
4. Deleting the losing side of a contradiction. Keep both sides in a contradiction
   entry until the disagreement is genuinely resolved.
5. Reading the whole wiki into every task. Briefings and context packages exist
   precisely so nobody — human or agent — has to.
