---
description: Comprehensive Python code review for PEP 8 compliance, type hints, security, and Pythonic idioms. Invokes the python-reviewer agent.
---

# Python Review Command

@python-reviewer Perform comprehensive Python code review:

## Instructions

1. **Identify Python Changes** - Find modified `.py` files via `git diff`
2. **Run Static Analysis** - Execute:
   - `ruff check`
   - `mypy`
   - `pylint` (if configured)
   - `black --check`
3. **Security Scan** - Check for:
   - SQL injection
   - Command injection
   - Unsafe deserialization
   - Hardcoded secrets
4. **Type Safety Review** - Analyze type hints and mypy errors
5. **Pythonic Check** - Verify PEP 8 compliance and idioms
6. **Generate Report** - Categorize issues by severity

Focus on Python-specific best practices.
