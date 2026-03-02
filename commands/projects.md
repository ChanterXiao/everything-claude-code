---
name: projects
description: List known projects and their instinct statistics
---

# Projects Command

List project registry entries and per-project instinct counts.

## Execution

Run the instinct CLI:

```bash
python3 ~/.claude/skills/continuous-learning-v2/scripts/instinct-cli.py projects
```

## What It Shows

1. Read `~/.claude/homunculus/projects.json`
2. For each project display:
   - Project name, id, root, remote
   - Personal and inherited instinct counts
   - Observation event count
   - Last seen timestamp
3. Global instinct totals

## Usage

```
/projects
```
