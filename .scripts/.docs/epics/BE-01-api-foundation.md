# EPIC BE-01 — API Foundation (Clean Architecture)

**Track:** Backend  
**Status:** `[x]` Done

## Description
Establish the foundational .NET API project structure following Clean Architecture principles.
This epic covers the skeleton that every other backend epic builds upon: layered project references, dependency injection, cross-cutting middleware, and infrastructure-level concerns like logging and health checks.

## Goal
Deliver a running, deployable API skeleton with correct layer boundaries, observable by default, and ready to host business use cases.

## Acceptance Criteria
- [x] Four projects exist and compile: `Domain`, `Application`, `Infrastructure`, `Api`.
- [x] Project references enforce inward dependencies only (`Api` → `Application` → `Domain`; `Infrastructure` → `Application`).
- [x] DI container is configured in `Api`; no concrete service instantiated with `new` outside of DI.
- [x] Global error handling returns `ProblemDetails`-compliant JSON for all unhandled exceptions.
- [x] Stack traces are never exposed in error responses.
- [x] Structured logging includes a `correlation-id` on every request.
- [x] `GET /health` returns `200 OK` when the service is healthy.
- [x] Build pipeline is green with no compiler warnings.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-01-01 | Define project layer structure | `[x]` |
| BE-01-02 | Configure DI container and project references | `[x]` |
| BE-01-03 | Add global error handling middleware (ProblemDetails) | `[x]` |
| BE-01-04 | Configure structured logging with correlation id | `[x]` |
| BE-01-05 | Add health check endpoint | `[x]` |
