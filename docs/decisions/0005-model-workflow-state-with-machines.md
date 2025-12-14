# ADR 0005 — Model Workflow State as Explicit State Machines

**Status:** Accepted  
**Date:** 2025-12-14

## Context
Some application logic represents processes rather than data. These processes have:
- explicit phases
- restricted transitions
- illegal state/action combinations

Representing such logic with booleans or ad-hoc conditionals leads to fragile systems that are difficult to reason about.

## Decision
Foundry will use **state machines (e.g. XState)** only for **workflow state**, defined as state that:
- progresses through named phases
- enforces transition rules
- benefits from being diagrammable

State machines are not used for:
- server state
- trivial UI state

## Consequences
- Workflow logic becomes explicit and resilient
- Simple UI remains lightweight
- State machines are treated as power tools, not defaults

## Alternatives Considered
- Using state machines for all state (rejected due to overhead)
- Using ad-hoc conditionals for workflows (rejected due to brittleness)
