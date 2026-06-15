# EPIC BE-05 — Persistence (Infrastructure)

**Track:** Backend  
**Status:** `[x]` Done

## Description
Configure EF Core and implement the persistence adapters in the `Infrastructure` layer.
Repositories implement the interfaces defined in `Application/Contracts` and abstract all ORM details from use cases.

## Goal
Deliver a working, tested persistence layer that is invisible to the Domain and Application layers.

## Acceptance Criteria
- [x] `DbContext` is configured in `Infrastructure` and registered in DI via an extension method.
- [x] All repository interfaces are defined in `Application/Contracts`.
- [x] Repository implementations live in `Infrastructure` only.
- [x] Read-only queries use `AsNoTracking()` consistently.
- [x] `ToList()` or `ToListAsync()` is called only at the final materialization point.
- [x] At least one migration exists and applies cleanly to a fresh database.
- [x] Integration tests cover create, read, update, and delete paths for core entities.
- [x] No repository exposes `IQueryable` outside Infrastructure.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-05-01 | Configure EF Core DbContext | `[x]` |
| BE-05-02 | Implement repositories with `AsNoTracking` read pattern | `[x]` |
| BE-05-03 | Add migrations | `[x]` |
| BE-05-04 | Integration tests for repositories | `[x]` |
