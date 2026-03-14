# Artifact Hub

Central registry: route artifact intent to the right workflow and template.

---

## Available Artifacts

| Artifact | When to Use | Inputs | Output Location | Workflow | Template |
|----------|-------------|--------|-----------------|----------|----------|
| Product Brief | Early alignment on problem, goals, and high-level solution direction — before detailed requirements | PM POV + Feature Context + Company Context | `Features/[feature]/product-brief.md` | `Workflows/product-brief-workflow.md` | `Templates/product-brief-template.md` |
| Full PRD | Detailed requirements for features going to engineering | PM POV + Feature Context + Company Context (or continues from Product Brief) | `Features/[feature]/prd.md` | `Workflows/prd-workflow.md` | `Templates/prd-template.md` |
| Interactive Prototype | Clickable, mid-fidelity visualization of key workflows | Product Brief or PRD | `Features/[feature]/prototype.html` | `Workflows/prototype-workflow.md` | N/A (output is HTML) |
| GTM 1-Pager | Quick primer for sales, CS, and marketing teams | Product Brief or PRD | `Features/[feature]/gtm-one-pager.md` | `Workflows/gtm-one-pager-workflow.md` | `Templates/gtm-one-pager-template.md` |
| External Product Docs | User-facing documentation draft for Eng and Support review | PRD (+ optionally the codebase) | `Features/[feature]/external-docs.md` | `Workflows/external-docs-workflow.md` | `Templates/external-docs-template.md` |

All file paths in the table above are relative to `System/` (for workflows and templates) or the workspace root (for outputs).

---

## Dependency Graph

```
PM POV + Feature Context + Company Context
    ├── Product Brief (sections 1-3 + high-level solution)
    │     ├── Interactive Prototype (high-level)
    │     └── GTM 1-Pager (from brief)
    ├── Full PRD (4-phase workflow, continues from Product Brief)
    │     ├── Interactive Prototype (detailed)
    │     ├── GTM 1-Pager (from PRD)
    │     └── External Docs (PRD + codebase)
```

The common path: **Product Brief → iterate → Full PRD → derivative artifacts as needed.** Prototype and GTM 1-pager can be created from the brief as soon as it's ready — you don't need to complete the PRD first.

Not every feature needs every artifact. The system is modular — produce what the feature and its stage require.

---

## Routing Logic

Use intent to determine which artifact to produce:

| User says... | Route to |
|-------------|----------|
| "product brief," "brief," "align the team," "early alignment" | Product Brief |
| "PRD," "requirements," "detailed specs," "send to engineering" | Full PRD |
| "prototype," "mockup," "wireframe," "show me what it looks like" | Interactive Prototype |
| "GTM," "one-pager," "sales enablement," "how do we sell this" | GTM 1-Pager |
| "docs," "documentation," "help article," "user guide" | External Product Docs |

**Prerequisite checks:**
- **Prototype, GTM 1-Pager:** Require a Product Brief or PRD to exist for the feature. If neither exists, tell the user and offer to create a Product Brief first.
- **External Docs:** Require a PRD. If one doesn't exist, tell the user.
- **PRD from Product Brief:** If a Product Brief already exists, the PRD workflow picks up from it — Phase 1 can be abbreviated since problem framing and goals are already aligned.

---

## Persona Assignments

| Artifact | Review Personas |
|----------|----------------|
| Product Brief | CEO/Founder, Design Lead, Tech Lead |
| Full PRD | All personas (see PRD workflow for phase assignments) |
| Interactive Prototype | Design Lead |
| GTM 1-Pager | GTM Lead, Support Lead |
| External Product Docs | Support Lead, Tech Lead |

Persona files live in `Personas/`. Read the relevant personas before running a review.

---

## Quality Bars

Before finalizing any artifact, the AI should verify it meets the **quality bar** for that artifact type. The full definitions live in **`System/quality-bars.md`** (Product Brief, Full PRD, Interactive Prototype, GTM 1-Pager, External Docs). Use them in coherence checks and final-review steps so the PM and AI align on "ready." If the bar isn't met, list the gaps and ask the PM: address before finalizing, or explicitly accept and proceed? The PM can override and move forward.

---

## Shared Inputs

- **`company-context.md`** — Strategic context; read at start of each artifact.
- **`Templates/pm-pov-template.md`** → copy to `Features/[feature]/pm-pov.md` (do not edit template).
- **`Templates/feature-context-template.md`** → copy to `Features/[feature]/feature-context.md` (do not edit template).

## Per-Feature Setup

1. Create `Features/[feature-name]/`; copy PM POV and feature-context templates into it; fill the copies.
2. Choose artifact; follow its workflow. If the feature folder already exists (e.g. brief done, now PRD), skip step 1 and reuse inputs.
