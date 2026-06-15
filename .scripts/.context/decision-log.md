# Decision Log (Lightweight ADR)

Tracks important technical decisions.

## Template
### ADR-XXXX - Short title
- Date: YYYY-MM-DD
- Status: Proposed | Accepted | Deprecated
- Context:
- Decision:
- Consequences:
- Alternatives Considered:

## Entries
### ADR-0001 - Adopt Clean Architecture
- Date: 2026-05-25
- Status: Accepted
- Context: Team scalability and long-term maintainability are required.
- Decision: Split into Domain, Application, Infrastructure, and Api layers.
- Consequences: Higher design discipline and better testability.
- Alternatives Considered: Layered monolithic architecture without strict boundaries.
