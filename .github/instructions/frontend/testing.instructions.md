---
description: Testing strategy for React and Tailwind frontend
applyTo: "src/frontend/**/*.{test,spec}.{ts,tsx,js,jsx},**/*.stories.{ts,tsx,js,jsx}"
---

## Goal
Prevent UI regressions with fast, deterministic, and behavior-focused tests.

## Test Levels
- Unit/component: React Testing Library + Vitest.
- Integration: feature-level flows with mocked network boundaries.
- Visual/playground checks: stories for critical states.

## Rules
- One test validates one behavior.
- Prefer user-centric assertions over implementation details.
- Avoid brittle snapshot-only coverage.
- Cover loading, success, empty, and error states.
- Keep tests deterministic and independent.

## Naming Convention
- Use: `ComponentOrHook_Condition_ExpectedResult`.
- Keep test names and comments in English.

## Quality Standards
- Favor `screen` queries by accessible role and label.
- Mock network at request layer, not deep internals.
- Ensure forms test validation and submission errors.
- Include accessibility checks in critical interaction tests.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
