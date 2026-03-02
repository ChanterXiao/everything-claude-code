---
description: Create or verify a checkpoint in your workflow.
---

# Checkpoint Command

Create or verify a checkpoint to track progress.

## Usage

`/checkpoint [create|verify|list] [name]`

## Execution

If `create <name>`:
1. Run `/verify quick` to ensure current state is clean
2. Create a git stash or commit with checkpoint name
3. Log checkpoint to `.claude/checkpoints.log`
4. Report checkpoint created

If `verify <name>`:
1. Read checkpoint from log
2. Compare current state to checkpoint:
   - Files added/modified since checkpoint
   - Test pass rate now vs then
   - Coverage now vs then
3. Report comparison results

If `list`:
1. Show all checkpoints with name, timestamp, git SHA, status

## Arguments

- `create <name>` - Create named checkpoint
- `verify <name>` - Verify against named checkpoint
- `list` - Show all checkpoints
- `clear` - Remove old checkpoints (keeps last 5)
