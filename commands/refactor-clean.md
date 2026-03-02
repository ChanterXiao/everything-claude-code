---
description: Safely identify and remove dead code with test verification at every step. Invokes the refactor-cleaner agent.
---

# Refactor Clean Command

@refactor-cleaner Safely identify and remove dead code:

## Instructions

1. **Detect Dead Code** - Run analysis tools based on project type:
   - JavaScript/TypeScript: `npx knip`, `npx depcheck`, `npx ts-prune`
   - Python: `vulture src/`
   - Go: `deadcode ./...`
   - Rust: `cargo +nightly udeps`

2. **Categorize Findings**:
   - **SAFE**: Unused utilities, test helpers (delete with confidence)
   - **CAUTION**: Components, API routes (verify no dynamic imports)
   - **DANGER**: Config files, entry points (investigate first)

3. **Safe Deletion Loop**:
   - Run full test suite (establish baseline)
   - Delete one dead code item
   - Re-run test suite
   - If tests fail → revert and skip
   - If tests pass → proceed

4. **Consolidate Duplicates** - After cleanup:
   - Merge near-duplicate functions
   - Consolidate redundant type definitions
   - Remove wrapper functions that add no value

5. **Report Results** - Show deleted items and lines saved

**CRITICAL**: Never delete without running tests first. One deletion at a time.
