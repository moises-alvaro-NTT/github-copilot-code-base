# .github Structure

This repository organizes Copilot customization and CI by domain track.

## Domain Split
- Backend track: .NET API, Clean Architecture, tactical DDD.
- Frontend track: React + Tailwind, typed boundaries, UI testing.

## Key Folders
- `agents/backend`: backend-focused custom agents.
- `agents/frontend`: frontend-focused custom agents.
- `instructions/backend`: scoped backend coding instructions.
- `instructions/frontend`: scoped frontend coding instructions.
- `skills/backend`: backend skills.
- `skills/frontend`: frontend skills.
- `best-practices`: extracted reusable practices.
- `workflows`: GitHub Actions pipelines.

## Workflows
- `backend-ci.yml`: restore, build, and test .NET changes.
- `frontend-ci.yml`: install, lint, test, and build React frontend changes.

## Notes
- Existing root-level instructions/skills/agents can remain for backward compatibility.
- Prefer adding new guidance under the domain-specific folders.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
