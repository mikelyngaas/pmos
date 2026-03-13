# Product Brief Workflow

The AI runs this workflow for you; you answer questions and approve steps. Output: `Features/[feature-name]/product-brief.md` from `System/Templates/product-brief-template.md`.

**Inputs:** Company context, PM POV (`Features/[feature-name]/pm-pov.md`), feature context (`Features/[feature-name]/feature-context.md`). If any are missing or thin, fill them in with the user first.

**When to use:** Early alignment before detailed requirements; common path is brief → feedback → iterate → PRD.

**2 phases.** Each: Draft → Review (persona feedback, P0/P1/P2) → Revise. Ask before moving between phases.

**Company context check:** At the start of the workflow, read `System/company-context.md`. If it is effectively empty (only placeholders, no real vision/goals/strategy), tell the user: "Company context isn't set; alignment and persona feedback will be generic. Set it up now, or proceed anyway?" Let the user choose before continuing.

---

## Phase 1: Problem Framing

**Persona:** CEO/Founder. **Goal:** Clear, scoped problem and goals, strategically justified.

1. **Context** — Read all three inputs; fill gaps with the user if needed.
2. **Evidence sufficiency check** — Before drafting the Problem section, check the feature context against the evidence bar:
   - **Bar:** At least **2 distinct evidence sources** (e.g. Voice of Customer + one of Voice of Sales / Voice of Support / Strategic Connection), each with substantive content (not just "TBD" or a single vague line).
   - If the bar is **not met:** Flag it as **P0** to the user: "Evidence is thin for an evidence-backed problem statement. You have [list what's present]. Consider adding [what's missing], or explicitly acknowledge that you're proceeding with limited evidence." **Do not draft Section 1 (Problem)** until the PM either adds evidence or explicitly acknowledges the gap and chooses to proceed.
   - If the bar **is met** (or PM has acknowledged): Proceed.
3. **Synthesis** — Present back: problem as understood, strongest evidence, tensions/gaps, strategic connection. PM confirms or corrects.
4. **Draft** — Executive summary (refine later), Section 1 (Problem), optional Section 2 (Historical Context — ask first), Section 3 (Goals & Success Metrics, non-goals). Invite PM to react.
5. **Coherence check** — AI flags if problem isn’t evidence-backed, goals aren’t measurable, scope isn’t controlled, or draft drifts from PM intent.
6. **CEO/Founder review** — Why this/why now, investment justified, smallest validating version, alignment with priorities. Feedback with P0/P1/P2.
7. **Revise** — Update sections 1–3 from feedback. **Exit:** Problem, goals, and strategic justification solid.

---

## Phase 2: Solution Direction

**Personas:** Design Lead, Tech Lead. **Goal:** High-level solution direction — enough to decide to proceed, not to hand to engineering.

1. **Draft** — Section 4.1 (Proposed Approach), 4.2 (Key Workflows), 4.3 (High-Level Scope in/out), 4.4 (Open Questions & Risks). Ask: simplest version, 2–3 user workflows, what’s deliberately out of V1.
2. **Design Lead + Tech Lead review** — Design: workflows make sense, UX/scope risks. Tech: feasibility, architecture/dependencies, need for spikes. Present feedback labeled, P0/P1/P2. Write review to `Features/[feature-name]/brief-review.md`. **At the top**, include a **Key Tensions to Resolve** table with columns: **Tension** (rich description), **Priority** (P0/P1/P2), **Source** (persona name), **PM Decision** (blank for PM to fill). Full persona feedback with P0/P1/P2 tags follows below.
3. **Revise & finalize** — Update section 4; finalize Executive Summary, open-question owners, Next Steps. Before calling the brief done, verify it meets the **Product Brief** quality bar in `System/quality-bars-draft.md`. If it doesn't, list the gaps and ask the PM: address them or explicitly accept and proceed? The PM can override. **Exit:** PM confirms brief ready for stakeholders.

---

## After the Brief

For a full PRD on the same feature: reuse PM POV and feature context; abbreviate PRD Phase 1; use the brief’s solution direction as the start for detailed requirements.

**Rules:** Ask before moving phases; user can skip or abbreviate. Persona feedback: clear heading, specific, P0/P1/P2; surface tensions for user to decide. Historical Context (Section 2) optional. Match depth to feature complexity.

**Updating inputs when discovery surfaces:** If during synthesis or any persona review the AI surfaces a new assumption, risk, or missing evidence that affects problem framing or the evidence base, suggest updating the PM POV or feature context and record the item in Section 4.4 (Open Questions & Risks) or in the brief so it isn't lost.
