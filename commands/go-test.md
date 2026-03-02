---
description: Enforce TDD workflow for Go. Write table-driven tests first, then implement. Verify 80%+ coverage with go test -cover.
---

# Go TDD Command

@go-reviewer Guide Go TDD workflow:

## Instructions

1. **Define Types/Interfaces** - Scaffold function signatures first
2. **Write Table-Driven Tests** - Create comprehensive test cases (RED phase):
   - Use `[]struct{name string; input; want}` pattern
   - Cover normal cases, edge cases, error cases
   - Run `go test` to verify tests fail for right reason

3. **Implement Code** - Write minimal code to pass (GREEN phase)
4. **Refactor** - Improve while keeping tests green
5. **Check Coverage** - Run `go test -cover` and ensure 80%+

**CRITICAL**: Never write implementation before tests. Follow idiomatic Go patterns.
