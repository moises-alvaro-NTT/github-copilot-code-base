---
name: frontend-docs-playground
description: Create and maintain frontend documentation and interactive playground scenarios for reusable components.
---

# Frontend Docs Playground Skill

## When to Use
- Document reusable components and design tokens.
- Create interactive examples (Storybook/Ladle style).
- Keep implementation and docs synchronized.

## Recommended Flow
1. Select components with high reuse or complexity.
2. Document props, variants, and behavioral states.
3. Add playground stories for normal, loading, empty, and error states.
4. Add accessibility notes and keyboard expectations.
5. Link docs updates in the related PR.

## Quality Bar
- Examples are runnable and realistic.
- Docs avoid stale, speculative APIs.
- Accessibility guidance is explicit.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
