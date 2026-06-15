# EPIC FE-02 — Core Libraries Integration

**Track:** Frontend  
**Status:** `[x]` Done

## Description
Integrate and configure the shared libraries that all features will use: routing, data fetching, form handling, state management, and utility helpers.
Each library must be configured at project level and validated with a basic working example.

## Goal
Deliver a configured, working integration of all core libraries so features can build on a consistent foundation without re-inventing boilerplate.

## Acceptance Criteria
- [x] React Router is installed and a root router with at least two placeholder routes renders correctly.
- [x] TanStack Query is configured with a `QueryClient` and global error/loading defaults.
- [x] React Hook Form is installed and a sample form with Zod resolver validates and submits correctly.
- [x] Zod schemas are the single source of truth for form validation and API response shapes.
- [x] Zustand is available and a minimal store example works (only add for shared cross-feature state).
- [x] `clsx` and `tailwind-merge` are wrapped in a shared `cn()` utility function.
- [x] All library integrations are covered by at least one working example test or story.

## Tasks
| ID | Task | Status |
|---|---|---|
| FE-02-01 | Add React Router and define route structure | `[x]` |
| FE-02-02 | Configure TanStack Query with base client | `[x]` |
| FE-02-03 | Add React Hook Form + Zod resolvers | `[x]` |
| FE-02-04 | Add Zustand for shared state (when needed) | `[x]` |
| FE-02-05 | Add clsx + tailwind-merge utilities | `[x]` |
