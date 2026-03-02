---
description: Fix Go build errors, go vet warnings, and linter issues incrementally. Invokes the go-build-resolver agent for minimal, surgical fixes.
---

# Go Build Command

@go-build-resolver Incrementally fix Go build errors:

## Instructions

1. **Run Diagnostics** - Execute:
   - `go build ./...`
   - `go vet ./...`
   - `staticcheck ./...` (if available)

2. **Parse Errors** - Group by file and sort by severity

3. **Fix Incrementally** - One error at a time:
   - Start with first error
   - Make minimal surgical fix
   - Re-run build to verify
   - Move to next error

4. **Report Summary** - Show what was fixed and what remains

**CRITICAL**: Make minimal changes. Do not refactor unrelated code.
