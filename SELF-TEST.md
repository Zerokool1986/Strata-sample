# Mini Self-Test — Five Questions for the Worked Example

## How to run this

Open a **fresh agent session** (one that has not seen this file's answer key)
with access to nothing but the `examples/worked-example/` folder in this
sample. Ask the five questions below, exactly as written. Then grade the
answers against the key at the bottom.

The point is not trivia. Each question tests one ability a knowledge store
exists to give an agent: recalling what is settled, tracking what changed,
knowing how much to trust a claim and why, refusing to repeat what already
failed — and saying "not in the store" instead of inventing an answer.

## The questions

1. **Recall.** According to the store, when does an invoice count as
   overdue, and how is the due date defined?

2. **Update / supersession.** Did Ledgerline always use that rule? If it
   changed, what was the earlier rule, why was it replaced, and what
   happened to the old entry?

3. **Provenance.** The store says most clients read invoice email within
   about 2 days. How well-established is that claim — what is its status,
   how was it arrived at, and what evidence backs it?

4. **Negative knowledge.** A teammate proposes simplifying invoice emails:
   empty body, everything — amount, due date, payment link — inside the PDF
   attachment only. What does the store say about that idea?

5. **Abstention.** Which payment processor does Ledgerline use to collect
   payments, and what fees does it charge?

---

## Answer key

**Do not show this section to the session being tested.**

1. **Recall.** An invoice counts as overdue **30 days after it was sent**;
   the due date is the send date plus 30 days. Source: `DEF-OVERDUE-30`,
   status `settled`. (Bonus: reminders before the due date are "upcoming",
   after it "overdue", with different wording.)

2. **Update / supersession.** No. The earlier rule was **14 days**
   (`DEF-OVERDUE-14`, set at project start by assumption). It was replaced
   on 2026-03-04 because observed payment data (median payment at 23 days)
   showed a 14-day line classified most normal invoices as late. The old
   entry was **not edited or deleted**: it is kept with status `superseded`
   and `superseded_by: DEF-OVERDUE-30`, as the historical record.

3. **Provenance.** Weakly established, and labelled as such. Entry
   `ASM-CLIENTS-CHECK-EMAIL` has status **`assumed`** and source
   **`inferred`**, with **no evidence attached** — it rests on support
   conversations and consistency with the payment pattern, and the entry
   itself says it was never measured. A correct answer reports the claim
   *and* its low standing; an answer that presents the 2-day figure as a
   measured fact fails this question even if the number is right.

4. **Negative knowledge.** It was tried and it failed. `NEG-PDF-ONLY-INVOICES`
   (status `disproven`) records that attachment-only invoice emails were
   missed or distrusted by clients — lost behind spam filters and mobile
   mail, and useless when forwarded to a bookkeeper. The standing
   instruction is that amount, due date, and payment link stay in the email
   body; there are no retry conditions for the original approach.

5. **Abstention.** **Not in the store.** No entry in the worked example names
   a payment processor or any fees. The correct answer is to say exactly
   that. Any named processor, fee schedule, or confident guess is a
   fabrication and fails the question — this is the most important of the
   five.

## What this is a miniature of

This is a five-question cut of the self-test discipline the full kit ships:
a 24-question test (with its template, so you write questions about *your*
store, not someone else's) spanning recall, knowledge updates, temporal
reasoning, multi-hop questions, contradiction handling, provenance, and
abstention. When the full v1.3 kit was itself tested end to end, a fresh
agent session with access only to the shipped worked example scored **8/8**
on an eight-question run — including both trap questions: one whose answer
was not in the store, and one built on a false premise it had to correct
before answering.
