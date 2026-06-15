# EPIC BE-02 — Domain Model

**Track:** Backend  
**Status:** `[x]` Done

## Description
Define the core business objects and rules that live exclusively in the `Domain` project.
Entities, value objects, and domain events capture the ubiquitous language and protect invariants without any dependency on infrastructure or frameworks.

## Goal
Deliver a complete domain layer with entities, value objects, domain events, and validated business rules, all covered by unit tests.

## Acceptance Criteria
- [x] All core entities are defined with private setters enforcing invariants.
- [x] Value objects are immutable and equality is value-based.
- [x] Domain events are defined and raised inside the entity aggregate root.
- [x] Domain layer has zero references to `Infrastructure`, `Application`, or any framework package.
- [x] Business rule violations throw typed domain exceptions or return typed results.
- [x] Unit test coverage exists for every domain rule and validation path.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-02-01 | Define core entities and value objects | `[x]` |
| BE-02-02 | Define domain events | `[x]` |
| BE-02-03 | Implement domain rules and validation | `[x]` |
| BE-02-04 | Unit tests for domain rules | `[x]` |
