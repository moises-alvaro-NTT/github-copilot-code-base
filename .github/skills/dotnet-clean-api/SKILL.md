---
name: dotnet-clean-api
description: Implement and evolve a .NET API with Clean Architecture, lightweight CQRS, and maintainability best practices.
---

# Dotnet Clean API Skill

## When to Use
- Create new endpoints.
- Implement use cases.
- Refactor to separate responsibilities by layer.
- Add validations, error handling, and contracts.

## Do Not Use For
- Cloud infrastructure changes unrelated to API code.
- Large-scale stack migrations outside .NET.

## Recommended Flow
1. Define use case and input/output contract.
2. Implement business logic in Domain/Application.
3. Adapt persistence/integrations in Infrastructure.
4. Expose endpoint in Api without business logic.
5. Add unit tests and minimal integration tests.

## Checklist
- Respect dependency direction.
- Use async and CancellationToken where applicable.
- Handle errors consistently.
- Include tests for new behavior.
- Update `.context/` if architecture changes.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
