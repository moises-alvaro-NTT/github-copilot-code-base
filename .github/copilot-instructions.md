# Copilot Instructions — Backend and Frontend

## Repository Goal
Build and maintain a robust, testable, and maintainable product with two explicit tracks:
- **Backend**: .NET API with Clean Architecture and tactical DDD.
- **Frontend**: React + Tailwind UI with clear component architecture.

---

## Architecture Split

### Backend (.NET)
- `src/backend/Domain`: entities, value objects, domain events, pure business rules.
- `src/backend/Application`: use cases, DTOs, contracts (interfaces), validations, orchestration.
- `src/backend/Infrastructure`: persistence, external integrations, contract implementations.
- `src/backend/Api`: HTTP endpoints, authentication/authorization, serialization, DI wiring.
- `tests`: backend unit, integration, and contract tests.

### Frontend (React + Tailwind)
- `src/frontend/src/app`: route-level pages and app bootstrapping.
- `src/frontend/src/features`: feature-based modules.
- `src/frontend/src/components`: shared UI components.
- `src/frontend/src/lib`: API client, hooks, schemas, and helpers.
- `src/frontend/src/styles`: global styles and Tailwind layer extensions.
- `src/frontend/tests` or `src/frontend/src/**/*.test.*`: frontend tests.

---

## Customization Reference

### Instructions (applied automatically by file pattern)
- Backend API rules: `.github/instructions/backend/dotnet-api.instructions.md`
- Backend testing: `.github/instructions/backend/testing.instructions.md`
- Frontend rules: `.github/instructions/frontend/react-tailwind.instructions.md`
- Frontend testing: `.github/instructions/frontend/testing.instructions.md`
- GitHub PR rules: `.github/instructions/github-pr.instructions.md`

### Skills (use on demand)
- `dotnet-clean-api` — implement .NET use cases and endpoints.
- `dotnet-architecture-guard` — detect layer violations.
- `dotnet-testing-quality` — improve .NET test coverage.
- `dotnet-best-practices-extract` — extract .NET patterns to best-practices.
- `frontend-react-tailwind` — implement React/Tailwind features.
- `frontend-testing-quality` — improve frontend test coverage.
- `frontend-docs-playground` — generate Storybook stories and component docs.
- `frontend-best-practices-extract` — extract frontend patterns to best-practices.
- `github-pr-workflow` — prepare and structure GitHub PRs.

### Agents (use for specialized mode)
- `DotNet Clean Architect` — implement .NET features end-to-end.
- `DotNet API Reviewer` — review .NET code changes.
- `Frontend React Tailwind Architect` — implement frontend features.
- `Frontend Code Reviewer` — review React/Tailwind changes.
- `Frontend Docs Playground Creator` — generate component docs and stories.
- `GitHub PR Creator` — draft and structure pull requests.

### Best-Practice Extractions
- Backend: `.github/best-practices/backend-dotnet-api.md`
- Frontend: `.github/best-practices/frontend-react-tailwind.md`

### Task Tracker
- All epics and tasks: `.docs/tasks.md` (numbered per track: BE-xx, FE-xx, CC-xx).

---

## Design Rules

### Backend Rules
- Dependencies must always point inward: Api → Application → Domain.
- Domain must not depend on infrastructure or frameworks.
- Avoid business logic in controllers, repositories, or HTTP handlers.
- For each new capability, define an interface in Application and inject via DI.
- Keep renegotiation logic encapsulated behind a dedicated interface; controllers only call and map.
- All generated code must include XML docs on public members and inline comments on complex logic.

### Frontend Rules
- Organize by feature first, then by technical role.
- Keep state local by default and elevate only when required.
- Keep side effects in hooks/services, not in presentational components.
- Prefer typed contracts at API, form, and routing boundaries (Zod schemas).
- Prefer composition over large monolithic components.
- Accessibility is a first-class constraint, not an afterthought.

---

## Testing Rules

### Backend
- Unit tests for Domain and Application; integration tests for Infrastructure and Api.
- All tests in English, naming standard: `Method_Condition_ExpectedResult`.
- Follow AAA (Arrange, Act, Assert) — label sections when used.

### Frontend
- Component/unit tests with React Testing Library + Vitest.
- Naming standard: `ComponentOrHook_Condition_ExpectedResult`.
- Cover loading, empty, error, and success states.
- Mock at network boundary, not internal implementation.

---

## When Copilot Proposes Changes
- Preserve repository style and structure.
- Keep changes small and focused.
- Do not introduce major dependencies without a technical reason.
- If an architectural decision is not obvious, document it in `.context/decision-log.md`.

---

## GitHub Pull Request Workflow
- Keep each PR focused on one objective.
- Use title pattern `type(scope): summary`.
- Include sections: Summary, What Changed, Risks and Mitigations, Test Evidence, Rollback Plan.
- Explicitly call out breaking changes and migration implications.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
