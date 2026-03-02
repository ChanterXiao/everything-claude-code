---
name: instinct-export
description: Export instincts from project/global scope to a file
---

# Instinct Export Command

Export instincts to a shareable format.

## Execution

Run the instinct CLI:

```bash
python3 ~/.claude/skills/continuous-learning-v2/scripts/instinct-cli.py export [--domain <name>] [--min-confidence <n>] [--output <file>] [--scope <project|global|all>]
```

## What It Does

1. Detect current project context
2. Load instincts by scope:
   - `project`: current project only
   - `global`: global only
   - `all`: project + global merged (default)
3. Apply filters (domain, min-confidence)
4. Write YAML export to file

## Usage

```
/instinct-export                           # Export all instincts
/instinct-export --domain testing          # Export testing domain only
/instinct-export --min-confidence 0.7      # High-confidence only
/instinct-export --output team-instincts.yaml
/instinct-export --scope project            # Project only
```

## Flags

- `--domain <name>`: Export only specified domain
- `--min-confidence <n>`: Minimum confidence threshold
- `--output <file>`: Output file path
- `--scope <project|global|all>`: Export scope (default: `all`)
