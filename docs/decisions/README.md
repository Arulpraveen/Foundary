# ADR Index & Rules

## What is an ADR?
An Architecture Decision Record (ADR) captures an important decision, its context, and consequences.

## Where they live
`docs/decisions/`

## Naming
`000X-short-kebab-title.md`

## Status values
- Proposed
- Accepted
- Superseded (by ADR ####)
- Deprecated

## Amending decisions
- If the decision changes, write a new ADR and mark the old one as **Superseded**.
- If only clarifying text without changing the decision, add an **Amendments** section with date and note.

## Cross-references
- New ADRs should reference the ADRs they supersede.
- Superseded ADRs should point to the replacing ADR in the header.
