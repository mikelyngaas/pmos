# [Feature Name] — Product Requirements Document

> **Author:** [Name]
> **Last Updated:** [Date]
> **Status:** Draft | In Review | Approved
> **Stakeholders:** [List key stakeholders]

---

## 0. Executive Summary

<!-- 1-4 sentences of prose: What customer problem does this feature solve and what is our proposed solution? -->

### 0.1 Outline
<!-- Auto-generated or manually maintained list of sections -->

- [1. Problem](#1-problem)
- [2. Historical Context](#2-historical-context)
- [3. Goals & Success Metrics](#3-goals--success-metrics)
- [4. Solution](#4-solution)
- [5. Rollout, GTM, and Enablement](#5-rollout-gtm-and-enablement)

---

## 1. Problem

> *This section synthesizes raw context from the companion feature context file into a clear, evidence-backed problem statement. See the feature context file for source material.*

### 1.1 Target Users
<!-- Who is this for? Define the primary and secondary user personas or segments. -->

### 1.2 Customer Problem(s)
<!-- What specific pain points or unmet needs are we solving? Be concrete — cite evidence where possible (support tickets, user interviews, data). -->

### 1.3 Why Current Solutions Fall Short
<!-- What are users doing today? Why is it insufficient, painful, or broken? -->

### 1.4 Why We Care About This Problem
<!-- Why does solving this matter for our business? Connect to company strategy, revenue, retention, or competitive positioning. -->

---

## 2. Historical Context *(Optional)*

> *Include this section for features with deep internal or external context — e.g., prior attempts, competitive landscape, or strategic shifts that inform this work.*

### 2.1 Prior Attempts & Lessons Learned
<!-- Have we tried to solve this before? What happened? What did we learn? -->

### 2.2 Competitive & Market Context
<!-- What are competitors doing in this space? What market signals are relevant? -->

### 2.3 Other Relevant Context
<!-- Any additional context the reader needs — regulatory changes, partner commitments, technical migrations, org changes, etc. -->

---

## 3. Goals & Success Metrics

### 3.1 Goals & Metrics
<!-- Each goal should have a direct line to how you'll measure success. If you can't measure a goal, sharpen it until you can. -->

| # | Goal | Metric | Type | Baseline | Target | How Measured |
|---|------|--------|------|----------|--------|--------------|
| 1 | | | North Star | | | |
| 2 | | | Input | | | |
| 3 | | | Input | | | |
| 4 | | | Guardrail | | | |

### 3.2 Non-Goals
<!-- What are we explicitly NOT trying to solve with this feature? This is just as important as goals for keeping scope tight. -->

---

## 4. Solution

### 4.1 Approaches Considered
> *Include when the scope is large enough to warrant evaluating multiple solution paths before diving into detailed requirements.*

| Approach | Summary | Pros | Cons | Verdict |
|----------|---------|------|------|---------|
| A | | | | |
| B | | | | |
| C | | | | |

### 4.2 Key Workflows & Journeys
<!-- What are the critical customer workflows and journeys we need to enable? Map these before going deep on requirements. Journey names here should match the subsection headers in 4.3.1 exactly. If there are supporting requirements (platform, infrastructure, edge states) that don't map to a user journey, note that here so the reader isn't surprised when they reach 4.3.1. -->

### 4.3 Detailed Requirements

> *Organize requirements around the customer journey — not by system component. Depending on the feature, this might follow a flow like Discover → Set Up → Execute → Report, or it might map to the customer's jobs to be done in their natural order. The goal: a reader should be able to follow requirements as a story of how the customer experiences the feature, end to end.*

#### 4.3.1 In Scope (V1)
<!-- Group requirements by journey phase. Use subheadings that match the journeys defined in 4.2 exactly. After the journey-mapped requirements, add a "Supporting Requirements" separator for platform/infrastructure and edge-state requirements that don't map to a user journey. -->

| # | Journey Phase | Requirement | Priority | Notes |
|---|---------------|-------------|----------|-------|
| 1 | | | Must have | |
| 2 | | | Must have | |
| 3 | | | Should have | |
| 4 | | | Nice to have | |

#### 4.3.2 Out of Scope (V1)
<!-- What are we deliberately deferring? This prevents scope creep and sets expectations. -->

### 4.4 Dependencies

> *Cross-functional or system dependencies required for this feature. Track what you need from other teams and whether it's committed.*

| # | Functional Requirement | Dependent System | Owning Team | Status |
|---|----------------------|-----------------|-------------|--------|
| 1 | | | | Committed / Not Committed / TBD |

### 4.5 Instrumentation *(Optional)*

> *Key events to implement so we can measure the goals in Section 3. Include when the feature has non-trivial measurement needs.*

| Event Name | Trigger (when fired) | Key Properties | Metric It Supports (from §3.1) |
|------------|----------------------|----------------|-------------------------------|
| | | | |

### 4.6 Edge Cases & Failure Modes

> *What happens when things go wrong or users do something unexpected? Populated during the QA review.*

| # | Scenario | Expected Behavior | Priority |
|---|----------|-------------------|----------|
| 1 | | | |

---

## 5. Rollout, GTM, and Enablement

### 5.1 Rollout Plan

| Phase | Audience | Entry Criteria | Exit Criteria | Duration |
|-------|----------|---------------|---------------|----------|
| Dogfood | Internal team | | | |
| Alpha | Select customers | | | |
| Beta | Broader cohort | | | |
| GA | All customers | | | |

### 5.2 Positioning & Messaging
<!-- How do we talk about this feature? What's the value prop? How does it fit in the product narrative? -->

### 5.3 Sales & Customer Enablement
<!-- What do customer-facing teams need to know? Any training, documentation, or collateral required? -->

### 5.4 Monetization & Packaging *(Optional)*

> *Include when the feature has pricing, packaging, or SKU implications.*

<!-- Does this feature fit into an existing SKU/plan tier, or does it need a new one? Is it a value driver that justifies a price change, or table stakes? Consider competitive packaging and the tradeoff between gating for revenue vs. opening for adoption. -->

| Question | Answer |
|----------|--------|
| Fits existing SKU/tier? | |
| New SKU or add-on needed? | |
| Plan-gated or available to all? | |
| Pricing impact | |
| Competitive packaging context | |

---

## Appendix: Decision Log

> *Single source of truth for all open questions and resolved decisions. Items start as Open and move to Decided as they're resolved during the PRD process.*

| # | Item | Status | Owner | Options Considered | Resolution | Date |
|---|------|--------|-------|--------------------|------------|------|
| 1 | | Open | | | | |

## Appendix: Assumptions

> *What are we assuming to be true? Calling these out explicitly helps catch blind spots.*

| # | Assumption | Risk if Wrong | How to Validate |
|---|-----------|---------------|-----------------|
| 1 | | | |
