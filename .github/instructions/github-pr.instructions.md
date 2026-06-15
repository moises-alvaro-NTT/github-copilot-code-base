---
description: GitHub Pull Request creation and quality rules
applyTo: "**/*.md,**/*.yml,**/*.yaml,**/*.json"
---

## Goal
Ensure every change is ready for review and can be merged safely.

## PR Creation Rules
- Keep PRs focused on a single objective.
- Use clear branch names, for example `feature/<scope>` or `fix/<scope>`.
- Include a concise title and a body with context, changes, and risks.
- Link related issues when available.

## Required PR Description Sections
- Summary
- What Changed
- Risks and Mitigations
- Test Evidence
- Rollback Plan

## Quality Gate Before Opening PR
- Local build passes.
- Relevant tests pass.
- No architecture rule violations.
- No secrets or sensitive data in diff.

## Reviewer Experience
- Prefer small commits with meaningful messages.
- Highlight non-obvious design decisions.
- Mention breaking changes explicitly.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
