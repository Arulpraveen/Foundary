# ADR 0003 — Own Tokens, Compose on Industry Primitives

**Status:** Accepted  
**Date:** 2025-12-14

## Context
Building accessible UI primitives from scratch is costly and error-prone. Fully outsourcing UI decisions to third-party frameworks reduces ownership and long-term coherence.

A balance is required between accessibility, speed, and ownership.

## Decision
Foundry will:
- Own **design tokens** (colors, spacing, typography, radius)
- Compose UI components on top of **industry-standard primitives** (e.g. Radix)
- Use shadcn-style source ownership for composed components

Applications must not import third-party UI primitives directly.

## Consequences
- Accessibility is inherited rather than reimplemented
- Visual language remains consistent and owned
- Vendor dependencies are isolated behind Foundry APIs

## Alternatives Considered
- Fully custom UI primitives (rejected due to cost and maintenance burden)
- Fully consuming UI frameworks (rejected due to loss of control)
