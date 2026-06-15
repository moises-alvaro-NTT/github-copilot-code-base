---
name: frontend-testing-quality
description: Improve React frontend quality through deterministic tests, accessibility checks, and behavior-first coverage.
---

# Frontend Testing Quality Skill

## When to Use
- Create or improve frontend test suites.
- Reduce UI regressions.
- Standardize testing conventions across components.

## Flow
1. Identify critical user journeys and fragile interactions.
2. Add component tests for behavior and accessibility.
3. Add integration tests for async and multi-step flows.
4. Ensure loading/empty/error states are covered.
5. Report uncovered risks and next priority tests.

## Quality Rules
- Prefer user-observable assertions.
- Keep tests deterministic and independent.
- Avoid snapshots as the main safety net.
- Validate error handling and retry behavior.

## Output Artifacts
- List of added/updated tests.
- Residual risks not covered.
- Prioritized next quality improvements.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
