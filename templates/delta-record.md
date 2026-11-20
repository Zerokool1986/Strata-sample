# Delta Record, [short name]

> File one record per change to the store: a supersession, a disproof,
> a contradiction resolved, a summary rewritten, or knowledge moved
> (for example from a repo store into the home store). A delta names
> exactly which facts were added, modified, or removed, so a reviewer
> can see the change to knowledge the way a diff shows a change to
> code. File it in `deltas/` as `DLT-SHORT-SLUG.md` at the time of the
> change, and link it from the entries it touches (in their
> `evidence:`). A delta is a log of a change, not a category of
> knowledge: it records what happened, it does not hold a claim.
>
> File a delta whenever a supersession, disproof, or contradiction
> resolution changes the store, and whenever a consolidation proposal
> that changes a summary or `CORE.md` is applied. If the change is
> trivial (a typo fix, a date bump on re-verification), say so in one
> line in the pass record instead; do not file a delta for it.

- Date: [YYYY-MM-DD]
- Filed by: [human name | agent name + model]
- Change: [supersession | disproof | contradiction resolved | summary rewritten | move | other]
- Reason: [one or two sentences: why this change, and what evidence or decision drove it]

## Added

- [entry id, one line each: what was added and why]

## Modified

- [entry id, what changed in it, before and after in one line each]

## Removed

- [entry id, what was removed from current standing and why.
  Removal here means superseded, disproven, or archived, never silently
  deleted: a removed entry stays in the store with its status set, and
  this line says where it went.]

## Entries affected

- [entry ids this change touches, including dependents flagged by the
  invalidation sweep, if any]

## Approval

- Approved by: [human name, or "consolidation pass of YYYY-MM-DD"]
- [If this delta was proposed in a consolidation pass, link the
  proposals file and the proposal number.]
