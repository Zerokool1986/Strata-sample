# End-of-Task Filing — [Task Name]

> Run this checklist before any task is called done. It takes about five minutes
> and it is the step that keeps the wiki alive: tasks that do not file back are
> how knowledge stores quietly go stale and die. File entries using
> `templates/categories/` (or the universal template), with honest statuses.

## 1. What was learned

- [ ] New facts or results filed — as `validated_finding` if tested,
      `empirical_observation` if raw, `hypothesis` if still a claim.
- [ ] Each new entry has evidence linked, or explicitly says there is none yet.

## 2. What changed status

- [ ] Hypotheses this task tested: status moved from `testing` to `settled`
      (promote via a validated finding) or `disproven` (file the negative
      knowledge entry — what was tried, what happened, why).
- [ ] Assumptions this task leaned on: confirmed (say how), broken (supersede
      and flag dependents), or still assumed (no change — that is a valid result).
- [ ] Definitions or methods this task proved wrong or incomplete: superseded
      with new entries, old ones marked `superseded`, never silently edited.

## 3. What was tried and failed

- [ ] Every failed approach from this task that a future agent might retry has a
      `negative_knowledge` entry: what was tried, context, what happened, the
      conditions under which a retry would be legitimate.

## 4. What opened up

- [ ] New questions filed as `unresolved_question`, each stating what information
      would close it.
- [ ] New risks filed as `risk_knowledge` if a failure mode became visible.
- [ ] New contradictions filed as `contradiction` if this task's results
      disagree with an existing entry. **Both sides stay.**

## 5. Links and housekeeping

- [ ] New entries linked (`related:`) to the entries they depend on, affect,
      confirm, or contradict.
- [ ] The task's briefing annotated with what was actually filed (entry ids),
      so the loop is auditable.
- [ ] No entry in this task contains secrets, credentials, or personal data.
- [ ] Nothing was deleted. (Deletion is not a filing action in this system.)

## 6. Promote the lesson — the episodic → semantic/procedural rule

If this task produced a session record (`memory_kind: episodic`, from
`templates/categories/episodic-session-record.md`), its lessons are
candidates, not knowledge. A lesson is **promoted** when it generalises
beyond this one task. It has exactly two destinations:

- **Semantic** — it becomes a claim in an epistemic category: a validated
  finding if it was tested, negative knowledge if it is a way of failing,
  a definition if it settles a term. The new entry links the session record
  in `evidence:`.
- **Procedural** — it changes how work is done: a playbook edit, a checklist
  step, an AGENTS.md rule. The procedure is what gets edited; the session
  record is linked as the reason.

One rung above procedural sits **compilation into a skill** (v1.3): a
procedural entry whose lesson recurs *again* after promotion becomes a
candidate for an Agent Skill under `skills/`. That step is never taken
inside a task filing — it is proposed and approved in the consolidation
pass (step 3 there; `guides/procedures-as-skills.md`). Filing's job is
only to make the recurrence visible: link the records that show it.

A lesson seen once *may* be promoted if the cost of relearning it is high.
A lesson seen twice **must** be — the second occurrence is the evidence.
Lessons not promoted stay in the record, to be weighed at the consolidation
pass; nothing is promoted silently inside the record itself.

Before deciding, answer these two prompts in the session record:

- [ ] **Post-mortem (say it as an instruction):** *What would you do
      differently, stated as an instruction to a future self?* Not "the API
      was slow" but "next time, check the mail authentication record before
      reading send logs." A lesson that cannot be phrased as an instruction
      is usually an observation — file it as one.
- [ ] **Contrast (failed vs. successful):** *Compare this attempt with the
      last similar task that went the other way.* If this one failed and a
      previous one succeeded (or the reverse), the **difference** between
      the two attempts is the lesson — file that, not a summary of either
      attempt alone. If there is no comparable attempt, say so; the
      contrast gets its chance at the consolidation pass, when more records
      exist.

- [ ] Each promoted lesson filed or procedure edited, with its destination
      named in the session record.
- [ ] The record itself left as the episodic evidence — promotion copies the
      lesson out; it does not move or upgrade the record.

## If nothing was learned

Say so, in one line on the briefing: "No knowledge changes from this task."
That is a legitimate outcome — and writing it down is still filing.
