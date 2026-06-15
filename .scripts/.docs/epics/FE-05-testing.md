# EPIC FE-05 — Testing

**Track:** Frontend  
**Status:** `[x]` Done

## Description
Establish a comprehensive frontend test suite covering hooks, shared components, async flows, and form validation.
All tests follow the agreed English naming convention and AAA structure.

## Goal
Deliver a reliable test suite that catches UI regressions and documents expected component behavior.

## Acceptance Criteria
- [x] Unit tests exist for all shared hooks and utility functions.
- [x] Component tests exist for all shared UI components covering: default, loading, empty, error, and interactive states.
- [x] Integration tests cover the critical async data-fetching flows with mocked network boundary.
- [x] Form tests cover: valid submission, field-level validation errors, and server-side error display.
- [x] All test names use `ComponentOrHook_Condition_ExpectedResult` convention.
- [x] All test names, comments, and data labels are in English.
- [x] Assertions use accessible queries (`getByRole`, `getByLabelText`) over `getByTestId` where possible.
- [x] No snapshot-only tests for behavior-critical components.

## Tasks
| ID | Task | Status |
|---|---|---|
| FE-05-01 | Unit tests for hooks and utilities | `[x]` |
| FE-05-02 | Component tests for shared UI (behavior + accessibility) | `[x]` |
| FE-05-03 | Integration tests for critical async flows | `[x]` |
| FE-05-04 | Form validation and submission error tests | `[x]` |
| FE-05-05 | Enforce `ComponentOrHook_Condition_ExpectedResult` naming | `[x]` |
