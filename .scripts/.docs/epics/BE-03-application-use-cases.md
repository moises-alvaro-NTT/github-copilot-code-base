# EPIC BE-03 — Application Use Cases

**Track:** Backend  
**Status:** `[x]` Done

## Description
Implement the Application layer as the orchestration hub between the API and the domain.
Each capability is represented by one interface in `Application/Contracts` and one handler/service implementation. Request DTOs are validated before any business logic executes.

## Goal
Deliver a set of use case handlers fully covered by unit tests, with validated inputs, correct orchestration, and no dependency on persistence technology.

## Acceptance Criteria
- [x] Every new business capability has a corresponding interface defined in `Application/Contracts`.
- [x] No interface is instantiated with `new` in the Application layer itself — implementations live in Infrastructure.
- [x] All request DTOs are validated with FluentValidation before the handler executes.
- [x] Handlers do not directly reference `DbContext` or any ORM type.
- [x] Each handler is covered by unit tests for success, validation failure, and domain error paths.
- [x] All public members have XML documentation comments.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-03-01 | Define Application contracts (interfaces) for each capability | `[x]` |
| BE-03-02 | Implement use case handlers | `[x]` |
| BE-03-03 | Add FluentValidation for request DTOs | `[x]` |
| BE-03-04 | Unit tests for use cases | `[x]` |
