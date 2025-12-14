# Foundry  
## Personal Prototyping Runtime — PRD

---

## 1. Overview

**Foundry** is a personal prototyping runtime for building full-stack tools with speed, clarity, and opinionated structure.

It exists to eliminate setup friction and decision fatigue when building multiple internal or experimental products — while preserving taste, architectural clarity, and long-term confidence.

Foundry is not a framework.  
It is a **system of reusable toolkits + documented thinking** that enables calm, repeatable product creation.

---

## 2. Problem Statement

Over time, building tools repeatedly introduces unnecessary friction:

- Re-deciding UI patterns and component behavior
- Re-implementing basic infrastructure (auth, data, errors)
- Losing momentum during project spin-up
- Architecture decisions living only in memory, not documentation

This results in:
- Slower starts
- Lower confidence in system design
- Energy spent on plumbing instead of product thinking

**Foundry exists to remove this friction permanently.**

---

## 3. Vision

> *“I can sit down with a new idea and have a coherent, well-structured tool running quickly — without compromising on design, clarity, or architectural intent.”*

Success feels like:
- Calm project beginnings
- Clear separation of concerns
- Reusable libraries I trust
- Opinions I can explain and defend
- Documentation that compounds over time

---

## 4. Non-Goals

Foundry is **not** intended to be:

- A production-grade enterprise platform
- A public framework (at least initially)
- A monolithic application
- An experiment in abstraction for abstraction’s sake

Explicitly out of scope:
- Microservices
- Heavy infrastructure orchestration
- Premature scalability optimizations
- Trend-driven technology choices

---

## 5. Core Principles (Non-Negotiable)

### 5.1 Self-Constituted Opinions
Every major architectural decision must:
- Be intentional
- Be documented
- Have a clear replacement path

If a decision is undocumented, it is not truly owned.

---

### 5.2 Separation of Concerns
Clear boundaries must exist between:

- UI and state
- State and data
- Data and transport
- Core logic and frameworks

Everything should be replaceable without disturbing core abstractions.

---

### 5.3 Libraries Over Applications
- Applications are thin shells
- Libraries contain truth
- Reuse is deliberate, not accidental

---

### 5.4 Elegance Over Cleverness
- Explicit over magical
- Predictable over flexible
- Fewer primitives, better understood

---

## 6. Target Use

### Primary User
My future self — working across:
- Personal machines
- Office environments
- Multiple tools and domains (dashboards, PLM, brand systems, data tools)

### Secondary (Future)
Trusted collaborators who may consume parts of Foundry.

---

## 7. System Scope

Foundry is a **collection of independent, composable toolkits**, supported by documentation.

### High-level structure:

- UI foundations
- Runtime shell
- Data access layer
- State conventions
- Backend starter template
- Documentation and decision records

---

## 8. Infrastructure Pillars

### 8.1 Design Tokens

**Goal:**  
Own the visual language without reinventing UI primitives.

**Responsibilities:**
- Color, spacing, typography, radius tokens
- CSS variable output
- Typed token access

**Artifact:**
- `@foundry/tokens`

Tokens are the single source of truth for visual decisions.

---

### 8.2 UI Toolkit

**Goal:**  
Accessible, consistent UI with minimal maintenance cost.

**Strategy:**
- Build on top of industry-standard primitives (Radix)
- Use shadcn-style source ownership
- Curate a small, intentional component surface

**Responsibilities:**
- Core UI components (Button, Input, Dialog, Table, etc.)
- Accessibility and keyboard behavior
- Storybook documentation

**Artifact:**
- `@foundry/ui`

Applications must never import Radix directly.

---

### 8.3 Runtime & App Shell

**Goal:**  
Remove repetitive app scaffolding.

**Responsibilities:**
- App layout primitives
- Routing conventions
- Error boundaries
- Toasts and notifications
- Page-level patterns

**Artifact:**
- `@foundry/runtime`

---

### 8.4 Data & Server State

**Goal:**  
Typed, predictable data access with minimal backend anxiety.

**Responsibilities:**
- API client
- Unified error shape
- Schema validation at boundaries
- Caching and refetch rules
- Mock adapter for no-backend prototyping

**Artifact:**
- `@foundry/data`

---

### 8.5 State Model

State is intentionally categorized:

1. **Server State**  
   Remote data, cached and synchronized.

2. **Client/UI State**  
   Local, ephemeral preferences and toggles.

3. **Workflow State**  
   Multi-step, constrained flows where transitions matter.

**Rules:**
- Server state does not live in global UI stores
- Workflow logic must be explicit and diagrammable
- State machines are used only when justified

---

### 8.6 Forms & Validation

**Goal:**  
Consistent form behavior across tools.

**Responsibilities:**
- Standard form setup
- Validation rules
- Error display conventions
- Async submit handling

Forms should feel predictable across all tools.

---

### 8.7 Authentication (Lightweight)

**Goal:**  
Enough realism for internal tools without ceremony.

**Responsibilities:**
- Pluggable auth interface
- Token-based flows
- Role awareness (admin/editor/viewer)
- Development bypass mode

---

### 8.8 Backend Starter Template

**Goal:**  
Provide a sane backend baseline without enforcing it.

**Responsibilities:**
- API structure
- Validation and error handling
- Auth middleware
- Database adapter (Mongo initially)
- Seed data for prototyping

**Artifact:**
- `apps/api-template`

This is a template, not a mandatory dependency.

---

### 8.9 Files & Storage

**Goal:**  
Support uploads without coupling to cloud providers.

**Strategy:**
- Local adapter for development
- Interface for future cloud storage

---

### 8.10 Observability & Debugging

**Goal:**  
Understand failures quickly.

**Responsibilities:**
- Structured logging interface
- Error boundary reporting
- Optional debug panel for internal tools

---

## 9. Documentation as Infrastructure

Documentation is a first-class artifact.

### Required documents:
- `PRD.md` (this document)
- `principles.md`
- `roadmap.md`
- `/decisions/*` (Architecture Decision Records)

**Rule:**  
If something is reusable, it must be documented.

---

## 10. Distribution & Portability

Foundry is designed to be:
- Used across machines
- Installed as private npm packages
- Versioned and released intentionally

Publishing strategy must support:
- Personal experimentation
- Office environment constraints

---

## 11. Phase 1 Scope (Initial Build)

Deliverables:
- Monorepo scaffold
- Tokens + core UI components
- Runtime shell
- Data client + mock adapter
- Backend template
- Sandbox app proving the system
- Documented principles and decisions

---

## 12. Success Criteria

Foundry is successful if:

- New tool setup time is under one hour
- No recurring debates about basic structure
- Architectural decisions are explainable
- Starting new projects feels calm and deliberate

---

## 13. Open Questions (Intentionally Left Open)

- Degree of Tailwind vs vanilla CSS usage
- When workflow state machines become necessary
- How public Foundry becomes over time
- Which domains deserve dedicated packages

These are expected to evolve and will be documented as decisions.

---

## Closing Note

Foundry is not about speed alone.

It is about becoming someone who can **design systems repeatedly, with clarity and composure**, without losing taste or confidence.

This repository is both a toolkit and a record of thinking.
