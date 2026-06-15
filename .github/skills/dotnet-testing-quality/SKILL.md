---
name: dotnet-testing-quality
description: Improve .NET API quality through testing strategy, linters, and maintainability rules.
---

# Dotnet Testing and Quality Skill

## When to Use
- Create or improve test suites.
- Reduce regressions.
- Standardize quality practices and definition of done.

## Flow
1. Identify critical behaviors.
2. Write unit tests for business rules.
3. Write integration tests for endpoints and persistence.
4. Verify error handling and authorization.
5. Review immediate technical debt.

## Quality Rules
- Deterministic and fast tests.
- Avoid excessive mocks in integration tests.
- Specific and useful assertions.
- Risk-focused coverage, not percentage-only.

## Output Artifacts
- List of added tests.
- Remaining uncovered risks.
- Prioritized recommendation for the next improvement.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
