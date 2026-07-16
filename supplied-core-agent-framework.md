# The Supplied-Core Agent
## Self-learning, self-evolving, acting — without changing model weights

*v2 — simplified*

---

## Thesis

Base models keep getting stronger. Don't compete with that — depend on it. The LLM is a **supplied core**: a rented, swappable reasoning engine. All learning lives in the system around it. The model is a supplier; the system is the asset.

## Seven layers

**1. Supplied core.** Any capable LLM via API. Interchangeable by design — a stronger model must make every other layer *more* valuable, never obsolete.

**2. Indexed knowledge.** The domain corpus — documents, data, precedents, policies — always paired with its index. Knowledge without retrieval is dead weight: the index (embeddings, metadata, freshness dates, provenance) decides what actually reaches the core's context, so corpus and index are curated as one unit. Grows two ways: humans ingest the world; the agent adds verified facts discovered in operation, each tagged with its origin episode.

**3. Skills.** Plain-language procedure files — the system's "weights." Versioned like code, loaded per task, and the primary surface the agent is allowed to propose edits to. Fully readable: you can open the file and see what the system has learned.

**4. Memory.** Episode logs (everything, with outcomes) and a case library (the best solved examples, promoted only after verified success).

**5. Actions.** Tools, tiered by reversibility: read → freely; reversible write → freely, logged; irreversible (send, transact, delete) → verification or human confirmation, with budget limits. Tiers are set by humans, never by the agent.

**6. Verification.** Every episode ends with a verdict. Prefer deterministic checks (tests pass, numbers reconcile — unhackable), then model judges (spot-audited), then humans (spent sparingly).

**7. Reflection + gate.** After each episode, a reflector asks: *what did this teach, and where does it belong?* Procedural → skills. Factual → indexed knowledge. Exemplary → case library. Output is a proposed diff, never a direct write. The **gate** runs the held-out eval suite: score holds → commit; regresses → discard.

## The loop

Perceive → plan → act → **verify** → reflect (route the learning) → **gate** → commit or discard → next episode runs smarter. One episode, one verdict, at most one accepted edit — every unit of learning a readable, timestamped diff.

## Two laws

**The agent edits its skills and knowledge, never its judges.** Verifiers, eval sets, tool tiers, and these laws are human-only territory. A system that can weaken its own grader produces worthless scores.

**No mutation without evaluation.** Every proposed edit passes the frozen eval set before committing. Facts need a higher bar than procedures — deterministic or human verification, because a false fact masquerades as ground truth in every future retrieval.

## Failure modes → controls

Skill bloat → size budgets, periodic gated consolidation. Memory pollution → promote only verified wins. Knowledge contamination → stronger verification for facts, provenance + expiry, auto-quarantine on traced failures. Verifier gaming → adversarial review, sampled human audits. Compounding action errors → verify at checkpoints, irreversible actions last. Model-swap drift → full eval run on every core change.

## Maturity ladder

L1 static agent → L2 adds memory → L3 gated self-editing (human approves each diff — live here a long time) → L4 eval-gated autonomy (humans own the eval set, audit samples). Earn each level only when the one below is boring.

## Build vs. skip

**Compounds:** indexed knowledge, skill files, case library, verifiers, eval sets, episode logs — all worth more when the supplier improves.
**Depreciates:** anything patching a current model's weakness — the next release deletes it for free.

---

*You are not training a model. You are running an institution that rents its brain, writes down everything it learns, refuses to grade its own homework — and gets a free intelligence upgrade every time its supplier ships.*
