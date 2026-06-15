---
name: dotnet-best-practices-extract
description: Extract recurring .NET API implementation patterns into concise best-practice guides with practical examples.
---

# Dotnet Best Practices Extract Skill

## Goal
Capture reusable backend patterns and convert them into actionable project guidance.

## When to Use
- After delivering a feature with a recurring interface/injection pattern.
- During codebase standardization or architecture reviews.
- Before scaling a shared module or domain service.

## Extraction Workflow
1. Identify stable patterns repeated in at least two use cases.
2. Distill do/don't rules and decision criteria.
3. Add minimal code examples and anti-pattern examples with XML docs.
4. Store the result in `.github/best-practices/backend-dotnet-api.md`.
5. Reference the extract in PR notes when relevant.

## Output Requirements
- One concise markdown section per pattern.
- Rationale and trade-offs.
- Copy-ready examples in C# with XML documentation comments.
- An anti-pattern checklist row for the new pattern.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
