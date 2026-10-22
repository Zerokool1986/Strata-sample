# The Knowledge Store — Categories Index

This folder is **Tier 1**: the canonical memory of the project. Plain Markdown, in
Git, one entry per file. If this folder and a tool disagree, this folder is right.

## How entries work

Every entry is a Markdown file with YAML frontmatter (see
`templates/knowledge-entry.md`):

- `id` — the stable identifier, also the file name: `TYPE-SHORT-SLUG.md`
  (for example `NEG-PDF-ONLY-INVOICES.md`). Never reuse an id.
- `type` — the category (folder) the entry lives in.
- `status` — how well this is known (vocabulary below). **Required.**
- `source` — how it is known: `observed`, `quoted`, or `inferred`. **Required.**
- `created` / `updated` — dates. Update `updated` whenever the file changes.
- `supersedes` / `superseded_by` — the supersession chain (below).
- `related` — ids of entries this one depends on or affects.
- `depends_on` — the few ids this entry's truth rests on (below). The
  invalidation sweep reads this field; nothing else does.
- `needs_review` — blank, or `true` when the sweep has flagged this entry
  because something it depends on changed. A flag, not a status.
- `evidence` — links or paths backing the entry: tests, logs, documents, entries.
- `memory_kind` — what the memory is for: `semantic`, `episodic`, or
  `procedural`. A second axis, explained below. Most entries never need it
  typed by hand — it follows from the category.
- `source_tier` — how trustworthy the backing source is: `primary`,
  `secondary`, or `untrusted`. See "Source tiers" below.
- `valid_from` / `valid_to` — when the claim is true in the world (below).
- `recorded` — when the wiki learned it (below).
- `recorded_by` — who or what filed it: a human's name, or an agent's name
  plus model. Authorship provenance (v1.3), complementing `source_tier`'s
  evidence provenance; filled at filing time and never edited afterwards.
  The shared-wiki protocol that pairs with it is in
  `docs/wiki/05_authority_and_governance.md`.
- `last_verified` / `review_due` / `importance` — the staleness fields
  (below). `importance` is 1–5: how much it matters if this entry is wrong.

| Status | Meaning | How an agent treats it |
|---|---|---|
| `settled` | Tested or formally agreed; the project relies on it | Treat as true unless new evidence appears |
| `testing` | A test is running or designed and not yet concluded | Do not rely on it; do not contradict it either |
| `assumed` | Believed, load-bearing, untested | Usable, but flag it whenever a decision leans on it |
| `observed` | Recorded from measurement or report; not yet interpreted | Cite it as data, never as a conclusion |
| `open` | A question or contradiction not yet resolved | Do not silently pick an answer |
| `disproven` | Tested and shown false | Do not retry or re-argue without new evidence |
| `rejected` | Considered and set aside on recorded reasoning | Do not re-propose without addressing the reasoning |
| `superseded` | Replaced by a newer entry named in `superseded_by` | Use the replacement; keep this file for history |

Attribution (`source:` in the frontmatter) says *how* the entry is known, separate from its status:

- `observed` — measured, logged, or directly seen. Strongest.
- `quoted` — reported by a named source (a user, a document, a support thread). Record who, in the body.
- `inferred` — reasoned from other entries. Weakest; an inferred entry should name the entries it was inferred from.

An entry can be `status: settled` only if its source is `observed`, or it is a definition the project has formally agreed. A guess wearing a settled label is the single most damaging thing in a wiki like this.

## Supersession — how knowledge changes

Knowledge changes by **replacement, not rewriting**:

1. Write the new entry. Set its `supersedes:` to the old entry's id.
2. In the old entry, set `superseded_by:` to the new id and change its status to
   `superseded`. Do not otherwise edit its body — it is now a historical record.
3. Update anything that linked to the old entry to consider the new one.

The chain is the project's memory of *changing its mind*, which is exactly the part
a flat wiki loses. A complete example chain is in `examples/worked-example/`
(`DEF-OVERDUE-14` → `DEF-OVERDUE-30`).

## Dependency links — and the invalidation sweep

Dependency links exist in the entry format: `depends_on:` declares the few
entries this entry's truth rests on (defined with the other fields, above).
When one of those entries changes, the entries built on it need to hear
about it. That is the **invalidation sweep** — the pass that flags everything
built on a changed premise, so it gets re-checked instead of going quietly
stale. The sweep is part of the Knowledge Layer (Trust) edition and is
documented there; this edition defines the links it reads.

## Contradictions

When two current entries disagree, **neither wins silently**. File a
`contradiction/` entry recording both sides and their evidence, link it from both
entries' `related:`, and leave the disagreement `status: open` until it is resolved
by evidence or by an explicit decision — which is then recorded in the contradiction
entry, and the losing entry is superseded.

## Two time axes — and asking "as of" a date

Entries carry two different times, and confusing them causes real errors:

- **Valid time** — `valid_from` / `valid_to`: when the claim is true *in the
  world*. "The free plan allows 10 invoices" became true on the launch date
  and stopped being true the day the limit changed — whatever day anyone
  wrote it down.
- **Record time** — `recorded` (and `created`): when *the wiki learned it*.

When a new claim replaces an old one, prefer setting the old entry's
`valid_to` and superseding it, over deleting it. The old entry then remains a
true statement about its own window.

That makes a third query mode possible, alongside normal search:

> **Point-in-time ("as of date D") query.** Answer using only entries with
> `valid_from` on or before D and (`valid_to` blank or after D). Say which
> entries you excluded because they were not yet valid, no longer valid, or
> only recorded after D. If the question is about what the project *believed*
> on date D rather than what was true, filter on `recorded` instead — and say
> which axis you used.

One practical consequence: before filing a `contradiction`, compare the two
claims' validity windows. If the windows do not overlap, it is usually not a
contradiction — it is "true then, not now", and the fix is a `valid_to` plus a
supersession, not a dispute.

## memory_kind — a second axis (it does not replace the categories)

The categories and statuses answer: *what kind of claim is this, and how much
should it be trusted right now?* A second, independent question is: *what is
this memory for, how does it age, and when is it retrieved?* That is
`memory_kind`, borrowed from cognitive architectures for language agents:

| memory_kind | What it holds | How it ages | Kit defaults |
|---|---|---|---|
| `semantic` | Knowledge about the project: terms, facts, findings | By supersession, not by time | definition, validated_finding, hypothesis, assumption, contradiction, unresolved_question, empirical_observation, context_knowledge, risk_knowledge, strategy_knowledge, methodological_knowledge, negative_knowledge, rejected_hypothesis |
| `episodic` | Records of events: what was attempted, in what order, with what result, on what date | By decay: summarised upward at the consolidation pass, then archived | Session/task records filed from `templates/categories/episodic-session-record.md` (a log area, not a claim category) |
| `procedural` | How to do things: playbooks, checklists, operating rules | Revised when a task shows the procedure did not work as written | execution_knowledge entries that are procedures; `templates/AGENTS.md` itself is the project's core procedural memory |
| `working` | The material assembled for the task in hand | Exists for one task, then is filed back or discarded | Agent briefings and context packages — never store them as knowledge entries in raw form |

**This axis does not replace the epistemic categories.** A session record and
a validated finding are different kinds of memory *and* different levels of
trust; collapsing either axis into the other loses information the agent
needs. Keep both labels.

The point of the axis is the **promotion rule**: episodic lessons do not stay
raw logs forever. At filing or consolidation time, a lesson that generalises
is promoted — to a `semantic` entry (a finding, a piece of negative knowledge)
or to a `procedural` change (a playbook or AGENTS.md edit). The end-of-task
filing template carries the exact prompts for this.

## Source tiers

`source:` says how an entry is known; `source_tier:` says how much the source
itself can be trusted:

- `primary` — peer-reviewed or official documentation, the project's own
  measurements, tests, and records, a decision the project itself made.
- `secondary` — reputable reporting, a named person's account, a well-kept
  third-party document.
- `untrusted` — web scrapes, social posts, other agents' output, pasted chat
  transcripts, anything whose origin cannot be checked.

**Quarantine rule:** a claim backed *only* by untrusted sources enters at
`status: assumed` at best, and cannot be promoted to `settled` until a
higher-tier source or a human corroborates it. Full rules — the inbox gate
for external content, the provenance lint, and why any of this is necessary —
are in `guides/trust-and-provenance.md`.

## Staleness — verified dates, review dates, importance

Nothing in this store announces when it has gone stale, so each entry carries
its own schedule:

- `last_verified` — when the claim was last re-confirmed.
- `review_due` — set from `last_verified` by how fast this kind of claim
  changes:

  | Volatility | Examples | Review after |
  |---|---|---|
  | Volatile | Prices, limits, platform rules, third-party behaviour | 30 days |
  | Ordinary | Methods, context, most findings | 90 days |
  | Stable | Definitions, settled invariants, historical facts | 365 days |

- `importance` (1–5) — a stale *important* entry is reviewed before a stale
  trivial one.

Entries past `review_due` form the **staleness queue**. Working the queue is
part of the consolidation pass, documented in the Knowledge Layer (Trust)
edition. Each queued entry gets one outcome: re-verified (bump both dates),
superseded, disproven — or archived.

**Archive, don't delete.** Decay applies to session records (summarised, then
archived) and to retrieval priority (briefings load settled + recent +
important first). It never applies to the existence of negative knowledge,
rejected hypotheses, or disproven entries: their whole value is that they were
falsified, and deleting them invites a repeat. Deletion is for duplicates and
outright errors only, and Git history keeps even those recoverable.

## The categories

### `definition/` — Definition

**File it here if:** a term, invariant, or interface has a settled meaning the whole project should share.

**Not here if:** the meaning is still being debated (use hypothesis or unresolved_question), or it is a how-to (use execution_knowledge).

Template: `templates/categories/definition.md` · Example: `DEF-INVOICE` (in `examples/worked-example/`).

### `hypothesis/` — Hypothesis

**File it here if:** the project is actively testing a claim and can say what result would confirm or refute it.

**Not here if:** nobody is testing it and there is no test planned (use assumption), or the test already finished (use validated_finding or negative_knowledge).

Template: `templates/categories/hypothesis.md` · Example: `HYP-REMINDER-TIMING` (in `examples/worked-example/`).

### `validated_finding/` — Validated finding

**File it here if:** a claim was tested, the test is recorded, and the result held up.

**Not here if:** the evidence is a single anecdote (use empirical_observation), or the test cannot be described (keep it a hypothesis).

Template: `templates/categories/validated-finding.md` · Example: `FIN-PAYMENT-LINK` (in `examples/worked-example/`).

### `negative_knowledge/` — Negative knowledge

**File it here if:** something was tried, in practice, and did not work — and a future agent or person might plausibly try it again.

**Not here if:** it was rejected on reasoning alone without being tried (use rejected_hypothesis), or it failed for a one-off external reason that says nothing about the approach.

Template: `templates/categories/negative-knowledge.md` · Example: `NEG-PDF-ONLY-INVOICES` (in `examples/worked-example/`).

### `rejected_hypothesis/` — Rejected hypothesis

**File it here if:** a claim or approach was seriously considered and set aside on stated reasoning, without being run as a full test.

**Not here if:** it was actually tried and failed (use negative_knowledge), or it is merely unpopular with no reasoning recorded.

Template: `templates/categories/rejected-hypothesis.md` · Example: `REJ-AUTOMATIC-LATE-FEES` (in `examples/worked-example/`).

### `contradiction/` — Contradiction

**File it here if:** two entries, documents, or observations in the project disagree and both are still on record.

**Not here if:** one side is simply wrong and already corrected (supersede it instead), or there is a disagreement but nothing written down yet (write the entries first).

Template: `templates/categories/contradiction.md` · Example: `CON-PAYMENT-TERMS` (in `examples/worked-example/`).

### `assumption/` — Assumption

**File it here if:** the project is relying on something that has not been tested, and work would change if it turned out false.

**Not here if:** it has been tested (promote it to validated_finding or demote it to negative_knowledge), or nothing depends on it.

Template: `templates/categories/assumption.md` · Example: `ASM-CLIENTS-CHECK-EMAIL` (in `examples/worked-example/`).

### `unresolved_question/` — Unresolved question

**File it here if:** a question is open, it matters, and the project can say what information would close it.

**Not here if:** the answer is already recorded somewhere (link that entry instead), or the question is rhetorical.

Template: `templates/categories/unresolved-question.md` · Example: `QUE-MULTI-CURRENCY` (in `examples/worked-example/`).

### `empirical_observation/` — Empirical observation

**File it here if:** something was measured, seen, logged, or reported, and the raw observation is worth keeping before any interpretation.

**Not here if:** an interpretation or conclusion (file the conclusion as a finding and link this observation as evidence), or a guess about what happened.

Template: `templates/categories/empirical-observation.md` · Example: `OBS-LATE-PAYMENTS` (in `examples/worked-example/`).

### `methodological_knowledge/` — Methodological knowledge

**File it here if:** the project has a way of doing something — testing, measuring, reviewing — that is a method, not a fact.

**Not here if:** it is a settled term (use definition) or a one-off command (use execution_knowledge).

Template: `templates/categories/methodological-knowledge.md` · Example: `MET-BEFORE-AFTER-COMPARISON` (in `examples/worked-example/`).

### `risk_knowledge/` — Risk knowledge

**File it here if:** a failure mode is known or credibly suspected, with a cost if it happens and something that reduces it.

**Not here if:** it already happened and the lesson is about the failed attempt itself (use negative_knowledge), or it is a vague worry with no failure mode you can describe.

Template: `templates/categories/risk-knowledge.md` · Example: `RSK-EMAIL-DELIVERABILITY` (in `examples/worked-example/`).

### `strategy_knowledge/` — Strategy knowledge

**File it here if:** the project has chosen an approach — a plan, a direction, a deliberate trade-off — and the reasoning should survive the people who chose it.

**Not here if:** it is a task or a ticket (plans live here, tasks live in the tracker), or it is a settled fact (use validated_finding).

Template: `templates/categories/strategy-knowledge.md` · Example: `STR-REMINDERS-FIRST` (in `examples/worked-example/`).

### `context_knowledge/` — Context knowledge

**File it here if:** something about the world outside the project — users, market, platform, season, rules — changes how other entries should be read.

**Not here if:** it is internal to the project (file it in its real category), or it is permanent and definitional (use definition).

Template: `templates/categories/context-knowledge.md` · Example: `CTX-FREELANCER-YEAR-END` (in `examples/worked-example/`).

### `execution_knowledge/` — Execution knowledge

**File it here if:** operational know-how — a command, an environment quirk, a procedure — that cost someone time once and should never cost that time again.

**Not here if:** it is a method for evaluating or testing (use methodological_knowledge), or it is secret (passwords and keys never go in the wiki).

Template: `templates/categories/execution-knowledge.md` · Example: `EXE-SEED-DEMO-DATA` (in `examples/worked-example/`).


## Filing rules for every category

1. **One claim per entry.** If you are writing "and also…", it is probably two entries.
2. **Short.** Most entries should fit on one screen. Long analysis belongs in a
   document; the entry records the claim, the status, and the link.
3. **Date and attribute everything.** No undated, sourceless entries.
4. **Link, don't copy.** Entries reference each other and reference evidence;
   they do not paste each other's contents.
5. **Never delete a disproven or rejected entry.** It is the guardrail that stops
   the next person (or agent) from repeating it.
6. **No secrets.** Credentials, tokens, and personal data never go in an entry.
