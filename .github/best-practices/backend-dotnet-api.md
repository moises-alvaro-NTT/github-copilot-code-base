# Backend Best Practices — .NET Clean API

## Scope
.NET API implementation standards for feature delivery using Clean Architecture, CQRS-lite, and SOLID principles.

---

## Layer and Dependency Rules

### Do
- Domain → pure rules, no framework references.
- Application → orchestrate use cases, define interfaces.
- Infrastructure → implement interfaces from Application.
- Api → thin controllers, DI wiring, HTTP mapping only.

### Don't
- Cross layers by importing Infrastructure into Domain.
- Put business logic in controllers or middleware.
- Instantiate services with `new` inside controllers.

---

## Interface and Injection Pattern

Every new business capability must follow this structure:

```csharp
// Application/Contracts/IMyFeatureService.cs
/// <summary>Contract for <feature> operations.</summary>
public interface IMyFeatureService
{
    /// <summary>Executes the main feature action.</summary>
    Task<Result<MyResponseDto>> ExecuteAsync(MyRequestDto request, CancellationToken ct);
}

// Infrastructure/Services/MyFeatureService.cs
/// <summary>Concrete implementation of <see cref="IMyFeatureService"/>.</summary>
public sealed class MyFeatureService : IMyFeatureService { ... }

// Api/Program.cs or DI extension
services.AddScoped<IMyFeatureService, MyFeatureService>();
```

---

## Renegotiation Encapsulation Pattern

```csharp
// Application/Contracts/IRenegotiationService.cs
public interface IRenegotiationService
{
    Task<Result<RenegotiationResultDto>> RenegotiateAsync(
        RenegotiationRequestDto request, CancellationToken ct);
}

// Api/Controllers/RenegotiationController.cs
[ApiController]
[Route("api/renegotiations")]
public sealed class RenegotiationController : ControllerBase
{
    private readonly IRenegotiationService _service;

    /// <summary>Initializes the controller with its required service.</summary>
    public RenegotiationController(IRenegotiationService service)
        => _service = service;

    /// <summary>Starts a contract renegotiation process.</summary>
    [HttpPost]
    public async Task<IActionResult> PostAsync(
        RenegotiationRequestDto request, CancellationToken ct)
    {
        // Delegate entirely to the service; no business rules here.
        var result = await _service.RenegotiateAsync(request, ct);
        return result.IsSuccess ? Ok(result.Value) : BadRequest(result.Error);
    }
}
```

---

## Commenting Rules

- Every public type must have an XML `<summary>`.
- Every public method must describe purpose, inputs, and side effects.
- Complex conditionals and domain decisions must have inline comments.
- Keep comments updated when code changes.

---

## Error Handling

```csharp
// Prefer typed Result over throwing everywhere
public sealed record Result<T>(T? Value, string? Error, bool IsSuccess);
// Never expose stack traces to clients; return ProblemDetails.
```

---

## EF Core Query Guidelines

```csharp
// Read-only queries: always AsNoTracking
var items = await _db.Orders
    .AsNoTracking()
    .Where(o => o.Status == OrderStatus.Active)
    .ToListAsync(ct); // Materialize as late as possible

// Never ToList() in the middle of a query chain
```

---

## Anti-Patterns Checklist

| Anti-Pattern | Preferred Alternative |
|---|---|
| Logic in controller | Delegate to Application interface |
| `new MyService()` in controller | Constructor injection |
| Business rules in repository | Move to Domain/Application |
| Raw SQL in controller | Use repository or EF Core |
| Throwing generic exceptions | Typed Result or domain exception |

## Repository Path Scope
- This guidance must account for generated or maintained content under `src/backend`, `src/frontend`, and `src/.docs`.
- If a legacy path is referenced, map it to the corresponding location under `src/`.
