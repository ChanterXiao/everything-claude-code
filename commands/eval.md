---
description: Manage eval-driven development workflow.
---

# Eval Command

Manage eval-driven development workflow.

## Usage

`/eval [define|check|report|list] [feature-name]`

## Execution

If `define <feature-name>`:
1. Create `.claude/evals/feature-name.md` with template
2. Prompt user to fill in specific criteria

If `check <feature-name>`:
1. Read eval definition
2. Run each capability eval
3. Run regression tests
4. Report PASS/FAIL status

If `report <feature-name>`:
1. Generate comprehensive eval report
2. Show metrics: pass@1, pass@3, pass^3
3. Provide SHIP/NEEDS WORK/BLOCKED recommendation

If `list`:
1. Show all eval definitions with status

## Arguments

- `define <name>` - Create new eval definition
- `check <name>` - Run and check evals
- `report <name>` - Generate full report
- `list` - Show all evals
- `clean` - Remove old eval logs (keeps last 10 runs)
