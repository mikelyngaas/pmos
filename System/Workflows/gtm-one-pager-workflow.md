# GTM 1-Pager Workflow

This document defines the process for creating a GTM 1-Pager — a concise primer that gives sales, CS, and marketing teams everything they need to understand and sell a feature.

## When to Use

- A feature is approaching launch and GTM teams need to be enabled
- Sales needs a quick reference for demos and prospect conversations
- CS needs to understand a feature well enough to support customers on it

## Inputs

The GTM 1-Pager is a **derivative artifact** — it extracts and repackages content from an existing Product Brief or PRD. It requires at least one of:

1. **Product Brief** (`Features/[feature-name]/product-brief.md`) — produces a higher-level 1-pager
2. **Full PRD** (`Features/[feature-name]/prd.md`) — produces a more detailed 1-pager with rollout specifics

Also read:
- **`System/company-context.md`** — for strategic framing and positioning context

If neither a Product Brief nor a PRD exists for this feature, tell the user and offer to create one first.

**Company context check:** At the start of the workflow, read `System/company-context.md`. If it is effectively empty (only placeholders), tell the user: "Company context isn't set; positioning and persona feedback will be generic. Set it up now, or proceed anyway?" Let the user choose before continuing.

## Output

`Features/[feature-name]/gtm-one-pager.md` — using the template at `System/Templates/gtm-one-pager-template.md`.

## How It Works

The GTM 1-Pager is a **single-phase** process. It's lighter than a PRD or Product Brief because it's extracting and reframing existing content, not creating new analysis.

---

## Step 1 — Extract & Draft

Read the source artifact (Product Brief or PRD) and draft the 1-pager by mapping content:

| 1-Pager Section | Source (from Brief) | Source (from PRD) |
|-----------------|--------------------|--------------------|
| What Is It? | Executive Summary | Section 0 (Executive Summary) |
| Who Is It For? | Section 1.1 (Target Users) | Section 1.1 (Target Users) |
| Core Use Cases | Section 4.2 (Key Workflows) | Section 4.2 (Key Workflows) + Section 1.2 (Customer Problems) |
| How It Works | Section 4.2 (Key Workflows) | Section 4.2 + Section 4.3 (Requirements) |
| Key Talking Points | Section 1.4 (Why We Care) + Section 4.1 (Proposed Approach) | Section 1.4 + Section 5.2 (Positioning & Messaging) |
| Competitive Context | Section 2.2 (if exists) | Section 2.2 (Competitive & Market Context) |
| Availability | Next Steps | Section 5.1 (Rollout Plan) + Section 5.4 (Monetization) |

**Tone shift is critical.** The source artifacts are written for product and engineering. The 1-pager is written for customer-facing teams. Translate:
- Technical language → customer value language
- Internal metrics → customer outcomes
- Requirements → use cases and scenarios

Present the draft to the user for review.

## Step 2 — Persona Review

Simulate **GTM Lead** and **Support Lead** reviewing the draft:

**GTM Lead** focuses on:
- Is the value prop crisp and sellable? Would a sales rep know what to say after reading this?
- Are the use cases concrete enough to resonate in a customer conversation?
- Is competitive positioning accurate and useful?
- Is anything missing that a customer-facing team would need?

**Support Lead** focuses on:
- Will CS understand the feature well enough to support it?
- Are there common customer questions this doesn't answer?
- Is the "how it works" section clear enough for someone who hasn't used the feature?

Present feedback from both personas with P0/P1/P2 priority tags.

## Step 3 — Revise & Finalize

Incorporate feedback and finalize. Before calling the 1-pager done, verify it meets the **GTM 1-Pager** quality bar in `System/quality-bars-draft.md`. If it doesn't, list the gaps and ask the PM: address them or explicitly accept and proceed? The PM can override. The 1-pager should be:
- **Skimmable** — a busy sales rep should get the gist in 60 seconds
- **Concrete** — use cases are scenarios, not abstractions
- **Actionable** — talking points are ready to use in a customer conversation

Fill in the Resources section with links to any available related artifacts (PRD, prototype, docs).

---

## Workflow Rules

### Pacing
- This is a fast workflow — typically completable in a single session
- The user can skip the persona review if they're confident in the content

### Tone
- Write for customer-facing humans, not product people
- Avoid jargon, internal metrics, and technical details
- Every sentence should answer "why should a customer care?"
