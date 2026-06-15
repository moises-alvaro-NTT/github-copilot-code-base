# Prompt: Add Countries Endpoint With Name Filter

Implement a new backend feature in this repository to expose a countries endpoint with filtering by name.

## Goal
Add an HTTP endpoint that returns countries and supports filtering by country name.

## Requirements
- Create `GET /api/countries`.
- Support query parameter `name` for filtering by country name.
- Filtering must be case-insensitive.
- Filtering should support partial matches (contains), not exact match only.
- If `name` is not provided, return all countries.
- Return `200 OK` with a JSON list.
- Return an empty list when no countries match.
- Do not break existing endpoints.

## Architecture Constraints
Follow the existing Clean Architecture rules in this repo:
- `Api` layer: controller/endpoint contract only.
- `Application` layer: use case, DTOs, contracts, validation.
- `Domain` layer: business rules only.
- `Infrastructure` layer: repository/data access implementation.
- Dependencies must point inward.

## Implementation Guidance
- Add a contract in Application for reading countries.
- Add a use case/service in Application that handles the `name` filter logic.
- Add repository abstraction in Application and implementation in Infrastructure.
- Add a new controller in Api for countries endpoint.
- Reuse existing project conventions for DI registration.
- Keep naming consistent with existing backend modules.

## Validation Rules
- Trim whitespace for `name`.
- Treat empty/whitespace `name` as no filter.
- Avoid throwing errors for normal "no results" cases.

## Tests
Add or update tests to cover:
- `GET /api/countries` returns all countries.
- `GET /api/countries?name=bra` returns matching countries (partial + case-insensitive).
- `GET /api/countries?name=<no-match>` returns empty list.
- Existing renegotiations endpoints remain unaffected.

Use current backend testing patterns:
- Unit tests for Application behavior.
- Integration tests for API endpoint behavior.

## Deliverables
- Code changes in backend layers.
- Tests passing for new and existing relevant scenarios.
- Short summary of changed files and behavior.

## Output Format
When done, provide:
1. What was implemented.
2. Files changed.
3. Test results.
4. Any assumptions made.
