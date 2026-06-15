---
name: github-pr-workflow
description: Prepare and create high-quality GitHub pull requests with clear scope, evidence, and rollback notes.
---

# GitHub PR Workflow Skill

## When to Use
- Create a new pull request.
- Prepare changes for review.
- Standardize PR quality and reviewer context.

## Recommended Flow
1. Verify branch and scope are correct.
2. Run build and relevant tests.
3. Review diff for secrets and accidental changes.
4. Write a PR title and body using the required sections.
5. Request reviewers and label the PR.

## PR Title Pattern
- `type(scope): short summary`
- Examples: `feat(api): add customer search endpoint`, `fix(auth): prevent token reuse`

## PR Checklist
- Scope is small and reviewable.
- Tests are included for behavior changes.
- Risks are documented.
- Rollback path is clear.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
