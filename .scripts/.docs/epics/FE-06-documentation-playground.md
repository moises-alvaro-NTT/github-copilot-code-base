# EPIC FE-06 — Documentation and Playground

**Track:** Frontend  
**Status:** `[x]` Done

## Description
Create an interactive component playground (Storybook or Ladle) and document design tokens, component APIs, and Tailwind conventions.
Documentation must stay in sync with implementation and include accessibility guidance per component.

## Goal
Deliver a living documentation playground that developers can use as the single source of truth for UI component usage.

## Acceptance Criteria
- [x] Storybook or Ladle is installed and runs with `npm run storybook`.
- [x] Stories exist for every foundational component covering all variants and states (default, loading, empty, error, disabled).
- [x] Design token documentation is available (color palette, spacing scale, typography scale).
- [x] Tailwind utility conventions and the `cn()` usage pattern are documented.
- [x] Each documented component includes at least one accessibility note (keyboard interaction, ARIA roles, focus behavior).
- [x] Recurring patterns have been extracted to `.github/best-practices/frontend-react-tailwind.md`.
- [x] Playground examples are realistic and production-like — no lorem ipsum-only examples.

## Tasks
| ID | Task | Status |
|---|---|---|
| FE-06-01 | Set up Storybook or Ladle | `[x]` |
| FE-06-02 | Add stories for foundational components (all states) | `[x]` |
| FE-06-03 | Document design tokens and Tailwind conventions | `[x]` |
| FE-06-04 | Add accessibility notes per documented component | `[x]` |
| FE-06-05 | Extract reusable patterns to `.github/best-practices/frontend-react-tailwind.md` | `[x]` |
