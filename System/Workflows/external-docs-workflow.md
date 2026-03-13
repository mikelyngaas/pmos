# External Product Documentation Workflow

This document defines the process for generating user-facing product documentation from a PRD. The output is a draft that can be reviewed with Engineering and Support before publishing to the help center or knowledge base.

## When to Use

- A feature is nearing launch or has shipped and needs customer-facing documentation
- Support needs documentation to reference when handling customer questions
- You want to draft docs early (from the PRD) and refine them as the feature is built

## Inputs

**Required:**
1. **Full PRD** (`Features/[feature-name]/prd.md`) — the primary source for feature behavior, workflows, and requirements

**Optional but valuable:**
2. **Codebase** — if the feature is built or partially built, reference the actual implementation for accuracy (API endpoints, configuration options, UI labels, error messages). Point the AI at relevant code files or directories.
3. **Product Brief** (`Features/[feature-name]/product-brief.md`) — useful for the Overview and Key Concepts sections
4. **Prototype** (`Features/[feature-name]/prototype.html`) — useful for describing the UI and creating screenshots or step descriptions

If a PRD doesn't exist for this feature, tell the user and offer to create one first. External docs without a PRD are possible but will be thin.

**Company context check:** At the start of the workflow, read `System/company-context.md`. If it is effectively empty (only placeholders), tell the user: "Company context isn't set; tone and framing may be generic. Set it up now, or proceed anyway?" Let the user choose before continuing.

## Output

`Features/[feature-name]/external-docs.md` — using the template at `System/Templates/external-docs-template.md`.

---

## How It Works

### Step 1 — Scope the Documentation

Read the PRD and identify what needs to be documented. Ask the user:

- "Is this for the full feature or a specific part of it?"
- "Who's the primary reader — end users, admins, or both?"
- "Is there existing documentation I should match in tone and structure?"
- "Are there code files I should reference for accuracy?" (settings, API routes, config options, error messages)

**Default scope:** Document all key workflows from Section 4.2 of the PRD, plus getting started and reference sections.

### Step 2 — Draft the Documentation

Map PRD content to documentation sections:

| Doc Section | PRD Source | Codebase Source (if available) |
|-------------|-----------|-------------------------------|
| Overview | Section 0 (Executive Summary) + Section 1 (Problem) | — |
| Key Concepts | Section 4.2 (Workflows) + domain terms from throughout | Model/entity names, UI labels |
| Getting Started | Section 4.3 (Requirements, first-use journey) | Setup flows, onboarding code |
| How-To Guides | Section 4.2 (Key Workflows) + Section 4.3 (Requirements) | UI flows, API endpoints |
| Reference | Section 4.3 (Requirements) + Section 4.4 (Dependencies) | Config options, permissions, limits |
| FAQ & Troubleshooting | Edge states from Section 4.3 + Phase 3 review feedback | Error messages, known issues |

**Critical tone shift:** The PRD is written for the product team. Documentation is written for the customer. Translate:
- Internal feature names → customer-facing names
- Requirements → step-by-step instructions
- Edge states → troubleshooting guidance
- Technical details → plain language

**Use the product's actual language.** If the codebase is available, pull exact UI labels, button text, menu names, and error messages. Don't guess at what the UI says.

Present the draft to the user for review.

### Step 3 — Persona Review

Simulate **Support Lead** and **Tech Lead** reviewing the draft:

**Support Lead** focuses on:
- Would a customer be able to follow these instructions without contacting support?
- Are there common confusion points or questions this doesn't address?
- Is the FAQ section covering the gotchas that will generate tickets?
- Is the tone appropriate for our customer base?

**Tech Lead** focuses on:
- Is the documented behavior technically accurate?
- Are there configuration options, limits, or permissions that are missing or wrong?
- Are the prerequisites correct and complete?
- Does anything described here not match how the feature actually works?

Present feedback with P0/P1/P2 priority tags.

### Step 4 — Revise & Finalize

Incorporate feedback. Before marking the doc ready, verify it meets the **External Product Docs** quality bar in `System/quality-bars-draft.md`. If it doesn't, list the gaps and ask the PM: address them or explicitly accept and proceed? The PM can override. The final documentation should be:
- **Accurate** — matches the actual product behavior
- **Complete** — covers getting started, key workflows, and reference
- **Scannable** — users should find what they need quickly (headers, numbered steps, tables)
- **Self-sufficient** — a user shouldn't need to contact support to accomplish the core tasks

Mark the document as ready for review with the broader Eng and Support teams.

---

## Workflow Rules

### Pacing
- This is typically a single-session workflow, but may require a follow-up if codebase review reveals discrepancies
- The user can skip the persona review if they're iterating quickly

### When Codebase Is Available
- Prioritize codebase over PRD when they conflict — the code is the source of truth for shipped behavior
- Pull exact UI strings, error messages, and configuration names from the code
- Note any PRD-to-implementation discrepancies for the PM to review

### When Codebase Is Not Available
- Draft from the PRD only — clearly mark sections that need verification against the built product
- Add a note at the top: "This documentation was drafted from the PRD. Verify against the shipped feature before publishing."

### Living Document
- External docs should be updated when the feature changes
- If the PRD is updated post-launch, the AI should flag sections of the docs that may need corresponding updates
