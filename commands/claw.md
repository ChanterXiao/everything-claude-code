---
description: Start the NanoClaw agent REPL — a persistent, session-aware AI assistant.
---

# Claw Command

Start an interactive AI agent session with persistent history.

## Execution

```bash
node scripts/claw.js
```

Or via npm:
```bash
npm run claw
```

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `CLAW_SESSION` | `default` | Session name |
| `CLAW_SKILLS` | *(empty)* | Comma-separated skill names to load |

## How It Works

1. Reads `CLAW_SESSION` to select named session (default: `default`)
2. Loads conversation history from `~/.claude/claw/{session}.md`
3. Optionally loads ECC skill context from `CLAW_SKILLS`
4. Enters blocking prompt loop - each message sent to `claude -p` with history
5. Responses appended to session file for persistence

## REPL Commands

```
/clear      Clear current session history
/history    Print full conversation history
/sessions   List all saved sessions
/help       Show available commands
exit        Quit the REPL
```

## Session Storage

Sessions stored as Markdown in `~/.claude/claw/`:
- `~/.claude/claw/default.md`
- `~/.claude/claw/my-project.md`

## Examples

```bash
# Start default session
node scripts/claw.js

# Named session
CLAW_SESSION=my-project node scripts/claw.js

# With skill context
CLAW_SKILLS=tdd-workflow,security-review node scripts/claw.js
```
