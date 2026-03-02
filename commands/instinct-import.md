---
name: instinct-import
description: Import instincts from file or URL into project/global scope
---

# Instinct Import Command

Import instincts from local file paths or HTTP(S) URLs.

## Execution

Run the instinct CLI:

```bash
python3 ~/.claude/skills/continuous-learning-v2/scripts/instinct-cli.py import <file-or-url> [--dry-run] [--force] [--min-confidence 0.7] [--scope project|global]
```

## What It Does

1. Fetch the instinct file (local path or URL)
2. Parse and validate the format
3. Check for duplicates with existing instincts
4. Merge or add new instincts
5. Save to inherited instincts directory:
   - Project: `~/.claude/homunculus/projects/<id>/instincts/inherited/`
   - Global: `~/.claude/homunculus/instincts/inherited/`

## Usage

```
/instinct-import team-instincts.yaml
/instinct-import https://github.com/org/repo/instincts.yaml
/instinct-import team-instincts.yaml --dry-run
/instinct-import team-instincts.yaml --scope global --force
```

## Flags

- `--dry-run`: Preview without importing
- `--force`: Skip confirmation prompt
- `--min-confidence <n>`: Only import instincts above threshold
- `--scope <project|global>`: Target scope (default: `project`)
