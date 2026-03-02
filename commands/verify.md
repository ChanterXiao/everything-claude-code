---
description: Run comprehensive verification on current codebase state.
---

# Verify Command

Run comprehensive verification on current codebase state.

## Execution

Execute verification in order:

1. **Build Check** - Run build command for project. If fails, report and STOP.
2. **Type Check** - Run TypeScript/type checker
3. **Lint Check** - Run linter
4. **Test Suite** - Run all tests, report pass/fail and coverage
5. **Console.log Audit** - Search for console.log in source
6. **Git Status** - Show uncommitted changes

## Output

```
VERIFICATION: [PASS/FAIL]

Build:    [OK/FAIL]
Types:    [OK/X errors]
Lint:     [OK/X issues]
Tests:    [X/Y passed, Z% coverage]
Secrets:  [OK/X found]
Logs:     [OK/X console.logs]

Ready for PR: [YES/NO]
```

## Arguments

- `quick` - Only build + types
- `full` - All checks (default)
- `pre-commit` - Checks relevant for commits
- `pre-pr` - Full checks plus security scan
