---
description: Testing strategy for .NET API
applyTo: "tests/**/*.cs,**/*Tests.cs,**/*.feature"
---

## Goal
Ensure functional quality and prevent regressions with fast, readable, and deterministic tests.

## Test Types
- Unit tests: Domain and Application, no real I/O.
- Integration tests: Infrastructure and Api with controlled dependencies.
- Contract tests: validate HTTP contracts and serialization.

## Rules
- One test validates one behavior.
- Use names like `Method_Condition_ExpectedResult`.
- Avoid sleeps and non-deterministic timing.
- Do not rely on shared state across tests.
- All test names, comments, and test data labels must be in English.
- Use a single naming standard across all tests: `Method_Condition_ExpectedResult`.
- Keep AAA section comments in English (`Arrange`, `Act`, `Assert`) when section comments are used.

## Suggested Minimum Coverage
- Domain/Application: high coverage of critical branches.
- Infra/Api: focus on main paths, error paths, and security.

## Test Quality
- Clear AAA structure.
- Specific and useful assertions.
- Readable test data (builders/factories when they add value).
- Include comments in English for scenario intent and non-obvious setup.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
