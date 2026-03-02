---
description: Comprehensive Go code review for idiomatic patterns, concurrency safety, error handling, and security. Invokes the go-reviewer agent.
---

# Go Review Command

@go-reviewer Perform comprehensive Go code review:

## Instructions

1. **Identify Go Changes** - Find modified `.go` files via `git diff`
2. **Run Static Analysis** - Execute `go vet`, `staticcheck`, `golangci-lint`
3. **Security Scan** - Check for:
   - SQL injection
   - Command injection
   - Race conditions
   - Unsafe memory operations
4. **Concurrency Review** - Analyze:
   - Goroutine safety
   - Channel usage patterns
   - Mutex and sync usage
5. **Idiomatic Check** - Verify:
   - Error handling patterns
   - Interface design
   - Package structure
   - Naming conventions
6. **Generate Report** - Categorize issues by severity

Focus on Go-specific best practices and idioms.
