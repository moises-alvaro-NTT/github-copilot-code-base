# EPIC FE-04 — Feature Modules

**Track:** Frontend  
**Status:** `[x]` Done

## Description
Implement the feature-first module structure with a typed API client layer and the first complete feature module (route, page, data hook, loading/empty/error states).
This epic establishes the pattern that all future features will follow.

## Goal
Deliver a working, production-grade first feature module that demonstrates the agreed architecture and can be used as a reference for all future modules.

## Acceptance Criteria
- [x] Features are organized under `features/<feature-name>/` with co-located components, hooks, and tests.
- [x] A typed API client layer exists in `lib/api/` with Zod-validated response schemas.
- [x] The first feature module includes: route definition, page component, data hook using TanStack Query.
- [x] Loading, empty, and error states are rendered consistently and tested.
- [x] No business logic lives directly inside page components.
- [x] All API call results are typed and validated at the boundary — no `any` types.
- [x] Feature module has unit tests for the data hook and component tests for all states.

## Tasks
| ID | Task | Status |
|---|---|---|
| FE-04-01 | Define feature-first folder structure | `[x]` |
| FE-04-02 | Implement typed API client layer | `[x]` |
| FE-04-03 | Add first feature module (route + page + data hook) | `[x]` |
| FE-04-04 | Handle loading, empty, and error states consistently | `[x]` |
