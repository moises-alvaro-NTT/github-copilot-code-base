# EPIC BE-04 — Renegotiation Feature

**Track:** Backend  
**Status:** `[x]` Done

## Description
Implement the full vertical slice for contract renegotiation, from interface definition to HTTP endpoint.
The renegotiation logic must be fully encapsulated in the Application/Infrastructure layers. The controller must contain zero business logic — only call the interface and map the HTTP response.

## Goal
Deliver a production-ready renegotiation endpoint that is thin, fully tested, and follows the interface-injection pattern mandated by the project standards.

## Acceptance Criteria
- [x] `IRenegotiationService` interface is defined in `Application/Contracts` with XML docs.
- [x] `RenegotiationService` implements `IRenegotiationService` in `Infrastructure`.
- [x] `IRenegotiationService` is registered in DI with the correct lifetime (Scoped).
- [x] `RenegotiationController` contains no business logic, condition trees, or persistence calls.
- [x] The controller receives the interface via constructor injection only.
- [x] All public controller actions, service methods, and DTO properties have XML documentation.
- [x] Unit tests cover: successful renegotiation, validation failure, domain error.
- [x] Integration tests cover: `POST /api/renegotiations` happy path and validation error response.
- [x] Error responses conform to `ProblemDetails` format.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-04-01 | Define `IRenegotiationService` interface in Application | `[x]` |
| BE-04-02 | Implement `RenegotiationService` in Infrastructure | `[x]` |
| BE-04-03 | Register in DI | `[x]` |
| BE-04-04 | Create thin `RenegotiationController` (no logic) | `[x]` |
| BE-04-05 | Unit tests for service | `[x]` |
| BE-04-06 | Integration tests for endpoint | `[x]` |
