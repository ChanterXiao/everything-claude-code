---
description: Comprehensive security and quality review of uncommitted changes. Invokes the code-reviewer agent.
---

# Code Review Command

@code-review Review the uncommitted changes for security and quality issues:

## Instructions

1. **Get Changed Files** - Run `git diff --name-only HEAD` to find modified files
2. **Security Review** - Check for:
   - Hardcoded credentials, API keys, tokens
   - SQL injection vulnerabilities
   - XSS vulnerabilities
   - Missing input validation
   - Insecure dependencies
   - Path traversal risks
3. **Quality Review** - Check for:
   - Functions > 50 lines
   - Files > 800 lines
   - Nesting depth > 4 levels
   - Duplicate code
   - Missing error handling
   - Poor naming
4. **Generate Report** - Categorize issues by severity (CRITICAL/HIGH/MEDIUM/LOW)
5. **Suggest Fixes** - Provide specific recommendations

Focus on uncommitted changes only. Be thorough but constructive.
