# PRD Workflow Guide

The AI runs this workflow for you; you answer questions and approve steps. It defines when each persona weighs in and what happens at each step.

## How It Works

The PRD process has **4 phases**. Each phase follows the same rhythm:

1. **Draft** — the user and AI work together to fill in the relevant PRD sections
2. **Review** — the AI simulates the relevant personas, presenting their feedback as a grouped batch
3. **Revise** — the user and AI incorporate feedback and update the draft

The user can skip or abbreviate any phase. The AI should ask before moving between phases.

## Before You Start: Context Loading

### Setting up a new feature

Every new feature gets its own folder under `Features/`. **Never edit the templates directly.** The repeatable process:

1. Name the feature (e.g., `smart-notifications`)
2. Create `Features/[feature-name]/` with fresh copies of the PM POV and feature context templates
3. Fill them in (via conversation or paste)
4. Run the 4-phase workflow
5. Final PRD lands in `Features/[feature-name]/prd.md`

```
Features/
  [feature-name]/
    pm-pov.md                ← copied from System/Templates/pm-pov-template.md
    feature-context.md       ← copied from System/Templates/feature-context-template.md

Features/
  [feature-name]/
    prd.md                   ← final output from prd-template.md
```

### Continuing from a Product Brief

If a Product Brief already exists for this feature (`Features/[feature-name]/product-brief.md`), the PRD workflow can pick up from it:

- **Phase 1 can be abbreviated.** The problem, goals, and high-level solution direction are already aligned. Review for completeness, confirm with the PM, and move to Phase 2.
- The Product Brief's content maps to PRD sections 0–3 + high-level solution. The PRD workflow fills in detailed requirements (section 4), readiness (section 5), and appendices.

### Three input files

At the start of every new PRD, the AI should read three input files:

1. **`System/company-context.md`** (stable) — Product vision, north star metrics, company strategy, and quarterly goals. Grounds every PRD in strategic reality.
2. **PM POV** (`Features/[feature-name]/pm-pov.md`) — The PM's point of view: their read on the problem, hypothesis on the solution, context that won't show up in data, key worries, and conviction level. **This is the primary framing.** The AI should treat the PM's judgment as the starting point, not override it.
3. **Feature context file** (`Features/[feature-name]/feature-context.md`) — Raw evidence: customer quotes, support tickets, sales feedback, competitive intel. This is a messy dump and that's fine.

If the feature folder doesn't exist yet, the AI creates it and copies fresh templates. If any inputs are missing or thin, the AI helps the user fill them in through conversation before proceeding.

**Company context check:** At the start of the workflow, read `System/company-context.md`. If it is effectively empty (only placeholders, no real vision/goals/strategy), tell the user: "Company context isn't set; alignment and persona feedback will be generic. Set it up now, or proceed anyway?" Let the user choose before continuing.

**How the three inputs work together:** The PM POV sets the direction. The feature context provides supporting evidence. The company context ensures strategic alignment. The AI's job is to synthesize all three into polished PRD sections — strengthening the PM's framing with evidence, flagging where evidence contradicts the PM's hypothesis, and connecting it to company strategy.

When the PM's conviction level is high (80–100%), the AI should sharpen and build out the framing. When conviction is low (< 60%), the AI should challenge, pressure-test, and explore alternatives more aggressively. When conviction is moderate (60–79%), lightly sharpen and lightly challenge (e.g. surface 1–2 pressure-test questions); use optional conviction notes in the PM POV to calibrate.

Personas should reference all three inputs when giving feedback (e.g., the CEO/Founder should check strategic alignment against company goals, not in a vacuum).

---

## Phase 1: Problem Framing

**Personas active:** CEO/Founder

**Goal:** Establish a clear, scoped, strategically justified problem and set of goals.

### Step 1.1 — Context Loading

The AI reads all three input files (company context, PM POV, feature context). If any are missing or thin, the AI helps the user fill them in through conversation before proceeding.

If the PM POV or feature context aren't written yet, the AI can help bootstrap them by asking the PM the key questions from each template conversationally, then writing the files.

### Step 1.2 — Synthesis Check

Before drafting anything, the AI presents a short synthesis back to the PM. This is a "here's what I took away from your inputs — did I get it right?" checkpoint. The synthesis should cover:

- **Problem as understood** — the AI's read on the core problem, in 2-3 sentences, grounded in the PM's framing
- **Strongest supporting evidence** — the most compelling signals from the feature context that back up the PM's hypothesis
- **Tensions or contradictions** — anywhere the evidence complicates or contradicts the PM's framing (e.g., "you believe X, but support tickets suggest Y")
- **Gaps** — things the AI would need to make the PRD stronger but doesn't have yet (e.g., "no data on current workaround usage" or "no competitive context provided")
- **Strategic connection** — how this maps to company goals and north star from the company context

The PM reviews the synthesis and confirms, corrects, or adds context. This is a conversation — the AI should ask follow-up questions if things are unclear. The goal is alignment before any drafting begins.

### Step 1.2b — Evidence Sufficiency Check

Before drafting the Problem section, check the feature context against the evidence bar:

- **Bar:** At least **2 distinct evidence sources** (e.g. Voice of Customer + one of Voice of Sales / Voice of Support / Strategic Connection), each with substantive content (not just "TBD" or a single vague line).
- If the bar is **not met:** Flag it as **P0** to the user: "Evidence is thin for an evidence-backed problem statement. You have [list what's present]. Consider adding [what's missing], or explicitly acknowledge that you're proceeding with limited evidence." **Do not draft Section 1 (Problem)** until the PM either adds evidence or explicitly acknowledges the gap and chooses to proceed.
- If the bar **is met** (or PM has acknowledged): Proceed to Step 1.3.

### Step 1.3 — Draft Core Sections

Once the PM confirms the synthesis and evidence is sufficient (or acknowledged), the AI drafts initial versions of:
- **Section 0** — Executive Summary (brief, will be refined at the end)
- **Section 1** — Problem (synthesized from all three inputs — target users, customer problems, why current solutions fall short, why we care)
- **Section 2** — Historical Context (if applicable — the AI should ask whether this section is needed)
- **Section 3** — Goals & Success Metrics (goal-metric mapping, non-goals)

The AI should present the draft and invite the PM to react, edit, and fill gaps. The draft should clearly reflect the PM's framing from the brief, strengthened with evidence from the feature context.

### Step 1.4 — Review

Before presenting persona feedback, the AI does its own coherence check on the draft:
- Is the problem specific and evidence-backed?
- Are goals measurable? Does each goal have a clear metric?
- Is scope controlled — are non-goals defined?
- Does the draft faithfully reflect the PM's intent from the brief?

Surface any issues directly — this is the AI's job, not a persona's.

Then simulate the **CEO/Founder** reviewing the draft:

**CEO/Founder** focuses on:
- Why this, why now? Is the strategic case compelling?
- Is the investment justified relative to the expected impact?
- What's the smallest version that validates the bet?
- Does this align with current company priorities?

Each piece of feedback should be actionable — not just "this could be better" but "here's what's missing or unclear."

### Step 1.5 — Revise

The user and AI revise sections 0–3 based on persona feedback. The AI updates the draft and confirms the user is satisfied before moving on.

**Exit criteria:** The user confirms the problem, goals, and strategic justification are solid.

---

## Phase 2: Deep Dive

**Personas active:** Tech Lead, Design Lead, Legal Lead, Data Science Lead

**Goal:** Flesh out the solution with technical feasibility, user experience, compliance, and measurement in mind.

### Step 2.1 — Draft Solution Sections

The AI works with the user to draft:
- **Section 4.1** — Approaches Considered (if relevant — the AI should ask whether the scope warrants evaluating multiple approaches)
- **Section 4.2** — Key Workflows & Journeys
- **Section 4.3** — Detailed Requirements (organized by customer journey)
- **Section 4.4** — Dependencies
- **Section 4.5** — Instrumentation (optional — key events for measuring Section 3 goals)
- **Section 4.6** — Edge Cases & Failure Modes

The AI should help the user think through requirements by asking about the customer journey: *What's the first thing a user does? Then what? What happens when they're done?*

### Step 2.2 — Persona Review

The AI simulates the **Tech Lead**, **Design Lead**, **Legal Lead**, and **Data Science Lead** reviewing the draft as a batch:

**Tech Lead** focuses on:
- Is this feasible with our current stack? What's the complexity?
- What are the dependencies and sequencing risks?
- Are there technical assumptions that need validation?

**Design Lead** focuses on:
- Are user flows intuitive? Can we simplify?
- What edge states are unaccounted for (empty, error, loading)?
- Are we adding complexity without proportional user value?

**Legal Lead** focuses on:
- Are there data privacy or compliance implications?
- Do we need new consent flows or disclosures?
- Are there regulatory or contractual risks to flag?

**Data Science Lead** focuses on:
- Can we compute every metric in Section 3 from the instrumentation we're defining?
- Is the metrics→events mapping complete? Any guardrails or data-quality risks missing?
- Are event design and attribution sufficient to interpret results post-launch?

The AI presents all four perspectives in a single response, clearly labeled. If personas conflict (e.g., Tech wants to defer something Design considers essential), the AI should highlight the tension and ask the user to decide.

### Step 2.3 — Revise

The user and AI revise section 4 based on persona feedback. Tradeoffs, decisions, and unresolved questions all go into the **Decision Log**.

**Exit criteria:** The user confirms the solution, requirements, and scope are solid.

---

## Phase 3: Risk & Readiness

**Personas active:** QA Lead, Support Lead, GTM Lead

**Goal:** Stress-test the plan for edge cases, customer impact, go-to-market readiness, and monetization.

### Step 3.1 — Draft Readiness Sections

The AI works with the user to draft:
- **Section 5.1** — Rollout Plan
- **Section 5.2** — Positioning & Messaging
- **Section 5.3** — Sales & Customer Enablement
- **Section 5.4** — Monetization & Packaging (if applicable — the AI should ask)

### Step 3.2 — Persona Review

The AI simulates the **QA Lead**, **Support Lead**, and **GTM Lead** reviewing the full draft as a batch:

**QA Lead** focuses on:
- Are acceptance criteria defined for key requirements?
- What edge cases and failure modes are missing?
- Is the rollback plan clear?

**Support Lead** focuses on:
- Where will customers get confused or stuck?
- Is documentation and error messaging planned?
- Is the support team prepared for launch volume?

**GTM Lead** focuses on:
- Is the ICP clear and the value prop crisp?
- Are internal teams enabled — Sales, CS, Support?
- Are monetization and packaging decisions addressed?

The AI presents all three perspectives in a single response, clearly labeled.

### Step 3.3 — Revise

The user and AI revise sections 4 and 5 based on persona feedback. The AI should help add acceptance criteria to key requirements in the requirements table if the QA Lead flagged gaps.

**Exit criteria:** The user confirms readiness across quality, support, and go-to-market.

---

## Phase 4: Synthesis & Sign-off

**Goal:** Produce the final, coherent PRD.

### Step 4.1 — Final Synthesis

The AI does a final pass across the entire PRD:
- Ensures all sections connect logically
- Resolves any remaining conflicts between persona feedback
- Finalizes the Executive Summary (Section 0) now that the full picture is clear
- Populates the Decision Log with key tradeoffs from all phases
- Confirms all Open Questions have owners and status
- Verifies the Assumptions appendix is complete

### Step 4.2 — Final Review

Before presenting, verify the PRD meets the **Full PRD** quality bar in `System/quality-bars-draft.md`. If it doesn't, list the gaps and ask the PM: address them or explicitly accept and proceed? The PM can override. Then present the complete PRD to the user for a final read-through, calling out:
- Any sections that are thin or incomplete
- Open questions that still need resolution
- Assumptions that carry high risk if wrong
- Any quality-bar criteria that are not yet met

### Step 4.3 — Done

The user confirms the PRD is ready for stakeholder review. The AI saves the final version.

---

## Workflow Rules

### Pacing
- Always ask before moving to the next phase
- The user can say "skip" to bypass any phase or persona
- The user can say "go deeper" to get more detailed feedback from a specific persona

### Persona Feedback Format
- Each persona's feedback is presented under a clear heading (e.g., "**Tech Lead Review**")
- Feedback should be specific and actionable — not vague praise or generic concerns
- Every piece of feedback must include a priority tag:
  - **P0** — Very strong suggestion. Should be addressed before moving forward.
  - **P1** — Consider. Worth discussing; the PM should make a deliberate call.
  - **P2** — Take it or leave it. Low-stakes observation.
- When personas conflict, highlight the tension explicitly and ask the user to decide

### Review File Output
- After each persona review, the AI writes the full review to `Features/[feature-name]/phase-N-review.md`
- **Key Tensions to Resolve table goes at the top of the file.** This is the most actionable section — it represents what the PM needs to resolve. Each row should have a rich description of the tension (not just a label), the priority level, the source persona, and a blank "PM Decision" column.
- Full persona feedback (with priority tags) follows below the tensions table for context and rationale.
- The PM addresses feedback in the review file, then the AI incorporates decisions into the PRD and Decision Log

### Updating Inputs When Discovery Surfaces
- If during synthesis or any persona review the AI surfaces a new assumption, risk, or missing evidence that affects the problem framing or evidence base, suggest updating the PM POV or feature context and record the item in the Decision Log or Open Questions so it isn't lost.

### Draft Management
- After each revision, the AI should update the PRD file directly
- The AI should confirm changes with the user before overwriting

### Flexibility
- Not every PRD needs every section. The AI should use judgment and ask the user:
  - "Does this feature have historical context worth including?" (Section 2)
  - "Is the scope large enough to warrant evaluating multiple approaches?" (Section 4.1)
  - "Are there monetization or packaging implications?" (Section 5.4)
- Smaller features may move through phases faster; the AI should match the depth to the complexity
