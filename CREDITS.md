# Credits

This kit builds on ideas published by other people. This page says exactly which ideas,
and what this kit itself contributes.

## The LLM Wiki pattern — Andrej Karpathy

The base pattern used here — a project wiki made of plain Markdown files, maintained by a
large language model under instructions kept in the repository (in his framing: raw
sources, the wiki itself, and a schema/instructions layer) — comes from Andrej Karpathy's
"LLM Wiki" idea file, published as a public GitHub gist in April 2026.

That pattern is free for anyone to use, and many implementations of it exist. This kit
credits the pattern to him clearly because it is his idea. **No text from the gist is
reproduced in this kit.** Every document here was written for this kit, and the parts
below are this kit's own contribution.

## Memory layers — Meta FAIR (conceptual inspiration only)

The layered way this kit organises memory — a small, always-present layer; a larger store
underneath; and bounded, task-specific assembly on top — was conceptually inspired by:

> Vincent-Pierre Berges, Barlas Oğuz, Daniel Haziza, Wen-tau Yih,
> Luke Zettlemoyer, Gargi Ghosh, et al., *Memory Layers at Scale*, Meta FAIR,
> December 2024. arXiv:2412.09764.

That paper is about memory layers *inside* large language models. This kit does not
implement it, reproduce its methods, or claim its results. The inspiration is only the
general shape — different kinds of memory at different depths, with cheap access to the
small layer and deliberate access to the large one — applied to files in a repo instead
of parameters in a model.

## What this kit adds (its own work)

**Strata** — the name this kit ships under from v1.2 — and the epistemic
layer described here were designed by **Christopher Mullins**, building on
the credited pattern and research. The contributions:

- The 14 typed epistemic categories and the rules for choosing between them
  (notably: hypothesis vs. assumption, negative knowledge vs. rejected hypothesis,
  observation vs. finding).
- The status and attribution vocabulary on every entry, and the rule that inferred
  knowledge can never present as settled.
- Supersession chains and contradiction preservation as first-class workflows.
- The pre-task briefing, context package, and end-of-task filing templates that turn
  a wiki from an archive into a working loop.
- The worked example, guides, and wiki document templates.
- From v1.3: the decision of *which* procedures graduate to skills, the
  promote-to-skill discipline (compilation as a reviewed consolidation
  act, never an in-task one), and the precedence rule that keeps the wiki
  the source of truth over its compiled skills — the format is the open
  standard's; the governance of it is this kit's.

## The v1.1 research additions

Version 1.1 adds eight features, each translated from a published paper or
system into plain Markdown templates. What was borrowed is the *mechanism as
an idea* — a field, a table, a workflow step — never text, code, or results.
Where a system's real contribution is software, the kit says so and ships
only the governance layer.

**Time and ingest (addition 1)**
- Rasmussen et al. (Zep AI), *Zep: A Temporal Knowledge Graph Architecture
  for Agent Memory*, arXiv:2501.13956 (2025). Borrowed: the two time axes —
  valid time vs. record time — as `valid_from`/`valid_to`/`recorded`
  frontmatter, and invalidation instead of deletion.
- Chhikara et al. (Mem0), *Mem0: Building Production-Ready AI Agents with
  Scalable Long-Term Memory*, arXiv:2504.19413 (2025). Borrowed: the update
  phase as a per-claim decision — ADD / MERGE / SUPERSEDE / FLAG / NOOP.

**Trust and provenance (addition 2)**
- Chen et al., *AgentPoison: Red-teaming LLM Agents via Poisoning Memory or
  Knowledge Bases*, NeurIPS 2024, arXiv:2407.12784. Borrowed: the threat
  model — a tiny number of planted records can steer an agent — and hence
  the quarantine and provenance rules.
- Dong et al., *MINJA: Memory Injection Attacks via Querying*, 
  arXiv:2503.03704 (2025). Borrowed: the warning that poison crosses into
  memory through ordinary inputs, which is why external content passes a
  write-gate.
- *A-MemGuard: A Proactive Defense Framework for LLM-Based Agent Memory*,
  arXiv:2510.02373 (2025). Borrowed: validation and consensus checks on
  memory writes, reduced here to human-checkable lint rules.

**Obsidian and search (additions 3–4)**
- Obsidian (Dynalist Inc.) — the Bases, Properties, Templates, and Graph
  features the `obsidian/` pack targets are Obsidian's; the pack's files
  are this kit's own templates and opinions, and Obsidian is not affiliated
  with this kit.
- QMD, by Tobi Lütke — the local Markdown search engine recommended in
  `guides/qmd-search.md`, and also named in Karpathy's original note. The
  guide is this kit's own; QMD itself is its author's project.

**Consolidation and the core tier (addition 5)**
- Lin, Snell, et al. (Letta / UC Berkeley), *Sleep-time Compute: Beyond
  Inference Scaling at Test-time*, arXiv:2504.13171 (2025). Borrowed:
  doing the synthesis work offline, off the latency path, with the
  strongest model — as a scheduled pass, not a feature.
- Park et al. (Stanford / Google), *Generative Agents: Interactive
  Simulacra of Human Agents*, arXiv:2304.03442 (2023). Borrowed: reflection
  that synthesises records into higher-level claims *with the evidence
  pointed to*, and importance-rated retrieval.
- Edge et al. (Microsoft Research), *From Local to Global: A Graph RAG
  Approach to Query-Oriented Summarization* (GraphRAG), arXiv:2404.16130
  (2024). Borrowed: pre-computed cluster summaries, refreshed in the pass,
  as the layer global questions are answered from.
- Packer et al. (UC Berkeley), *MemGPT: Towards LLMs as Operating Systems*,
  arXiv:2310.08560 (2023). Borrowed: the small always-loaded core vs. the
  paged-in store — here, `CORE.md` with a hard size cap.

**Memory kinds and promotion (addition 6)**
- Sumers, Yao, Narasimhan, Griffiths (Princeton), *Cognitive Architectures
  for Language Agents* (CoALA), arXiv:2309.02427 (2023). Borrowed: the
  episodic / semantic / procedural / working distinction, as a second axis
  that complements — and does not replace — this kit's epistemic categories.
- Shinn et al., *Reflexion: Language Agents with Verbal Reinforcement
  Learning*, arXiv:2303.11366 (2023). Borrowed: the post-mortem written as
  an instruction to a future self.
- Zhao et al., *ExpeL: LLM Agents Are Experiential Learners*, AAAI 2024,
  arXiv:2308.10144. Borrowed: extracting the lesson from the *contrast*
  between a failed and a successful attempt.

**Staleness and retention (addition 7)**
- Zhong et al. (Sun Yat-Sen University / HIT / KTH), *MemoryBank: Enhancing
  Large Language Models with Long-Term Memory*, AAAI 2024,
  arXiv:2305.10250. Borrowed: decay as a policy — translated from a formula
  into review dates and a queue, and deliberately *not* applied to
  falsified knowledge.
- Behrouz, Zhong, Mirrokni (Google), *Titans: Learning to Memorize at Test
  Time*, arXiv:2501.00663 (2025). Borrowed: two heuristics only — the
  surprise check at ingest (memorise what violates expectation; a repeat is
  a NOOP) and the retention gate as a framing: a system without a stated
  forgetting policy has still chosen one.

**The self-test (addition 8)**
- Wu et al., *LongMemEval: Benchmarking Chat Assistants on Long-Term
  Interactive Memory*, ICLR 2025, arXiv:2410.10813. Borrowed: the ability
  list — extraction, multi-session reasoning, knowledge updates, temporal
  reasoning, abstention — as question types.
- Maharana et al., *Evaluating Very Long-Term Conversational Memory of
  LLM Agents* (LoCoMo), ACL 2024, arXiv:2402.17753. Borrowed: recall,
  multi-hop, temporal, and adversarial (answer-not-present) question types.
- Hu et al. (HUST), *MemoryAgentBench*, arXiv:2507.05257 (2025). Borrowed:
  conflict resolution as a first-class thing to test.
- None of these benchmarks' data, code, or questions ship in the kit. Only
  the taxonomy of what to test was borrowed; buyers write their own
  questions about their own wiki.

## The v1.2 research additions

Version 1.2 — the currency-and-integrity release — adds six features,
translated the same way as v1.1's: the mechanism as an idea, never text,
code, data, or results.

**Dependency links and the invalidation sweep (addition 1)**
- Chao et al., *STALE: Can LLM Agents Know When Their Memories Are No
  Longer Valid?*, arXiv:2605.06527 (2026). Borrowed: the problem itself —
  implicit conflict and cascading invalidation, where a changed premise
  silently invalidates dependent memories — and the finding that the best
  current system resolves only about half of cases, which is why the kit
  records and queues doubt instead of guessing at resolution.
- Uddin et al., *Memora: From Recall to Forgetting*, arXiv:2604.20006
  (2026). Borrowed: penalising reliance on obsolete memory as a first-class
  failure, translated here into the `needs_review` flag's urgency in the
  queue.

**Consolidation diff discipline (addition 2)**
- Zhang et al., *Useful Memories Become Faulty When Continuously Updated
  by LLMs*, arXiv:2605.12978 (2026). Borrowed: the central warning —
  continuously rewritten textual memory degrades, eventually below the
  no-memory baseline, and the rewrite step is the failure point — hence
  proposals instead of rewrites, and immutable episodic records.
- Lam et al., *SSGM: Governing Evolving Memory in LLM Agents*,
  arXiv:2603.11768 (2026). Borrowed: verify-before-promotion as a gate
  in front of consolidation.
- Kerestecioglu et al., *Human-Inspired Memory Architecture*,
  arXiv:2605.08538 (2026). Borrowed: deduplication, not summarisation, as
  the dominant consolidation mechanism — hence dedup-before-summarise.
- Cui et al., *MemTxn*, arXiv:2607.27834 (2026). Borrowed: every update
  supported by its cited source — hence the evidence field on every
  proposal.

**Write-path security pack (addition 3)**
- Zhang et al., *MemGhost*, arXiv:2607.05189 (2026). Borrowed: the attack
  shape — a single message arranging for the agent to write a payload into
  its own persistent filesystem memory — and its two portable defences:
  announce every memory write in the visible reply, and quarantine
  message-derived content.
- OWASP, *Top 10 for Agentic Applications (2026)*, risk ASI06 (Memory &
  Context Poisoning), genai.owasp.org. Borrowed: the control set the pack
  maps to — scoping, per-entry provenance, quarantine workflows, treating
  external content written to memory as untrusted. The Gemini memory
  incident it cites (Johann Rehberger, February 2025) is the source of the
  trigger-entry quarantine rule.
- Pillar Security, *Rules File Backdoor* (2025). Borrowed: hidden Unicode
  in shared agent rules files as a delivery channel — hence the lint over
  U+200B–200D, U+FEFF, U+202A–202E, and U+E0000–E007F.
- Leong, *Injection-Execution Dissociation*, arXiv:2605.08442 (2026).
  Borrowed: the result that isolating recalled memory from executable
  context is the defence that works — translated here as the
  recall-is-not-authority rule.
- Srivastava & He, *MemoryGraft*, arXiv:2512.16962 (2025). Borrowed:
  imported examples and experiences must never auto-promote to trusted
  memory.
- Mitiga (2026), the poisoned coding-test repository incident. Borrowed:
  the opening-untrusted-projects procedure. The lethal-trifecta framing
  (private data + untrusted content + external communication) is Simon
  Willison's (2025).

**Behavioural self-test v2 (addition 4)**
- Chao et al., *STALE*, arXiv:2605.06527 (2026) — again: its
  premise-resistance probe design (questions that falsely presuppose a
  stale state) is the B1 probe.
- Ma et al., *MEMPROBE*, arXiv:2606.24595 (2026). Borrowed: evaluating
  memory as an auditable artefact — reconstruct the true state from the
  store left behind — which is the B2 state-recovery drill.
- Chen et al., *HaluMem*, arXiv:2511.03506 (2025, revised 2026).
  Borrowed: operation-level scoring — errors are manufactured at
  extraction and update time — which is the B4 write-fidelity sample.
- Wu et al., *LongMemEval-V2*, arXiv:2605.12493 (2026). Borrowed: the
  field's shift from recall questions to trajectory and premise tasks,
  which Part 2 of the self-test follows.

**Deferred-adjudication inbox (addition 5)**
- Mem0 (vendor publication, April 2026). Borrowed: the evidence and the
  pivot — a production memory system publicly abandoned per-claim
  write-time operations for append-only capture with later resolution,
  because write-time adjudication is a real cost centre. Strata keeps the
  adjudication and moves it to the consolidation pass; it does not adopt
  append-only storage as the endpoint.
- *MPBench* (systematic study of memory poisoning), arXiv:2606.04329
  (2026). Borrowed: the safety rider — agents that write memory more
  aggressively are more exploitable — hence the inbox's quarantine by
  construction.

**Rescue & migration kit (addition 6)**
- Letta, *Context Repositories / MemFS* (February 2026),
  letta.com/blog/context-repositories. Borrowed: the initialisation idea —
  fanning out over a user's existing agent history to build the store —
  applied here to the file the buyer already has.
- Anthropic, Claude Code memory documentation (2025–2026). Borrowed: the
  ~200-line guidance for always-loaded instruction files, which is the
  split worksheet's target size for the surviving schema file.

## The v1.3 research additions

Version 1.3 — the compiled-procedures release — adds the skills-format
procedural pack, translated the same way as v1.1's and v1.2's additions:
the mechanism as an idea, never text, code, data, or results. It also
ships two small fill-ins from the same research pass.

**Procedures as skills (the headline)**

- Anthropic, *Agent Skills* and the **Agent Skills open standard**
  (launched October 2025; published as an open standard 18 December
  2025), anthropic.com/news/skills and agentskills.io. Borrowed: the
  format itself — a folder containing `SKILL.md`, YAML frontmatter
  limited to `name` + `description`, the procedure as the Markdown body,
  optional `references/` / `scripts/` / `assets/` — and its mechanism,
  progressive disclosure: name and description always in context, the
  full file loaded when a task matches, bundled files loaded only as
  referenced. The standard is open and vendor-neutral; Strata's skills
  are written to it unchanged, and the kit's contribution is the
  governance around it, not the format.
- Tang et al. (Google), *WikiSkill*, arXiv:2608.27454 (2026). Borrowed:
  the three-layer shape — raw experience → accumulated knowledge →
  executable skills, co-maintained, with the persistent wiki as the
  critical layer — and the finding that skills compiled *from* a
  maintained wiki are the ones that compound. Strata's precedence rule
  (the wiki is the source of truth; a skill is its compiled edge; on
  disagreement the entry wins and the skill is recompiled) is that shape
  stated as a discipline.
- Xia et al., *SkillRL*, arXiv:2602.08234 (2026). Borrowed: the skill
  card's shape — name, principle, when-to-apply — and the practice of
  keeping failed episodes as concise **failure lessons** attached to the
  skill they taught, rather than discarding them.
- Zhang et al., *MemSkill*, arXiv:2602.02474 (2026). Borrowed: the
  direction of travel — memory operations themselves becoming reusable,
  periodically revised skills — which is where Strata's own workflow
  templates point next; v1.3 compiles project procedures, and MemSkill is
  cited as the research marker, not as a shipped feature.
- Zhang et al., *Experience Compression Spectrum*, arXiv:2604.15877
  (2026). Borrowed: the framing that episodic records, procedural skills,
  and declarative rules are one spectrum at different compression
  ratios — the reason a skill's description (its decompression trigger)
  has to be precise, and a lifecycle has to exist for moving knowledge
  along the spectrum in both directions.
- Letta, *Context Repositories / MemFS* (February 2026),
  letta.com/blog/context-repositories — again: its
  frontmatter-description progressive disclosure over a file tree is the
  same routing shape, applied there to memory files generally.

**Authorship & the multi-agent write protocol (fill-in, candidate 8)**

- Letta, *Context Repositories / MemFS* (2026) — again: memory edits on
  per-agent branches/worktrees, merged back — adopted here with the
  kit's own rider that merges happen at a reviewed consolidation point,
  not continuously.
- *Portable Agent Memory*, arXiv:2605.11032 (2026). Borrowed: the
  signed-provenance argument — authorship of a memory write should be
  attestable, which the kit takes as `recorded_by:` on every entry plus
  optional signed commits in shared repos.
- *VMG survey* (storage-time provenance), arXiv:2604.16548 (2026), and
  NIST's agent identity and logging direction (February 2026).
  Borrowed: provenance captured *at write time*, not reconstructed
  later — the reason `recorded_by:` is filled when the entry is filed
  and never edited afterwards.

**OKF alignment note (fill-in, candidate 10)**

- Google, *Open Knowledge Format (OKF) v0.1* (June 2026). Borrowed:
  nothing structural — the note in `guides/okf-alignment.md` is a
  mapping, not an adoption: one concept per Markdown file, `type` as the
  one required frontmatter field, ordinary links as the graph, and the
  reserved names `index.md` / `log.md`, all of which Strata's
  conventions already honour or superset. OKF's details are cited as
  reported in secondary coverage of Google's announcement; the note says
  so in its own text, and exact conformance claims should be re-verified
  against Google's current documentation before being relied on.

## The worked examples

Ledgerline, the invoicing app used in the main worked example, and Pantry,
the meal-planning app in the rescue example, are fictional. Any resemblance
to a real product or company is coincidence. The numbers in their entries are
illustrative, not measurements of a real business. The three skills in
`examples/skills-example/` are compiled from Ledgerline's entries and share
their fictional status.
