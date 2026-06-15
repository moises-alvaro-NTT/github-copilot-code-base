# Master Prompt: Build a Europe Countries API with Agents and Subagents

## Context
You are working in a .NET backend that follows Clean Architecture.
Your task is to design and implement a new API endpoint that returns European countries, with optional filtering by country name.

## Main Objective
Create an endpoint to query countries in Europe:
- Endpoint: GET /api/countries/europe
- Optional query parameter: name
- If name is provided, apply partial and case-insensitive filtering
- If name is empty or whitespace, treat it as no filter
- Return HTTP 200 with a JSON list in all successful cases
- If no matches are found, return an empty list

## Agent-Oriented Execution Model
Use one orchestrator agent and multiple specialized subagents.

### Main Agent: Europe Countries API Orchestrator
Responsibilities:
1. Break down the implementation into architecture-safe steps.
2. Delegate work to subagents.
3. Consolidate outputs into a final implementation.
4. Validate acceptance criteria before finishing.
5. Produce final technical summary with test evidence.

### Subagent 1: Architecture Guard
Responsibilities:
1. Ensure no Clean Architecture violations.
2. Verify dependency direction remains inward.
3. Prevent domain-layer coupling with infrastructure.

Deliverable:
- Architecture compliance note with identified risks and fixes.

### Subagent 2: Application Layer Builder
Responsibilities:
1. Create use case contract(s) for querying European countries.
2. Implement filtering logic for name.
3. Define DTOs for response payload.
4. Normalize and validate input at application boundary.

Deliverable:
- Summary of contracts, use case logic, and DTOs.

### Subagent 3: Infrastructure Layer Builder
Responsibilities:
1. Implement repository/data provider for countries.
2. Support efficient filtering by partial country name.
3. Keep implementation swappable for future data-source changes.
4. Wire implementation via dependency injection.

Deliverable:
- Summary of repository implementation and DI wiring.

### Subagent 4: API Layer Builder
Responsibilities:
1. Create Countries controller endpoint: GET /api/countries/europe
2. Bind query parameter name.
3. Return consistent HTTP 200 responses.
4. Keep controller thin and delegate business logic to application.

Deliverable:
- Endpoint summary and sample response contract.

### Subagent 5: Testing Specialist
Responsibilities:
1. Add unit tests for application filtering behavior.
2. Add integration tests for the endpoint.
3. Confirm no regressions on existing endpoints.
4. Validate edge cases and empty-result behavior.

Minimum test scenarios:
1. No filter returns all European countries.
2. Partial filter works, example: name=spa.
3. Filtering is case-insensitive.
4. No-match filter returns empty list.
5. Whitespace-only filter behaves as no filter.

Deliverable:
- Test report with executed scenarios and outcomes.

### Subagent 6: Quality Reviewer
Responsibilities:
1. Review implementation for maintainability and readability.
2. Ensure logs/errors follow project conventions.
3. Confirm final output is PR-ready.

Deliverable:
- Quality checklist and improvement notes.

## Data Contract Example
Response item fields:
- countryName: string
- isoCode: string
- capital: string
- region: string
- population: number (optional)

## Non-Functional Requirements
1. Keep changes scoped to this feature only.
2. Keep implementation deterministic and testable.
3. Avoid breaking existing routes and contracts.
4. Follow repository naming and folder conventions.

## Required Delivery Format
When all agents finish, return:
1. Implementation summary by layer.
2. Full list of modified files.
3. Test evidence.
4. Risks and mitigations.
5. Assumptions and data-source limitations.
6. Final acceptance checklist.

## Acceptance Criteria
1. GET /api/countries/europe exists and works.
2. name filtering is partial and case-insensitive.
3. Empty/whitespace name is treated as no filter.
4. No-match case returns HTTP 200 with empty list.
5. Unit and integration tests pass.
6. No architecture violations are introduced.
7. Existing endpoints remain unaffected.
