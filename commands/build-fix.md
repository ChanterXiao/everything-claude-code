---
description: Fix build and type errors with minimal, safe changes. Invokes the build-error-resolver agent.
---

# Build Fix Command

@build-error-resolver Incrementally fix build and type errors:

## Instructions

1. **Detect Build System** - Identify project type and run build:
   - TypeScript: `npx tsc --noEmit` or `npm run build`
   - Go: `go build ./...`
   - Python: `mypy .` or `python -m py_compile`
   - Rust: `cargo build`

2. **Parse and Group Errors** - Organize by file and severity

3. **Fix Incrementally** - One error at a time:
   - Start with the first error in the first file
   - Make minimal surgical fix
   - Re-run build to verify
   - Move to next error

4. **Report Progress** - Show what's fixed and what remains

**CRITICAL**: Make minimal changes. Do not refactor unrelated code.
