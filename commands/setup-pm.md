---
description: Configure your preferred package manager (npm/pnpm/yarn/bun)
disable-model-invocation: true
---

# Package Manager Setup

Configure your preferred package manager.

## Execution

```bash
# Detect current package manager
node scripts/setup-package-manager.js --detect

# Set global preference
node scripts/setup-package-manager.js --global <npm|pnpm|yarn|bun>

# Set project preference
node scripts/setup-package-manager.js --project <npm|pnpm|yarn|bun>

# List available package managers
node scripts/setup-package-manager.js --list
```

## Detection Priority

1. Environment variable: `CLAUDE_PACKAGE_MANAGER`
2. Project config: `.claude/package-manager.json`
3. package.json: `packageManager` field
4. Lock file detection
5. Global config: `~/.claude/package-manager.json`
6. Fallback: First available (pnpm > bun > yarn > npm)

## Configuration Files

Global: `~/.claude/package-manager.json`
Project: `.claude/package-manager.json`
