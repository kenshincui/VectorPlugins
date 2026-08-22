---
name: doc-coauthoring
description: Collaboratively draft and revise structured documents such as PRDs, RFCs, technical designs, proposals, decision records, strategy documents, and project plans. Use when the user needs to turn incomplete context into a document that is clear to reviewers, technically coherent, decision-oriented, and ready for circulation.
---

# Document Co-authoring

Work as an active co-author. Preserve the user's facts and intent, expose missing decisions, and produce a document that works for a reader who was not present in the conversation.

## 1. Establish the contract

Infer what is safe to infer, then ask only questions that materially change the document. Establish the document type, readers, desired decision, status, required template, deadline, destination, source material, and claims requiring verification.

When the user supplies a template, keep its required headings and semantics. When no template exists, choose a structure appropriate to the document type.

## 2. Build a context ledger

Collect unstructured notes without forcing the user to organize them. Separate the material into:

- confirmed facts and constraints;
- goals and non-goals;
- stakeholder needs;
- options considered and rejected;
- dependencies, risks, open questions, and assumptions;
- measurable acceptance criteria;
- evidence and source links.

Never promote an assumption to a fact. Mark unresolved items explicitly and avoid inventing business metrics, dates, owners, or technical behavior.

## 3. Design the document before drafting

Propose a compact outline and explain the decision flow in one sentence. Typical structures:

- PRD: context, problem, users, goals, non-goals, experience, requirements, metrics, rollout, risks, open questions.
- RFC or technical design: context, requirements, current state, proposed design, interfaces and state, alternatives, security, failure handling, migration, observability, testing, rollout.
- Decision record: decision, status, context, options, tradeoffs, consequences, follow-ups.
- Proposal: executive summary, opportunity, evidence, recommendation, plan, investment, risks, decision requested.

Use tables only for exact comparisons, mappings, ownership, or acceptance criteria. Prefer prose for reasoning.

## 4. Draft in reviewable increments

Draft the highest-leverage section first, usually the executive summary, problem statement, or proposed design. For each section:

1. State the conclusion or decision first.
2. Support it with relevant evidence and constraints.
3. Make tradeoffs and exclusions explicit.
4. End with implications, owners, or decisions when useful.

Keep terminology stable. Define ambiguous terms once. Distinguish requirements from implementation suggestions and current behavior from proposed behavior.

## 5. Run a reader test

Review the draft as a fresh reader with no conversation context. Check whether that reader can answer:

- What problem is being solved, for whom, and why now?
- What exactly is proposed or requested?
- What is deliberately out of scope?
- What alternatives were considered and why were they rejected?
- What could fail, and how will failure be detected or recovered?
- Who owns the next action, and what constitutes acceptance?

Repair gaps directly when evidence exists. Otherwise surface a short list of blocking questions or clearly labeled assumptions.

## 6. Final quality gate

Check that the opening summary matches the proposal, every section advances the decision, requirements are testable, diagrams and tables agree with prose, evidence is traceable, risks have mitigations or explicit acceptance, and the document ends with decisions and next steps.

If editing a real file or shared document, preserve formatting and unrelated content, then read back the changed sections before reporting completion.
