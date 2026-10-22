# Agent Briefing — Move the first reminder to 2 days before the due date

> Filled example, built with `templates/agent-briefing.md`. (The entry texts named
> here are in `knowledge/` in this worked example.)

## Task

Change Ledgerline's first payment reminder so it is sent 2 days **before** the
invoice's due date, instead of on the due date itself, and set up the comparison
that will judge the change.

**Done looks like:** new invoices get their first reminder at due-date-minus-2-days;
the comparison window and its start date are recorded. Nothing else about reminders
changes in this task.

## Why

The first reminder currently lands on the due date itself (DEF-OVERDUE-30:
due date = send + 30 days), so a client who pays on first prompting is
already late. Moving the prompt earlier only matters if clients actually see
email quickly — which is an assumption, not a measurement
(ASM-CLIENTS-CHECK-EMAIL). This task makes the timing change and records
the window it will be judged over.

## Relevant knowledge — pulled, with status

| Entry id | Status | Why it matters here |
|---|---|---|
| `ASM-CLIENTS-CHECK-EMAIL` | assumed | The whole idea leans on clients seeing email quickly — unmeasured |
| `DEF-OVERDUE-30` | settled | The due date this task counts from (send + 30 days) |

## Assumptions in play

- `ASM-CLIENTS-CHECK-EMAIL` — if clients do not read email within ~2 days, a
  2-day-early reminder is no earlier in any sense that matters. If the comparison
  fails, this assumption is investigated before the wording is.

## Negative knowledge and rejected paths

- `NEG-PDF-ONLY-INVOICES` (disproven) — the reminder must keep amount, due date,
  and payment link in the email body. Not directly this task's surface, but the
  reminder template must not be "tidied" into an attachment-only form.

## Boundaries

- Do not change the due-date definition or the overdue classification.
- Do not change reminder wording in this task (timing only), so the comparison
  has one variable.
- The comparison record is filed as an observation when its window closes —
  not by this task, which only sets the window up.

## What to file back afterwards

- File nothing as a finding yet. A shipped reminder is not a result.
- Note on this briefing which entries were used, for the audit trail.

## Open questions before starting

- None blocking. (Count from the current definition, DEF-OVERDUE-30;
  DEF-OVERDUE-14 is superseded and stays in the store for history.)
