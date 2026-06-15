---
name: frontend-best-practices-extract
description: Extract recurring frontend implementation patterns into concise best-practice guides with practical examples.
---

# Frontend Best Practices Extract Skill

## Goal
Capture reusable frontend patterns and convert them into actionable project guidance.

## When to Use
- After delivering a feature with repeated UI/state patterns.
- During codebase standardization efforts.
- Before scaling a design system or component library.

## Extraction Workflow
1. Identify stable patterns repeated in at least two features.
2. Distill do/don't rules and decision criteria.
3. Add minimal code examples and anti-pattern examples.
4. Store the result in `.github/best-practices/`.
5. Reference the extract in PR notes when relevant.

## Output Requirements
- One concise markdown section per pattern.
- Rationale and trade-offs.
- Copy-ready examples with TypeScript + Tailwind.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
