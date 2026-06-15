---
description: Rules for building Frontend features with React, Tailwind, and modern TypeScript practices
applyTo: "src/frontend/**/*.{ts,tsx,js,jsx,css,scss,json},**/*.tsx,**/*.jsx"
---

## Core Stack
- React with TypeScript by default.
- Tailwind CSS for styling and design tokens.
- Recommended libraries when useful: React Router, TanStack Query, React Hook Form, Zod, Zustand.

## Architecture
- Prefer feature-first organization (`features/<feature-name>`).
- Keep shared UI components in a dedicated shared folder.
- Keep side effects in hooks/services, not in presentational components.
- API boundaries must be typed and validated.

## Component Design
- Components should have one clear responsibility.
- Prefer composition over inheritance and giant components.
- Keep prop contracts explicit and strongly typed.
- Reuse utility classes through class-variance or variant helpers when repetition grows.

## Tailwind Guidelines
- Define reusable tokens using CSS variables and Tailwind theme extension.
- Avoid ad-hoc one-off values when a token should exist.
- Use responsive and state variants intentionally.
- Keep utility lists readable; extract helper components when classes become too long.

## Accessibility
- Ensure keyboard navigation for interactive components.
- Use semantic HTML before ARIA.
- Include visible focus styles.
- Provide labels and error feedback for form controls.

## Performance
- Memoize only where profiler evidence exists.
- Split heavy routes/components with lazy loading.
- Avoid unnecessary global state.
- Prevent waterfalls in async data loading.

## Documentation and Best Practices
- Extract recurring patterns to `.github/best-practices/frontend-react-tailwind.md`.
- Keep examples practical and short.

## PR Checklist
- Build succeeds and tests pass.
- No obvious accessibility regressions.
- New UI behavior has test coverage.
- Relevant docs/playground examples are updated.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
