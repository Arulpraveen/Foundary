# ADR 0002 — Libraries Over Applications

**Status:** Accepted  
**Date:** 2025-12-14

## Context
Applications tend to accumulate assumptions, shortcuts, and coupling that make reuse difficult. Reusing application code often introduces more friction than value.

Reusable thinking and structure live more reliably in libraries than in applications.

## Decision
Foundry will be structured primarily as **libraries**, not applications.

- Applications act as thin shells used for validation
- Core logic, UI, and infrastructure live in publishable packages
- Applications may be discarded without loss of core value

## Consequences
- Initial setup may feel more deliberate
- Reuse becomes intentional and reliable
- Long-term confidence increases when starting new tools

## Alternatives Considered
- Monolithic starter application (rejected due to poor portability)
- Copy-paste reuse across projects (rejected due to drift and inconsistency)
