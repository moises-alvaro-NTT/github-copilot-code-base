---
name: dotnet-architecture-guard
description: Protect Clean Architecture boundaries and prevent accidental coupling in .NET APIs.
---

# Dotnet Architecture Guard Skill

## Goal
Detect and fix layer violations and improper dependencies.

## When to Use
- Review large PRs.
- Refactors that move responsibilities.
- Introduction of new external integrations.

## Key Rules
- Domain does not reference Infrastructure or Api.
- Application does not depend on the web framework.
- Api does not know persistence internals.

## Recommended Actions
1. Map current dependencies.
2. Identify invalid crossings.
3. Propose interface/adapter to decouple.
4. Move logic to the correct layer.
5. Validate with regression tests.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
