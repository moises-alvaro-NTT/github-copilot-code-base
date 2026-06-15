# Frontend Best Practices Extraction

## Scope
React + Tailwind + TypeScript implementation standards for feature delivery.

## Recommended Libraries
- Routing: React Router.
- Data fetching/cache: TanStack Query.
- Forms: React Hook Form + Zod resolvers.
- Validation: Zod.
- Client state (when needed): Zustand.
- Utility patterns: clsx + tailwind-merge.

## Patterns to Prefer
- Feature-first modules with co-located hooks, components, and tests.
- Typed API contracts and schema validation at boundaries.
- Explicit loading, empty, and error rendering states.
- Reusable Tailwind variants for shared controls.

## Extracted Patterns (Implemented)

### 1) Query-Driven Feature Panel
- Keep async state handling inside the feature panel component.
- Render predictable states in this order: loading -> error -> empty -> success.

```tsx
const { data, isPending, isError } = useContractsQuery()
if (isPending) return <Alert severity='info'>Loading contracts...</Alert>
if (isError) return <Alert severity='error'>Contracts could not be loaded.</Alert>
if (!data?.length) return <Alert severity='warning'>No contracts available.</Alert>
return data.map((contract) => <Card key={contract.id}>{contract.number}</Card>)
```

### 2) Typed Boundary with Zod in API Client
- Parse unknown responses immediately at the API boundary.
- Export inferred types from schema to avoid duplicate interfaces.

```tsx
const parsed = contractsResponseSchema.parse(mockApiResponse)
return Promise.resolve(parsed)
```

### 3) Form Contract with React Hook Form + Zod
- Keep schema near form component and infer `FormData` directly.
- Use `valueAsNumber` for numeric inputs to avoid `unknown` coercion drift.

```tsx
const schema = z.object({ requestedAmount: z.number().positive() })
type FormData = z.infer<typeof schema>
register('requestedAmount', { valueAsNumber: true })
```

### 4) UI Variant + Utility Composition
- Use `class-variance-authority` for variants and `cn()` for conditional merge.
- Keep focus-visible styles in primitives to enforce accessibility defaults.

## Patterns to Avoid
- Business rules embedded directly in UI components.
- Global state for local-only concerns.
- Copy-pasted utility class blocks across many files.
- Snapshot-only tests for critical flows.

## Testing Baseline
- Component tests for interaction and accessibility.
- Integration tests for critical async flows.
- Docs/playground examples for reusable components.

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
