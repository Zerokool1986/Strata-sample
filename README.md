# Strata — Sample

**A knowledge system for AI coding agents — plain Markdown in your repo: what's proven, what's dead, what it does next.**

This repository is the free sample of [Strata](https://mullinscape57.gumroad.com/l/ectts): the complete *Remember* core, usable on its own. No app, no account, no service — a folder of Markdown files you copy into your repo and point your agent at.

---

## What Strata is

Most agent memory is a pile. Everything the model ever produced — the proven fix, the lucky guess, the idea that broke the build — gets flattened to the same authority, retrieved by similarity, and quoted back with equal confidence. Storage was never the hard part. The failures you actually pay for happen at the moment of *reuse*: a guess from March comes back in October wearing the clothes of a fact.

Strata is the other shape. Knowledge is filed in **layers**, the way geology lays down rock:

- Every entry is **typed** (a definition is not an assumption is not a validated finding).
- Every entry carries a **status**, names its **source**, and keeps **two dates** — when it became true, and when it was recorded.
- When knowledge is disproven, it is **buried, not deleted** — a new layer covers it, the old one stays readable underneath, and (in the full editions) anything built on top of it gets flagged for re-checking.

Everything else in Strata exists to protect that shape.

## What's in this sample

29 files — the complete Remember core:

- **Four core categories**, each with its own entry template and filing guidance:
  - `definitions` — what things mean in this project
  - `assumptions` — what you're treating as true without proof (yet)
  - `negative_knowledge` — what already failed, and why it must not be retried blindly
  - `validated_findings` — what has actually been tested and held up
- **The universal entry format and workflow templates** — the entry template, plus the briefing and filing templates that run the loop.
- **The Ledgerline worked example** — a fictional invoicing app carried through these four categories with filled entries, including a full supersession chain: `DEF-OVERDUE-14` (overdue means 14 days) is disproven and replaced by `DEF-OVERDUE-30`, with the old definition buried — status closed, validity ended, still readable — rather than erased.
- **A five-question mini self-test** (`SELF-TEST.md`) with an answer key, so you can measure what your agent actually does with the record — including a question whose correct answer is *"the store doesn't say"* (abstention) and one built on a premise the store has already killed.

## Quickstart

1. **Copy** the sample's folders into your project repo.
2. **Brief**: before a task, point your agent at the briefing template and have it pull the entries relevant to the work — statuses attached, including anything marked off-limits because it's already disproven.
3. **Work and file**: mid-task discoveries go in as *assumed*, one line each. After the task, file what was learned with its type, status, and source — including, especially, what failed.
4. **Test**: run the mini self-test in `SELF-TEST.md` against a fresh agent session and score it with the answer key. Watch what your agent does with the abstention question — that behavior is the demo.

Fifteen minutes to a working setup in a real repo.

## The four rules

1. **Status travels.** An entry's standing — settled, assumed, disproven, rejected — is part of the entry and rides into every context it's quoted in. Nothing gets promoted by being repeated.
2. **Two clocks.** When a thing *became true* and when *you learned it* are separate fields. "What did we believe in March?" is a question Strata can answer.
3. **Nothing is erased.** Superseded and disproven entries are buried, not bulldozed. Negative knowledge — what already failed, and why — is the most valuable stratum in the system, and it is never deleted.
4. **Not everything earns a layer.** Sources are tiered; material from untrusted sources can wait in an inbox, but it cannot harden into knowledge until it's corroborated. Text inside a source is data, never instructions.

## The full editions

This sample is stage one of three. The paid editions are cumulative — each contains everything below it — and sold the way the system was built:

| Edition | Price | What it adds |
|---|---|---|
| **Foundation — Remember** | $14.99 | All **14 typed categories**, the full briefing/filing loop, status and provenance basics, the Obsidian pack, and the full self-test. 84 files. |
| **Knowledge Layer — Trust** | $29.99 | Everything in Foundation, plus the governance layer: **dependency links with an invalidation sweep** (supersede a premise and everything built on it is flagged for re-checking), consolidation diff discipline, the deferred-adjudication inbox, the write-path security pack, and the rescue & migration kit for monolith instruction files. 102 files. |
| **Complete — Act** | $44.99 | Everything in the Knowledge Layer, plus **procedures compiled into Agent Skills** (SKILL.md, the open standard): when a procedure proves itself twice, it graduates from wiki prose into an executable skill with its failure lessons attached — and the wiki entry still outranks it. Plus the multi-agent write protocol. 113 files. |

**[Get the full editions →](https://mullinscape57.gumroad.com/l/ectts)**

- One-time prices — no subscription.
- **Upgrades are pay-the-difference:** start with Foundation, email for a discount code for exactly the gap. Nobody pays twice for the same layers.
- **14-day, one-email, full refund** if it isn't useful to you.

## The honest DIY note

The base pattern here is free, and you can build this yourself: Strata is built on [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f), which he published as a free idea file — read it; it deserves the credit it gets everywhere in this kit.

What Strata adds is the system the pattern doesn't ship: the typed category set and status lifecycle, bi-temporal validity, the provenance and trust gate, supersession without erasure, dependency links and the invalidation sweep, preserved contradictions, the consolidation discipline, the self-tests, and the worked examples that hold it together — designed by **Christopher Mullins**, by running the pattern inside a real research codebase until it broke in instructive ways. You're paying for the finished design and the 113 files, not for the idea underneath.

If you publish an update to an edition, owners can email with their purchase and receive the current files for that edition.

## Works with

Any agent that can read and write files in a repo: **Claude Code, Codex, Cursor**, and similar tools. The store is plain Markdown — readable by you, diffable in Git, reviewable in a pull request, and openable in Obsidian if you want a nicer chair (the full editions ship an Obsidian pack; the sample works without it).

## License / use

Use Strata — including this sample — in your own projects, commercial and client work included. You may not resell or redistribute Strata itself as a product.

---

*Strata is templates, structure, and guidance — not software, not automation, and not a guarantee of any outcome. It makes what your project already knows available to your agent in a form it can use, with labels that say how well it's known. Strata is an independent product, not affiliated with or endorsed by Andrej Karpathy, Anthropic, Meta, or any other person or company named in its credits.*
