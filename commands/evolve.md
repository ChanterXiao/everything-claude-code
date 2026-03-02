---
name: evolve
description: Analyze instincts and suggest or generate evolved structures
command: true
---

# Evolve Command

Analyze instincts and cluster related ones into higher-level structures.

## Execution

Run the instinct CLI:

```bash
python3 ~/.claude/skills/continuous-learning-v2/scripts/instinct-cli.py evolve [--generate]
```

Or with plugin root:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/skills/continuous-learning-v2/scripts/instinct-cli.py" evolve [--generate]
```

## What It Does

1. Detect current project context
2. Read project + global instincts
3. Group instincts by trigger/domain patterns
4. Identify evolution candidates:
   - **Commands**: User-invoked actions
   - **Skills**: Auto-triggered behaviors
   - **Agents**: Complex multi-step processes
5. Show promotion candidates (project → global)
6. If `--generate`, write files to `evolved/{skills,commands,agents}/`

## Usage

```
/evolve              # Analyze and suggest evolutions
/evolve --generate   # Also generate files
```
