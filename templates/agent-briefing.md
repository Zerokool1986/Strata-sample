# Agent Briefing — [Task Name]

> One briefing per task, filled in **before** work starts. It is the front door to
> the task's context package: this page decides what knowledge the task will use,
> what it must respect, and what it must produce for the store afterwards.
> Keep it to one page where you can.

## Task

[What is to be done, in plain language.]

**Done looks like:** [the observable end state — a test passing, a behaviour
changed, a document written. If you cannot describe done, the task is a question,
not a task: file it as an unresolved_question first.]

## Why

[The reason for the task and the decision or goal it serves. Link the wiki
document or knowledge entry that motivates it instead of restating it.]

## Relevant knowledge — pulled, with status

[List only the entries this task needs. Each line: the id, its status, and one
line on why it is here. This list is the index of the context package.]

| Entry id | Status | Why it matters here |
|---|---|---|
| `DEF-…` | settled | [reason] |
| `ASM-…` | assumed | [reason — flagged because this task leans on it] |
| `NEG-…` | disproven | [the retired approach this task must not repeat] |

## Assumptions in play

[The assumptions this task depends on, by id. If one turns out false mid-task,
stop and re-brief — do not improvise around a broken assumption.]

## Premise check — dependencies of what you are relying on

[For each settled entry this briefing pulls: glance at its `depends_on` list.
Are those entries still current — none superseded, disproven, or
validity-closed since? Does the pulled entry carry a `needs_review` flag
from the invalidation sweep? List anything doubtful here, by id, with its
upstream problem. Relying on an entry whose premise moved is how stale
knowledge gets used with fresh confidence; this section exists so the doubt
is written down before the work starts, not discovered after. If every
dependency is clean, write "premises clean" — the check still happened.]

## Negative knowledge and rejected paths

[Approaches close to this task that were already tried and failed, or considered
and rejected. One line each, with the entry id. This section existing is what
stops the same idea being rebuilt every few months.]

## Contradictions to respect

[Open contradictions touching this task, by id, and the working rule until they
are resolved — for example "quote the behaviour the code implements, flag the
document as wrong". If there are none, write "none known".]

## Boundaries

[What not to touch. What needs approval first. Irreversible actions to avoid.
Anything frozen, locked, or someone else's in-flight work.]

## What to file back afterwards

[The expected deposits to the store, named in advance where possible: e.g.
"the comparison result as a validated_finding or negative_knowledge entry",
"the status of HYP-… updated to testing / settled / disproven", "any new
question opened, as an unresolved_question". The checklist itself is
`templates/end-of-task-filing.md`.]

## Open questions before starting

[Anything unresolved that could change the approach. "None" is a good answer.
Guessing is not.]
