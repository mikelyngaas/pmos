# Interactive Prototype Workflow

This document defines the process for generating a mid-fidelity, clickable HTML prototype that visualizes key workflows from a Product Brief or PRD. You can run this as soon as a Product Brief exists (concept-level prototype) or after a PRD (detailed prototype). The output is a single self-contained HTML file that opens in any browser — no build step, no dependencies.

## When to Use

- Stakeholders need to *see* what you're building, not just read about it
- You want to pressure-test a workflow's UX before detailed design begins
- Pairing with a Product Brief for early alignment, or with a PRD for pre-build validation
- Communicating the feature to people who don't read PRDs (execs, customers, partners)

## Inputs

Requires at least one of:

1. **Product Brief** (`Features/[feature-name]/product-brief.md`) — produces a higher-level prototype focused on key workflows and navigation
2. **Full PRD** (`Features/[feature-name]/prd.md`) — produces a more detailed prototype with specific UI states, edge cases, and requirement coverage

Also read:
- **`System/company-context.md`** — for product context and mental model

**Optional (for a more true-to-form prototype):** Prompt the PM to provide design system or reference artifacts — e.g. design tokens (colors, typography, spacing), brand guidelines, screenshots of existing product UI, or component patterns. If they upload or link these (in the feature folder or in chat), use them when generating the prototype so it better matches their product. If they don't have any, proceed with the default design language below.

If neither a Product Brief nor a PRD exists for this feature, tell the user and offer to create one first.

**Company context check:** At the start of the workflow, read `System/company-context.md`. If it is effectively empty (only placeholders), tell the user: "Company context isn't set; product context for the prototype will be generic. Set it up now, or proceed anyway?" Let the user choose before continuing.

## Output

`Features/[feature-name]/prototype.html` — a single self-contained HTML file.

---

## Technical Constraints

The prototype must be:
- **Single file.** One `.html` file with all CSS and JS inline. No external dependencies, no CDN links, no frameworks.
- **Opens in any browser.** Double-click the file and it works.
- **Mid-fidelity.** Clean, structured, and clear — not pixel-perfect production UI. Think wireframe with enough detail to understand the experience.
- **Clickable.** Key interactions work: navigation between screens, button clicks that reveal state changes, tab switching, modal opens/closes. No real data or API calls.

### Design Language

- Clean sans-serif typography (system fonts)
- Neutral color palette with one accent color for primary actions
- Clear visual hierarchy: headers, cards, tables, buttons
- Consistent spacing and alignment
- Responsive is nice-to-have, not required — optimize for desktop

### Interaction Patterns

Use JavaScript to handle:
- **Screen navigation** — clicking a nav item or CTA switches the visible screen
- **State changes** — buttons toggle states (e.g., empty → populated, collapsed → expanded)
- **Modals and overlays** — triggered by buttons, dismissed by close/backdrop click
- **Tab switching** — within a screen, if applicable

Keep interactions simple. The goal is to communicate the workflow, not build a functional app.

---

## How It Works

### Step 1 — Scope the Prototype

Read the source artifact and identify which workflows to prototype. Ask the user:

- "Which workflows from the brief/PRD are most important to visualize?"
- "Are there specific screens or states you want to see?"
- "Do you have a design system or reference artifacts to make the prototype true to form?" Prompt for design tokens (colors, typography, spacing), brand guidelines, screenshots of existing product UI, or component patterns. If they provide any — via upload to the feature folder or in chat — use them when generating the prototype; otherwise use the default design language below.

**Default scope:** If the user doesn't have a strong opinion, prototype the key workflows defined in the source artifact (Section 4.2 of the brief or PRD). Typically 3-6 screens covering the primary happy path.

Propose the screen list to the user and confirm before building.

### Step 2 — Generate the Prototype

Build the HTML file covering:

1. **Navigation structure** — how screens connect to each other and to the broader product
2. **Screen layouts** — content hierarchy, key UI elements, data display
3. **Interactive flows** — the clickable path through the core workflow
4. **Key states** — at minimum: default state and populated state. If the PRD is the source, also include empty states and error states where defined.

**Important:** Use realistic placeholder content, not "Lorem ipsum." If the source artifact describes a template gallery for outbound sequences, show actual template names and categories, not generic placeholders. Realistic content is what makes a prototype useful for stakeholder conversations.

### Step 3 — Present & Review

Show the user the prototype (they'll open the HTML file in their browser). Walk through:
- The screens you built and why
- The interaction flow
- What's represented vs. what's out of scope

Then simulate the **Design Lead** reviewing:

**Design Lead** focuses on:
- Does the flow feel intuitive? Are there confusing navigation patterns?
- Are key interaction moments (CTAs, state changes) clear?
- What's missing from the UX that would confuse a stakeholder viewing this?

The AI should also check:
- Does the prototype faithfully represent the workflows from the brief/PRD?
- Are there requirements or workflows that should be visualized but aren't?
- Would a stakeholder understand the feature experience from this prototype alone?

Present feedback with P0/P1/P2 priority tags.

### Step 4 — Iterate

Update the HTML file based on feedback. Common iterations:
- Adding missing screens or states
- Adjusting layout or content hierarchy
- Adding interactions that were overlooked
- Refining placeholder content for realism

Before calling the prototype done, verify it meets the **Interactive Prototype** quality bar in `System/quality-bars-draft.md`. If it doesn't, list the gaps and ask the PM: address them or explicitly accept and proceed? The PM can override. The user confirms when the prototype is ready.

---

## Workflow Rules

### Pacing
- Scope confirmation (Step 1) is the critical checkpoint — don't build without it
- The user can skip the persona review if time is tight
- Iteration can happen across multiple sessions — the HTML file is durable

### Fidelity Calibration
- **From a Product Brief:** Higher-level. Focus on navigation and workflow flow. Fewer screens, less detail per screen. Think "concept demo."
- **From a PRD:** More detailed. Cover specific requirements, edge states, and UI details from the requirements table. Think "design review artifact."

### What the Prototype Is NOT
- Not a design spec. Designers will still do proper UI design.
- Not a functional app. No real data, no real API calls, no real authentication.
- Not pixel-perfect. Visual polish is secondary to workflow clarity.
- Not a testing tool. It demonstrates the concept; it doesn't validate it.
