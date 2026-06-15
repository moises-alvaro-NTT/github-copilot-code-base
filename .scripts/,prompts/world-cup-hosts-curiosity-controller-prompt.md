# Prompt: Create a World Cup Host Countries Controller with a Curious Fact

Implement a new backend feature in this repository to expose an endpoint for countries that have hosted the FIFA World Cup, also returning a curious fact about the host country and the winning team.

## Objective
Create a new controller that queries all World Cup host countries and returns, for each host, tournament information and a curious fact.

## Functional Requirements
- Create endpoint `GET /api/world-cup-hosts/curiosities`.
- The endpoint must return a list of all countries that have hosted at least one World Cup.
- It must support an optional country-name filter using query param `name`.
- The `name` filter must be case-insensitive and based on partial matches.
- If `name` is not provided, return the full catalog.
- Return `200 OK` with JSON.
- If there are no matches, return an empty list.

## Suggested Response Model
Each item may include:
- `country`: host country name.
- `editionsHosted`: list of editions hosted by that country (year).
- `winningTeamsInHostedEditions`: champion teams from World Cups hosted by that country.
- `curiousFact`: short text with a curious fact.

Example of `curiousFact`:
- "Uruguay hosted and won in 1930, the first World Cup in history."

## Curious Fact Rules
- Generate a deterministic curious fact (not random).
- Prioritize verifiable facts:
  - If the host country won at home, highlight it.
  - Otherwise, highlight which national team won and in which year.
- Avoid ambiguous or invented text.

## Architecture Constraints
Follow the repository Clean Architecture:
- `Api`: controller and HTTP contract.
- `Application`: use cases, DTOs, contracts, validations.
- `Domain`: pure business rules.
- `Infrastructure`: repository/data source.
- Dependencies must always point inward.

## Implementation Guidance
- Create a contract in Application to query World Cup hosts.
- Implement a use case in Application for filtering and curious-fact composition.
- Define a repository abstraction in Application and its implementation in Infrastructure.
- Create a new controller in Api.
- Register services in DI following existing conventions.
- Keep naming consistent with current modules.

## Validations
- Apply `Trim()` to `name`.
- Treat empty or whitespace-only `name` as no filter.
- Do not throw errors for "no results".

## Required Tests
Add or update tests to cover:
- `GET /api/world-cup-hosts/curiosities` returns data.
- `GET /api/world-cup-hosts/curiosities?name=arg` filters by partial, case-insensitive match.
- `GET /api/world-cup-hosts/curiosities?name=<no-match>` returns an empty list.
- Validate `curiousFact` composition for at least 2 scenarios:
  - host country that won.
  - host country where another national team won.
- Verify existing endpoints remain unaffected.

## Deliverables
- Code changes in the required backend layers.
- Passing unit and integration tests.
- Final summary of changed files, test results, and assumptions.

## Expected Final Output Format
1. What was implemented.
2. Modified files.
3. Test evidence.
4. Assumptions and limits of the historical data used.
