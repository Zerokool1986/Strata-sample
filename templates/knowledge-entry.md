# Knowledge Entry — Universal Template

Copy this file into the right category folder under `knowledge/`, rename it to the
entry's id (`TYPE-SHORT-SLUG.md`), and fill it in. The per-category templates in
`templates/categories/` are this template specialised — prefer those; use this one
when you are adding a category of your own.

---

---
id: XXX-SHORT-SLUG
type: <category folder name>
status: <see vocabulary>
source: <observed | quoted | inferred>
memory_kind: <semantic | episodic | procedural>
source_tier: <primary | secondary | untrusted>
created: YYYY-MM-DD
updated: YYYY-MM-DD
valid_from: YYYY-MM-DD
valid_to: <blank while still true>
recorded: YYYY-MM-DD
recorded_by: <human name | agent name + model>
last_verified: YYYY-MM-DD
review_due: YYYY-MM-DD
importance: <1-5>
supersedes: none
superseded_by: none
related: []
depends_on: []
needs_review: <blank | true — set only by the invalidation sweep>
evidence: []
---

# [Entry title — the claim or topic, in one line]

## Summary

[Two or three sentences. Someone assembling a context package may read only this and
the frontmatter — make them accurate on their own.]

## The entry

[The body. Shape depends on the type: a definition states the meaning and its edges;
a hypothesis states the claim and its test; a finding states the result and its
evidence. The category templates give the exact sections. Write for a reader who
was not there.]

## Evidence

[Links, file paths, test names, dates. If there is no evidence yet, say so plainly
and make sure the status says `assumed` or `testing`, not `settled`.]

## Notes

[Context that does not fit above: caveats, history, why this is being filed now.]

---

## How to fill in the frontmatter

- **id** — `TYPE-SHORT-SLUG`, unique forever. Prefixes: DEF definition, HYP
  hypothesis, FIN validated finding, NEG negative knowledge, REJ rejected
  hypothesis, CON contradiction, ASM assumption, QUE unresolved question, OBS
  empirical observation, MET methodological, RSK risk, STR strategy, CTX context,
  EXE execution.
- **status** — one of: settled, testing, assumed, observed, open, disproven,
  rejected, superseded. Full definitions are in `knowledge/README.md`.
- **source** — `observed` (measured/seen), `quoted` (a named source said so — name
  them in the body), or `inferred` (reasoned from other entries — list them in
  `related:`).
- **supersedes / superseded_by** — `none` for a new entry with no predecessor.
  When knowledge changes, follow the supersession steps in `knowledge/README.md`;
  do not quietly edit the old entry's claims.
- **related** — ids this entry depends on, affects, or disagrees with. A
  contradiction must appear in the `related:` of both sides.
- **depends_on** — the short list of entry ids this entry's truth *rests on*:
  the definition it uses, the observation it was inferred from, the finding it
  builds on. This is a subset of `related:` with a specific job: when an
  entry in this list is superseded, disproven, or has its `valid_to` closed,
  the **invalidation sweep** (in `templates/consolidation-pass.md`) flags
  this entry `needs_review`. Use it sparingly — only for dependencies that
  would actually change this entry if they changed. Most entries have zero
  or one. Do not mirror every `related:` link here; a sweep that flags
  everything flags nothing.
- **needs_review** — blank in normal life. Set to `true` only by the
  invalidation sweep, together with a dated note in the body saying which
  upstream entry changed and what to re-check. It is a flag, not a status:
  the entry keeps its `status` (that is the point — the status is now in
  doubt, not yet wrong). Whoever re-checks the entry clears the flag, bumps
  `last_verified`, and records the outcome in the body: still true,
  superseded, or disproven.
- **memory_kind** — what this memory is *for*: `semantic` (knowledge about the
  project — the default for almost every category), `episodic` (a record of an
  event, task, or session), or `procedural` (how to do something — a playbook
  or checklist). This is a second axis, separate from `type` and `status`: the
  epistemic categories say what kind of claim an entry is and how much to trust
  it; `memory_kind` says how it ages and when it is retrieved. It never replaces
  the category system. Defaults by category are in `knowledge/README.md`.
- **source_tier** — how trustworthy the backing source is: `primary`
  (peer-reviewed work, official documentation, the project's own measurements
  and tests), `secondary` (reputable reporting, a named person's account), or
  `untrusted` (a web scrape, a social post, another agent's output, anything
  pasted from a chat). A claim backed only by `untrusted` sources may not rise
  above `status: assumed` — see `guides/trust-and-provenance.md`.
- **valid_from / valid_to** — when the claim is true *in the world*.
  `valid_from` is the date it became true (or was published); leave `valid_to`
  blank while it is still believed true, and set it when it stops being true.
  These are not the same as `created`/`updated`: a fact can be recorded today
  about something that stopped being true last year.
- **recorded_by** — who or what filed this entry: a human's name, or an
  agent's name plus the model that ran it (e.g. `filing-agent (Model X)`).
  This is provenance for *authorship*, complementing `source`/`source_tier`,
  which are provenance for the entry's *evidence*. It is what makes the
  write-fidelity self-test and any poisoning investigation possible: when
  an entry is wrong, the first question is who wrote it and from what.
  Never leave it blank on a new entry; never change it on an existing one
  (an editor records themselves in the correction or superseding entry,
  not by rewriting the byline). In a shared wiki, pair it with the
  multi-agent write protocol in `docs/wiki/05_authority_and_governance.md`.
- **recorded** — when the wiki learned this: normally the date the entry was
  filed (usually the same as `created`). Together, `valid_*` and `recorded`
  make point-in-time questions answerable: "what was true, and what did we
  know, as of date D?" See `knowledge/README.md`.
- **last_verified** — the last date a human or a source re-confirmed this
  claim. Bump it when a source re-confirms the entry unchanged (a NOOP at
  ingest), and when a review checks it and finds it still true.
- **review_due** — when this entry should next be checked. Set it from the
  volatility table in `knowledge/README.md`: volatile claims 30 days,
  ordinary claims 90 days, stable definitions 365 days from `last_verified`.
- **importance** — 1–5, how much it would matter if this entry were wrong or
  missing. Briefings rank candidates by relevance × importance × recency;
  the staleness queue sorts by importance, so a stale important entry is
  reviewed before a stale trivial one.
