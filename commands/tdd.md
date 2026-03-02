---
description: Enforce test-driven development workflow. Scaffold interfaces, generate tests FIRST, then implement minimal code to pass. Ensure 80%+ coverage.
---

# TDD Command

@tdd-guide Guide the user through Test-Driven Development workflow:

## Instructions

1. **Scaffold Interfaces** - Define types/interfaces first based on requirements
2. **Generate Tests First** - Write failing tests (RED phase)
3. **Implement Minimal Code** - Write just enough to pass tests (GREEN phase)
4. **Refactor** - Improve code while keeping tests green (REFACTOR phase)
5. **Verify Coverage** - Ensure 80%+ test coverage

Follow strict TDD cycle:
- Start with user's feature/bug request
- Define the interface/signature
- Write comprehensive tests
- Run tests to confirm they fail
- Implement minimal code to pass
- Refactor while green
- Check coverage

**CRITICAL**: Never write implementation code before tests exist.
