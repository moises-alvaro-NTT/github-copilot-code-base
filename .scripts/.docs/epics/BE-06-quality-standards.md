# EPIC BE-06 — Quality and Standards

**Track:** Backend  
**Status:** `[x]` Done

## Description
Establish the quality baseline for the backend: test project structure, naming conventions, best-practice documentation, and compiler strictness settings.

## Goal
Ensure the backend codebase is consistently structured, well-documented, and enforces standards from day one.

## Acceptance Criteria
- [x] Separate test projects exist for unit tests and integration tests.
- [x] All test methods follow the naming convention `Method_Condition_ExpectedResult`.
- [x] All test names and comments are in English.
- [x] AAA sections are labelled (`// Arrange`, `// Act`, `// Assert`) when section comments are used.
- [x] `<Nullable>enable</Nullable>` is set in all production csproj files.
- [x] XML doc generation warnings are enabled and zero warnings exist in production projects.
- [x] At least one recurring pattern has been extracted to `.github/best-practices/backend-dotnet-api.md`.

## Tasks
| ID | Task | Status |
|---|---|---|
| BE-06-01 | Set up test projects (unit + integration) | `[x]` |
| BE-06-02 | Enforce naming standard: `Method_Condition_ExpectedResult` | `[x]` |
| BE-06-03 | Extract backend patterns to `.github/best-practices/backend-dotnet-api.md` | `[x]` |
| BE-06-04 | Configure nullable and XML doc warnings in csproj | `[x]` |
