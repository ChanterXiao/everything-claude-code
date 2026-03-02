---
description: Auto-analyze project and generate PM2 service commands.
---

# PM2 Command

Auto-analyze project and generate PM2 ecosystem config and commands.

## Execution

1. **Check PM2** - Install via `npm install -g pm2` if missing

2. **Scan Project** for services:
   - Vite (vite.config.*, port 5173)
   - Next.js (next.config.*, port 3000)
   - Express/Node (server directory, port 3000)
   - FastAPI/Flask (requirements.txt, port 8000)
   - Go (go.mod, port 8080)

3. **Generate Files**:
   - `ecosystem.config.cjs` - PM2 configuration
   - `{backend}/start.cjs` - Python wrapper (if needed)
   - `.claude/commands/pm2*.md` - Service commands
   - `.claude/scripts/pm2*.ps1` - PowerShell helpers

4. **Update CLAUDE.md** - Append PM2 section

## Generated Commands

- `/pm2-all` - Start all + monit
- `/pm2-all-stop` - Stop all
- `/pm2-all-restart` - Restart all
- `/pm2-{port}` - Start single + logs
- `/pm2-{port}-stop` - Stop single
- `/pm2-logs` - View all logs
- `/pm2-status` - View status

## Windows Configuration

- Config must use `.cjs` extension
- Specify `interpreter: 'C:/Program Files/nodejs/node.exe'`
- Python: Use Node.js wrapper with `windowsHide: true`

## Usage

```
/pm2                    # Generate PM2 config
/pm2 --port 3000,8000   # Specify ports
/pm2 --force            # Overwrite existing
```
