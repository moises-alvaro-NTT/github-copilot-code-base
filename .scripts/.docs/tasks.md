# Project Task Tracker

Tracks epics, tasks, and progress across Backend and Frontend tracks.

**Legend:** `[ ]` Not started · `[~]` In progress · `[x]` Done · `[!]` Blocked

---

## BACKEND TRACK

### EPIC BE-01 — API Foundation (Clean Architecture)

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-01-01 | Define project layer structure (Domain, Application, Infrastructure, Api) | `[x]` | |
| BE-01-02 | Configure DI container and project references | `[x]` | |
| BE-01-03 | Add global error handling middleware (ProblemDetails) | `[x]` | |
| BE-01-04 | Configure structured logging with correlation id | `[x]` | |
| BE-01-05 | Add health check endpoint | `[x]` | |

---

### EPIC BE-02 — Domain Model

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-02-01 | Define core entities and value objects | `[x]` | |
| BE-02-02 | Define domain events | `[x]` | |
| BE-02-03 | Implement domain rules and validation | `[x]` | |
| BE-02-04 | Unit tests for domain rules | `[x]` | |

---

### EPIC BE-03 — Application Use Cases

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-03-01 | Define Application contracts (interfaces) for each capability | `[x]` | |
| BE-03-02 | Implement use case handlers | `[x]` | |
| BE-03-03 | Add FluentValidation for request DTOs | `[x]` | |
| BE-03-04 | Unit tests for use cases | `[x]` | |

---

### EPIC BE-04 — Renegotiation Feature

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-04-01 | Define `IRenegotiationService` interface in Application | `[x]` | |
| BE-04-02 | Implement `RenegotiationService` in Infrastructure | `[x]` | |
| BE-04-03 | Register in DI | `[x]` | |
| BE-04-04 | Create thin `RenegotiationController` (no logic) | `[x]` | |
| BE-04-05 | Unit tests for service | `[x]` | |
| BE-04-06 | Integration tests for endpoint | `[x]` | |

---

### EPIC BE-05 — Persistence (Infrastructure)

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-05-01 | Configure EF Core DbContext | `[x]` | |
| BE-05-02 | Implement repositories with `AsNoTracking` read pattern | `[x]` | |
| BE-05-03 | Add migrations | `[x]` | |
| BE-05-04 | Integration tests for repositories | `[x]` | |

---

### EPIC BE-06 — Quality and Standards

| ID | Task | Status | Notes |
|---|---|---|---|
| BE-06-01 | Set up test projects (unit + integration) | `[x]` | |
| BE-06-02 | Enforce naming standard: `Method_Condition_ExpectedResult` | `[x]` | |
| BE-06-03 | Extract backend patterns to `.github/best-practices/backend-dotnet-api.md` | `[x]` | |
| BE-06-04 | Configure nullable and XML doc warnings in csproj | `[x]` | |

---

## FRONTEND TRACK

### EPIC FE-01 — Project Setup

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-01-01 | Scaffold React + TypeScript project | `[x]` | Vite or Next.js |
| FE-01-02 | Configure Tailwind CSS with design tokens | `[x]` | |
| FE-01-03 | Add ESLint + Prettier + strict TypeScript config | `[x]` | |
| FE-01-04 | Configure Vitest + React Testing Library | `[x]` | |
| FE-01-05 | Set up path aliases and folder structure | `[x]` | |

---

### EPIC FE-02 — Core Libraries Integration

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-02-01 | Add React Router and define route structure | `[x]` | |
| FE-02-02 | Configure TanStack Query with base client | `[x]` | |
| FE-02-03 | Add React Hook Form + Zod resolvers | `[x]` | |
| FE-02-04 | Add Zustand for shared state (when needed) | `[x]` | |
| FE-02-05 | Add clsx + tailwind-merge utilities | `[x]` | |

---

### EPIC FE-03 — Component Architecture

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-03-01 | Define shared UI component folder | `[x]` | |
| FE-03-02 | Create base design tokens (colors, spacing, typography) | `[x]` | |
| FE-03-03 | Implement variant system (class-variance-authority) | `[x]` | |
| FE-03-04 | Build foundational components (Button, Input, Card, Alert) | `[x]` | |
| FE-03-05 | Ensure keyboard nav and focus styles on all interactive components | `[x]` | |

---

### EPIC FE-04 — Feature Modules

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-04-01 | Define feature-first folder structure | `[x]` | |
| FE-04-02 | Implement typed API client layer | `[x]` | |
| FE-04-03 | Add first feature module (route + page + data hook) | `[x]` | |
| FE-04-04 | Handle loading, empty, and error states consistently | `[x]` | |

---

### EPIC FE-05 — Testing

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-05-01 | Unit tests for hooks and utilities | `[x]` | |
| FE-05-02 | Component tests for shared UI (behavior + accessibility) | `[x]` | |
| FE-05-03 | Integration tests for critical async flows | `[x]` | |
| FE-05-04 | Form validation and submission error tests | `[x]` | |
| FE-05-05 | Enforce `ComponentOrHook_Condition_ExpectedResult` naming | `[x]` | |

---

### EPIC FE-06 — Documentation and Playground

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-06-01 | Set up Storybook or Ladle | `[x]` | |
| FE-06-02 | Add stories for foundational components (all states) | `[x]` | |
| FE-06-03 | Document design tokens and Tailwind conventions | `[x]` | |
| FE-06-04 | Add accessibility notes per documented component | `[x]` | |
| FE-06-05 | Extract reusable patterns to `.github/best-practices/frontend-react-tailwind.md` | `[x]` | |

---

### EPIC FE-07 — Quality and Standards

| ID | Task | Status | Notes |
|---|---|---|---|
| FE-07-01 | Enforce strict TypeScript across all modules | `[x]` | |
| FE-07-02 | Validate all API boundaries with Zod | `[x]` | |
| FE-07-03 | Audit and fix accessibility on interactive components | `[x]` | |
| FE-07-04 | Code review with Frontend Code Reviewer agent | `[x]` | |

---

## CROSS-CUTTING

### EPIC CC-01 — GitHub Workflow

| ID | Task | Status | Notes |
|---|---|---|---|
| CC-01-01 | Finalize backend instructions and skills | `[x]` | Done |
| CC-01-02 | Finalize frontend instructions, skills, and agents | `[x]` | Done |
| CC-01-03 | Extract backend best practices | `[x]` | Done |
| CC-01-04 | Extract frontend best practices | `[x]` | Done |
| CC-01-05 | Configure GitHub PR workflow (instruction + skill + agent) | `[x]` | Done |
| CC-01-06 | Create this task tracker | `[x]` | Done |

---

## Progress Summary

| Track | Total Tasks | Done | In Progress | Not Started |
|---|---|---|---|---|
| Backend | 24 | 24 | 0 | 0 |
| Frontend | 29 | 29 | 0 | 0 |
| Cross-Cutting | 6 | 6 | 0 | 0 |
| **Total** | **59** | **59** | **0** | **0** |

---

*Last updated: 2026-05-26**
