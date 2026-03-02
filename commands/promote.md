---
name: promote
description: Promote project-scoped instincts to global scope
---

# Promote Command

Promote instincts from project scope to global scope.

## Execution

Run the instinct CLI:

```bash
python3 ~/.claude/skills/continuous-learning-v2/scripts/instinct-cli.py promote [instinct-id] [--force] [--dry-run]
```

## What It Does

1. Detect current project
2. If `instinct-id` provided, promote only that instinct
3. Otherwise, find cross-project candidates that:
   - Appear in at least 2 projects
   - Meet confidence threshold
4. Write promoted instincts to `~/.claude/homunculus/instincts/personal/`

## Usage

```
/promote                  # Auto-detect promotion candidates
/promote --dry-run        # Preview candidates
/promote --force          # Promote all qualified without prompt
/promote grep-before-edit # Promote specific instinct
```

## Flags

- `--dry-run`: Preview without promoting
- `--force`: Skip confirmation prompt
