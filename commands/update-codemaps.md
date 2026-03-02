---
description: Analyze codebase structure and generate token-lean architecture documentation.
---

# Update Codemaps Command

Generate architecture documentation optimized for AI context consumption.

## Execution

1. **Scan Project Structure**:
   - Identify project type (monorepo, single app, library)
   - Find source directories (src/, lib/, app/, packages/)
   - Map entry points

2. **Generate Codemaps** in `docs/CODEMAPS/`:
   - `architecture.md` - System diagram, service boundaries, data flow
   - `backend.md` - API routes, middleware, service → repository mapping
   - `frontend.md` - Page tree, component hierarchy, state management
   - `data.md` - Database tables, relationships, migrations
   - `dependencies.md` - External services, integrations

3. **Diff Detection**:
   - If changes > 30%, show diff and request approval
   - If changes <= 30%, update in place

4. **Add Metadata**:
   ```markdown
   <!-- Generated: 2026-02-11 | Files: 142 | Tokens: ~800 -->
   ```

5. **Save Report** to `.reports/codemap-diff.txt`:
   - Files added/removed/modified
   - New dependencies
   - Architecture changes
   - Staleness warnings

## Tips

- Focus on high-level structure, not implementation
- Prefer file paths and signatures over full code
- Keep each codemap under 1000 tokens
- Use ASCII diagrams for data flow
