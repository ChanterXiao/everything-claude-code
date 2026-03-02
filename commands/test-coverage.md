---
description: Analyze test coverage, identify gaps, and generate missing tests to reach 80%+ coverage.
---

# Test Coverage Command

Analyze test coverage and generate missing tests.

## Execution

1. **Detect Test Framework**:
   - Jest: `npx jest --coverage`
   - Vitest: `npx vitest run --coverage`
   - pytest: `pytest --cov=src`
   - Go: `go test -coverprofile=coverage.out ./...`
   - Rust: `cargo llvm-cov`

2. **Analyze Coverage Report**:
   - List files below 80% coverage
   - Identify untested functions
   - Find missing branch coverage

3. **Generate Missing Tests** (priority order):
   - Happy path (core functionality)
   - Error handling (invalid inputs, failures)
   - Edge cases (empty, null, boundary values)
   - Branch coverage (if/else, switch cases)

4. **Verify** - Run tests and re-check coverage

5. **Report** - Show before/after comparison

## Focus Areas

- Complex branching functions
- Error handlers and catch blocks
- Utility functions used across codebase
- API endpoint handlers
