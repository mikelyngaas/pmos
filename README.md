# Product Dev OS

**A modular artifact-building system that turns AI coding assistants into product development partners.**

This is for **building features on existing products** — problem framing, alignment, and specs that plug into your current strategy and users. It is not for vibe coding 0-to-1 or greenfield ideas; most AI coding setups already excel there. Product Dev OS is for the other 90%: shipping the next feature on something that already exists.

Five structured workflows for creating product artifacts — briefs, PRDs, prototypes, GTM 1-pagers, and external docs — with AI-simulated stakeholder reviews built in.

Works with [Cursor](https://cursor.com/) and [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

By [Mike Lyngaas](https://mikelyngaas.github.io/index.html)

---

## Start here (for PMs)

You don't need to read the artifact hub or workflows — the AI uses those to route and run. You do this:

1. **First time:** Fill in `System/company-context.md` with your vision, goals, and principles (once; reuse for every feature).
2. **Start a feature:** In Cursor, type **`@new-feature`** in chat (or say "I want to start a new feature"). Give a short name when asked (e.g. `smart-notifications`). The AI creates `Features/[name]/`, copies the PM POV and feature-context templates there, and walks you through filling them in.
3. **Answer the PM POV and feature-context questions** (one at a time; your conviction level calibrates whether the AI sharpens or challenges your framing).
4. **Pick an artifact** (Product Brief is the default). The AI runs the workflow: draft → persona review (P0/P1/P2) → revise. You react and decide when to move on.
5. **Iterate.** From the brief you can go to a PRD, or spin off a prototype or GTM 1-pager right away — no need to finish the PRD first.

**Cursor:** Clone the repo, open the folder in Cursor, then do the steps above. **Claude Code:** Same steps; Claude Code reads `CLAUDE.md` automatically.

For more context — how it works, demo, project structure — read on below.

---

### Without Product Dev OS

- You ask the AI to write a PRD and get a generic template filled with vague language — the AI effectively does the product thinking for you
- No structured review — the AI agrees with everything you wrote
- Each artifact starts from scratch with no shared context
- You spend more time wrestling the output into shape than thinking about the product
- The AI doesn't know your company strategy, your conviction level, or what you're worried about

### With Product Dev OS

- Core product thinking stays with you: you fill in the PM POV (your point of view, in your words — no shortcuts) and raw evidence; the AI synthesizes and drafts from that, it doesn't replace your judgment
- The AI synthesizes your inputs against company strategy before writing anything
- Structured, phased workflows with AI-simulated stakeholder reviews (CEO/Founder, Tech Lead, Design Lead, QA, GTM, and more)
- Every piece of feedback is tagged P0/P1/P2 so you know what to address
- When your conviction is low, the AI challenges your framing. When it's high, the AI sharpens it.
- Artifacts build on each other — a brief flows into a PRD; you can spin off a prototype or GTM 1-pager from the brief as soon as it's ready (no need to finish the PRD first)

---

## Artifacts

| Artifact | What it does | When to use it |
|----------|-------------|----------------|
| **Product Brief** | Aligns the team on problem, goals, and solution direction | Early stage — before detailed requirements |
| **Full PRD** | Detailed requirements and edge cases ready for engineering | Pre-build — after alignment |
| **Interactive Prototype** | Clickable, self-contained HTML visualization of key workflows | From a brief (concept-level) or PRD (detailed) — when stakeholders need to *see* it |
| **GTM 1-Pager** | Sales/CS/marketing primer for a feature | Pre-launch — when GTM teams need enablement |
| **External Docs** | Customer-facing documentation draft | Near or post-launch |

Artifacts are modular. You can create a prototype as soon as the brief is done; you don't need to finish the PRD first. Not every feature needs every artifact. Produce what the feature and its stage require.

---

## Demo: one feature, brief to PRD

```
You:   I want to start a new feature. (or @new-feature)
Product Dev OS:  What should we call it? Short name, e.g. smart-notifications or sequence-templates.
You:   template-gallery
Product Dev OS:  Set up Features/template-gallery/. Let's fill in the PM POV. What's the problem in your own words?
You:   Users build outbound sequences from scratch every time — 30+ min, same patterns. New reps don't know what a good sequence looks like.
Product Dev OS:  What's your hypothesis on the right solution direction?
You:   Curated templates: gallery of proven sequences they can browse, preview, deploy. V1 read-only; V2 adds AI customization.
...
You:   Conviction around 80-85%.
Product Dev OS:  High conviction — I'll sharpen. [Synthesis:] Problem = slow, inconsistent quality. Signal = top accounts asked. Tension = V1 read-only vs support tickets wanting customization. Strategic fit = Q1 "Make Unify Self-Serve." Match?
You:   Yes. Staying firm on read-only for V1.
Product Dev OS:  Noted. [Drafts sections 1-3.] Ready for CEO/Founder review?
You:   Go.
Product Dev OS:  **CEO/Founder:** P0 — "Why now" is weak; quantify churn/onboarding cost. P1 — Size the investment (2 weeks vs quarter?). P2 — Templates as wedge into marketing ops?
You:   Addressing P0, then moving on. Now do the full PRD.
Product Dev OS:  Brief exists — abbreviating Phase 1, starting with detailed requirements. Ready for Phase 2?
```

---

## How it works

```
                    ┌─────────────────────────┐
                    │       PM POV            │
                    │   (your point of view)  │
                    └────────────┬────────────┘
                                │
              ┌─────────────────┼─────────────────┐
              │                                   │
              ▼                                   ▼
┌─────────────────────────┐         ┌─────────────────────────┐
│    Feature Context      │         │    Company Context      │
│   (raw evidence)        │         │  (strategy & goals)     │
└─────────────┬───────────┘         └───────────┬─────────────┘
              │                                 │
              └────────────┬────────────────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │  Artifact Hub   │
                  │  (routes to     │
                  │   the right     │
                  │   workflow)     │
                  └────────┬────────┘
                           │
        ┌──────────┬───────┼───────┬──────────┐
        ▼          ▼       ▼       ▼          ▼
     Brief       PRD   Prototype  GTM      Docs
                                1-Pager
```

**Three inputs feed every artifact:**

1. **PM POV** (point of view) — your read on the problem, why it matters, your hypothesis, your worries, your conviction level. This is the primary framing — the AI builds on your judgment, not around it.
2. **Feature Context** — raw evidence. Customer quotes, support tickets, sales feedback, competitive intel. Messy is fine.
3. **Company Context** — your product vision, north star metrics, quarterly goals, and design principles. Set once, reuse everywhere.

**Conviction-based AI behavior:**

| Your conviction | AI mode |
|-----------------|---------|
| High (80–100%) | **Sharpen.** Strengthen your framing with evidence. Push for precision. |
| Moderate (60–79%) | **Sharpen and challenge.** Build out the framing but also surface 1–2 pressure-test questions. If the PM added conviction notes (e.g. high on problem, low on solution), use those to calibrate. |
| Low (< 60%) | **Challenge.** Pressure-test the hypothesis. Surface alternatives. Ask harder questions. |

**Phased workflows with persona reviews:** Each artifact is Draft → Review → Revise. The AI simulates the right stakeholders (CEO/Founder, Tech Lead, Design Lead, QA, GTM, Support, Legal, Data Science) and tags feedback P0/P1/P2. Not every artifact uses every persona. Personas live in `System/Personas/` — add, remove, or edit to match your team.

---

## Personas

Personas are AI-simulated stakeholders used during the Review phase of each workflow. They give you structured feedback from different roles so you can pressure-test artifacts without scheduling meetings. Each persona focuses on a different slice of the artifact (strategy, engineering, UX, compliance, etc.); feedback is tagged P0/P1/P2 so you know what to fix first. Add, remove, or edit personas in `System/Personas/` to match your team.

| Persona | Description |
|----------|--------------|
| **CEO/Founder** | Strategic lens: right investment at the right time, ROI, opportunity cost, scope prioritization. |
| **Tech Lead** | Engineering reality check: feasibility, architecture, dependencies, risk, build-vs-buy. |
| **Design Lead** | User's advocate: intuitive workflows, cognitive load, edge-case UX, simplification. |
| **QA Lead** | Failure-case thinker: acceptance criteria, edge cases, testability, release readiness. |
| **GTM Lead** | Market-facing strategist: positioning, adoption, packaging/pricing, launch and enablement. |
| **Support Lead** | Customer confusion anticipator: error messaging, documentation, post-launch monitoring. |
| **Legal Lead** | Risk and compliance guardrail: regulatory, contractual, data privacy, disclosures. |
| **Data Science Lead** | Measurement reality check: instrumentable goals, event design, metrics, guardrails. |

---

## Working with the repo

Your working copies are always in the feature folder (`Features/[name]/`); don't edit files in `System/Templates/`. The always-on Product Dev OS rule routes other artifact requests (e.g. "write the PRD") to the right workflow. **Cursor:** type **`@new-feature`** to kick off. **Claude Code:** same; `CLAUDE.md` loads automatically.

---

## Project structure

```
System/
├── artifact-hub.md              ← Registry for the AI (workflow routing)
├── company-context.md           ← Your company strategy (fill this in)
├── Workflows/
│   ├── prd-workflow.md          ← 4-phase PRD process
│   ├── product-brief-workflow.md
│   ├── prototype-workflow.md
│   ├── gtm-one-pager-workflow.md
│   └── external-docs-workflow.md
├── Templates/
│   ├── pm-pov-template.md        ← Input: PM's point of view
│   ├── feature-context-template.md ← Input: raw evidence
│   ├── prd-template.md          ← Output format for PRDs
│   ├── product-brief-template.md
│   ├── gtm-one-pager-template.md
│   └── external-docs-template.md
└── Personas/
    ├── ceo-founder.md
    ├── tech-lead.md
    ├── design-lead.md
    ├── qa-lead.md
    ├── gtm-lead.md
    ├── support-lead.md
    ├── legal-lead.md
    └── data-science-lead.md

Features/                        ← Per-feature working docs and outputs (created as you go)
└── [feature-name]/
    ├── pm-pov.md
    ├── feature-context.md
    └── (artifact outputs: prd.md, product-brief.md, prototype.html, etc.)
```

---

## Customization

- **Personas:** Edit `System/Personas/` and update assignments in `System/artifact-hub.md`. Default set is typical product team; add/remove (e.g. Compliance for fintech, drop GTM for consumer).
- **Company context:** `System/company-context.md` — set once, reused for every artifact.
- **Templates:** Edit `System/Templates/` to add sections or change output format; workflows pick them up.

---

## Who this is for

PMs who use AI coding tools and want structured artifacts with real review — not generic output. Best fit: teams shipping features on an existing product (strategy, users, and context already in place), not greenfield 0-to-1 builds. The AI challenges when you're uncertain and sharpens when you're confident. Stakeholder perspectives without six meetings. Lives in your editor; grounded in your company context.

---

## License

MIT
