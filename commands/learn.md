---
description: Extract reusable patterns from the session and save as skills.
---

# Learn Command

Analyze the current session and extract patterns worth saving as skills.

## Instructions

1. **Review Session** - Look for extractable patterns:
   - Error resolution patterns (error + root cause + fix)
   - Debugging techniques (non-obvious steps, tool combinations)
   - Workarounds (library quirks, API limitations)
   - Project-specific patterns (conventions, architecture decisions)

2. **Identify Most Valuable** - Select the most reusable insight

3. **Draft Skill File** using this format:
   ```markdown
   # [Pattern Name]
   **Extracted:** [Date]
   **Context:** [When this applies]

   ## Problem
   [What problem this solves]

   ## Solution
   [The pattern/technique]

   ## When to Use
   [Trigger conditions]
   ```

4. **Ask User Confirmation** before saving to `~/.claude/skills/learned/`

**Notes**: Don't extract trivial fixes (typos) or one-time issues. Focus on reusable patterns.
