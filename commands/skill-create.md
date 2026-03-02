---
name: skill-create
description: Analyze local git history to extract coding patterns and generate SKILL.md files. Local version of the Skill Creator GitHub App.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# Skill-Create Command

Analyze repository's git history to extract coding patterns and generate SKILL.md files.

## Execution

1. **Gather Git Data**:
   ```bash
   git log --oneline -n ${COMMITS:-200} --name-only --pretty=format:"%H|%s|%ad" --date=short
   ```

2. **Detect Patterns**:
   - Commit conventions (regex on commit messages)
   - File co-changes (files that always change together)
   - Workflow sequences (repeated file change patterns)
   - Architecture (folder structure and naming)
   - Testing patterns (locations, naming, coverage)

3. **Generate SKILL.md** with:
   - Commit conventions
   - Code architecture
   - Workflows
   - Testing patterns

4. **Optionally Generate Instincts** (if `--instincts`)

## Usage

```
/skill-create                    # Analyze current repo
/skill-create --commits 100      # Analyze last 100 commits
/skill-create --output ./skills  # Custom output directory
/skill-create --instincts        # Also generate instincts
```

## GitHub App Integration

For advanced features (10k+ commits, team sharing), use the [Skill Creator GitHub App](https://github.com/apps/skill-creator).
