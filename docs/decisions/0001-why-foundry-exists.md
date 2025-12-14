# ADR 0001 — Why Foundry Exists

**Status:** Accepted  
**Date:** 2025-12-14

## Context
Over time, building multiple internal and experimental tools has repeatedly required re-deciding basic infrastructure, UI patterns, and architectural structure. This introduces cognitive overhead, loss of momentum, and reduced confidence when starting new projects.

Existing frameworks and starter kits tend to optimize for production readiness or scale, rather than calm, repeatable prototyping with architectural clarity and taste.

## Decision
Create **Foundry** as a personal prototyping runtime:
- A collection of reusable libraries
- Accompanied by explicit documentation of principles and decisions
- Optimized for fast spin-up, clarity, and long-term reuse

Foundry prioritizes:
- opinionated defaults
- explicit reasoning
- composability over completeness

## Consequences
- Foundry is intentionally personal and opinionated
- Architectural decisions are documented, not implied
- The system favors clarity over trend adoption

## Alternatives Considered
- Ad-hoc starter repositories (rejected due to drift and repetition)
- Using existing frameworks wholesale (rejected due to loss of ownership)
