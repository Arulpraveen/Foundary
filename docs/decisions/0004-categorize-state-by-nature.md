# ADR 0004 — Categorize State by Nature, Not by Tool

**Status:** Accepted  
**Date:** 2025-12-14

## Context
Modern frontend ecosystems provide multiple state management tools. Using a single tool for all types of state often leads to unnecessary complexity and misuse.

Different kinds of state have fundamentally different characteristics and constraints.

## Decision
Foundry explicitly categorizes state into three types:

1. **Server State** — remote data, cached and synchronized  
2. **Client/UI State** — local, ephemeral preferences and toggles  
3. **Workflow State** — multi-step, constrained processes

The nature of the state determines the strategy used to manage it.

## Consequences
- State decisions become intentional rather than habitual
- Overuse of complex tools is avoided
- Developers must identify the nature of state before choosing a solution

## Alternatives Considered
- Single global state solution (rejected due to misuse and overreach)
- Ad-hoc state without categorization (rejected due to inconsistency)
