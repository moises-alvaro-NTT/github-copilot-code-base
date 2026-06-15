---
description: Rules for building .NET APIs with Clean Architecture
applyTo: "**/*.cs,**/*.csproj,**/*.sln,**/*.json,**/*.http,**/*.yaml,**/*.yml"
---

## Core Rules
- Implement layered architecture: Domain, Application, Infrastructure, Api.
- Avoid cyclic dependencies.
- All business logic lives in Domain/Application.
- For every new business capability, define an interface in Application and inject it via DI.
- Never instantiate business services directly with `new` inside controllers.

## Renegotiation Encapsulation
- Any renegotiation logic must be encapsulated in a dedicated Application use case or domain service.
- Expose renegotiation behavior through an interface (for example, `IRenegotiationService` or `IRenegotiationUseCase`).
- Controllers must only call the interface and map the HTTP response.

## Endpoints
- Keep endpoints thin: receive request, call use case, return response.
- Do not access DbContext directly from controllers.
- Use explicit request/response contracts.
- Do not implement business rules, condition trees, or persistence logic in controllers.

## Use Cases
- One handler/use case per action.
- Validate before executing business logic.
- Do not mix validation, mapping, and persistence in one large block.

## Commenting Standard
- All generated code must be commented.
- Public types and public members must include XML documentation comments.
- Methods must include brief intent comments describing purpose, input expectations, and side effects.
- Complex branches and business decisions must include inline explanatory comments.
- Keep comments updated when code changes.

## Persistence
- Repositories are only for data access.
- Keep queries efficient and paginated when applicable.
- Manage transactions explicitly when multiple writes occur.

## Errors
- Standardize errors with ProblemDetails or an equivalent contract.
- Never return stack traces to clients.
- Keep internal logs with correlation id.

## Performance
- Avoid early `ToList()` in EF Core queries.
- Use `AsNoTracking()` for read-only queries.
- Use cache only where it provides clear value and has explicit invalidation.

## PR Checklist
- Build succeeds and tests pass.
- Layering rules remain intact.
- Includes tests for new behavior.
- Changes are documented if architecture or API contracts are modified.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
