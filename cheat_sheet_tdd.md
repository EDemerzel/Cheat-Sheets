# Test‑Driven Development (TDD) Cheat Sheet

## Core Principles

1. **Test First** – write a failing test before production code.
2. **Incremental Steps** – smallest code to pass, then refactor.
3. **Red → Green → Refactor** loop.

## Benefits

- Enhanced code quality & design
- Fewer regressions
- Living documentation
- Faster feedback loops

## Types of Tests

| Layer           | Focus                                        |
|-----------------|----------------------------------------------|
| **Unit**        | Smallest testable unit (functions / methods) |
| **Integration** | Interaction between components               |
| **E2E**         | Full application flow, user perspective      |

### The Test Pyramid

```text
    ▲   E2E  (few, slow)
  △ △   Integration
△ △ △   Unit (many, fast)
```

## Test Doubles

| Kind   | Shortcut | Use                                        |
|--------|----------|--------------------------------------------|
| Dummy  | —        | Placeholder, no logic                      |
| Fake   | —        | Lightweight working impl (e.g., in‑mem DB) |
| Stub   | —        | Pre‑canned responses                       |
| Mock   | —        | Expects calls / verifies behaviour         |
| Spy    | —        | Wraps real object, records calls           |

## Best Practices

- **Keep tests small & focused** – verify one behaviour.
- **Descriptive names** – `CalculateSum_PositiveNumbers_ShouldReturnTotal`.
- **Isolate dependencies** – use doubles.
- **Aim for high coverage**, prioritise critical paths.
- **Don’t test implementation details**; test observable behaviour.
- **Refactor ruthlessly** once tests pass.

## Mockist vs Classicist TDD

| School                   | Characteristics                                  |
|--------------------------|--------------------------------------------------|
| **Mockist (London)**     | Heavy mocks, fast feedback, isolation            |
| **Classicist (Detroit)** | Real objects preferred; mocks only at boundaries |
