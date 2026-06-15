# Architecture Context

## Style
.NET API with Clean Architecture.

## Layers
- Domain: pure business rules.
- Application: use cases and contracts.
- Infrastructure: adapters and persistence.
- Api: HTTP transport and composition.

## Principles
- Inward dependency flow.
- Small use cases.
- Consistent errors.
- Observability and security from day one.

## Suggested Structure
- `src/Domain`
- `src/Application`
- `src/Infrastructure`
- `src/Api`
- `tests/UnitTests`
- `tests/IntegrationTests`
