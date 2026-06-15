# EPIC FE-01 — Project Setup

**Track:** Frontend  
**Status:** `[x]` Done

## Description
Bootstrap the React + TypeScript frontend project with the full toolchain configured: Vite (or Next.js), Tailwind CSS, ESLint, Prettier, Vitest, and React Testing Library.
This epic produces a runnable development environment with a clean, consistent folder structure.

## Goal
Deliver a green, runnable development baseline that every feature epic builds on.

## Acceptance Criteria
- [x] Project scaffolded with React + TypeScript (strict mode enabled).
- [x] Tailwind CSS installed and configured with a custom theme extension file.
- [x] ESLint enforces React, TypeScript, and accessibility rules (no-unused-vars, exhaustive-deps, jsx-a11y).
- [x] Prettier is configured and consistent with ESLint.
- [x] Vitest and React Testing Library are installed with a working sample test.
- [x] Path aliases (e.g. `@/features`, `@/components`) are configured and working.
- [x] Folder structure matches the agreed layout: `app/`, `features/`, `components/`, `lib/`, `styles/`.
- [x] `npm run build` produces a clean production bundle with no warnings.

## Tasks
| ID | Task | Status |
|---|---|---|
| FE-01-01 | Scaffold React + TypeScript project | `[x]` |
| FE-01-02 | Configure Tailwind CSS with design tokens | `[x]` |
| FE-01-03 | Add ESLint + Prettier + strict TypeScript config | `[x]` |
| FE-01-04 | Configure Vitest + React Testing Library | `[x]` |
| FE-01-05 | Set up path aliases and folder structure | `[x]` |
