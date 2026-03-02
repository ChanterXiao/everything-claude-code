---
description: Manage Claude Code session history - list, load, alias, and edit sessions.
---

# Sessions Command

Manage session history stored in `~/.claude/sessions/`.

## Usage

`/sessions [list|load|alias|info|aliases|help] [options]`

## Execution

**List sessions**:
```bash
node -e "const sm=require(process.env.CLAUDE_PLUGIN_ROOT+'/scripts/lib/session-manager'); console.table(sm.getAllSessions({limit:20}).sessions)"
```

**Load session**: Display session content by ID or alias

**Create alias**: Map memorable name to session ID
```bash
node -e "const aa=require(process.env.CLAUDE_PLUGIN_ROOT+'/scripts/lib/session-aliases'); aa.setAlias('$1','$2')"
```

**Remove alias**: Delete existing alias

**Session info**: Show detailed statistics

**List aliases**: Display all alias mappings

## Arguments

- `list [--limit <n>] [--date <YYYY-MM-DD>] [--search <pattern>]` - List sessions
- `load <id|alias>` - Load session content
- `alias <id> <name>` - Create alias
- `alias --remove <name>` / `unalias <name>` - Remove alias
- `info <id|alias>` - Show session details
- `aliases` - List all aliases

## Notes

- Sessions stored as markdown in `~/.claude/sessions/`
- Aliases stored in `~/.claude/session-aliases.json`
- Session IDs can be shortened (first 4-8 chars usually unique)
