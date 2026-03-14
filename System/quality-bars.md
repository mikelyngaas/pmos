# Quality Bars

> **Purpose:** Explicit definition of "ready" for each artifact. The AI uses these in coherence checks and final-review steps; the PM and AI align on what "good enough" means before calling an artifact done.
>
> **Source of truth:** This file is referenced by `System/artifact-hub.md` and by each workflow. Before finalizing any artifact, the AI should verify it meets the relevant bar below.
>
> **When the bar isn't met:** Don't stand pat. List the gaps for the PM (which criteria are missing or weak), then ask: **address them before finalizing, or explicitly accept and proceed?** The PM can override — if they choose to proceed, document their decision (e.g. in the artifact or in the review file) and move on.

---

## Product Brief

A brief is **ready for stakeholders** when:

| # | Criterion | What it means |
|---|-----------|----------------|
| 1 | Problem has cited evidence | Section 1 (Problem) references at least 2 distinct evidence sources from the feature context (e.g. VoC + Sales/Support/Strategic). If the PM proceeded with thin evidence via explicit acknowledgment, that is documented. |
| 2 | Goals have metrics | Section 3 includes at least one goal with a defined metric (and ideally baseline/target). Non-goals are explicitly listed. |
| 3 | Solution direction is scoped | Section 4 states proposed approach, 2–3 key workflows, and what is in/out of scope for V1. Open questions and risks are called out. |
| 4 | Strategic connection is stated | The brief explains how this feature connects to company strategy or quarterly goals (from company context or feature context). |
| 5 | Review feedback addressed or accepted | Key tensions from the persona review have a PM decision (accept, reject, or defer); P0s are either resolved or explicitly accepted as open risk. |

---

## Full PRD

A PRD is **ready for engineering** when:

| # | Criterion | What it means |
|---|-----------|----------------|
| 1 | Problem is evidence-backed | Section 1 synthesizes from feature context with cited evidence; if evidence was thin, the PM's acknowledgment is reflected. |
| 2 | Goals are measurable | Section 3 has a goals table with metric, type, and "How Measured" specified for each goal. Non-goals are explicit. |
| 3 | Requirements are testable | Section 4.3 (Detailed Requirements) has key requirements with clear acceptance criteria (or a clear owner for adding them). Priority (Must have / Should have) is assigned. |
| 4 | Dependencies and risks are captured | Section 4.4 (Dependencies) and 4.6 (Edge Cases & Failure Modes) are filled in where applicable; Assumptions appendix lists material assumptions. |
| 5 | Readiness is addressed | Section 5 covers rollout, positioning/messaging, and enablement at a level appropriate to the feature. Rollback or release strategy is stated where relevant. |
| 6 | Open questions have owners | Every open question has an owner and (if possible) target resolution. Decision Log captures key tradeoffs from persona feedback. |
| 7 | Persona feedback is resolved | P0 feedback from all phases is either addressed in the PRD or explicitly accepted as open risk; Key Tensions have PM decisions recorded. |

---

## Interactive Prototype

A prototype is **ready for stakeholder review** when:

| # | Criterion | What it means |
|---|-----------|----------------|
| 1 | Scope is confirmed | The set of screens/workflows to prototype was agreed with the PM before building. |
| 2 | Key workflows are clickable | The primary user path(s) from the brief or PRD are navigable (screens connect, key CTAs and state changes work). |
| 3 | Faithful to source | The prototype reflects the workflows and scope from the Product Brief or PRD; no major requirements or flows from the source are missing. |
| 4 | Key states are shown | At least default and one other meaningful state (e.g. empty, populated, or error) are represented where the source artifact defines them. |
| 5 | Content is realistic | Placeholder content matches the domain and terminology of the brief/PRD (no generic "Lorem" where the doc specifies a concrete example). |

---

## GTM 1-Pager

A GTM 1-pager is **ready for GTM teams** when:

| # | Criterion | What it means |
|---|-----------|----------------|
| 1 | Source is used | Content is drawn from the Product Brief or PRD; no material claims that contradict the source. |
| 2 | Core sections are complete | "What Is It," "Who Is It For," "Why It Matters," and "How to Sell/Support It" (or equivalent per template) are filled in with concrete, actionable content. |
| 3 | Value prop is one-sentence testable | A sales rep could state the value prop in one sentence from this doc. |
| 4 | Objections / FAQ addressed | Known objections or FAQs from the source or persona review are addressed, or explicitly called out as "TBD before launch." |

---

## External Product Docs

External docs are **ready for Eng/Support review** when:

| # | Criterion | What it means |
|---|-----------|----------------|
| 1 | PRD is the source | Content is grounded in the PRD (and optionally codebase); workflows and requirements are accurately represented. |
| 2 | Audience is clear | The doc states who it's for (e.g. end users, admins) and is written at the right level. |
| 3 | Key workflows are documented | All workflows that the PRD defines as in-scope for users are covered (getting started, main flows, and reference where needed). |
| 4 | Accuracy check | Where implementation exists, terminology and behavior match the product (or discrepancies are flagged for the review team). |
