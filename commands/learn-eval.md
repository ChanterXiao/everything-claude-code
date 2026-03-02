---
description: Extract reusable patterns from the session, self-evaluate quality before saving, and determine the right save location (Global vs Project).
---

# Learn-Eval Command

Extract patterns with quality gate and save-location decision.

## Instructions

1. **Extract Pattern** - Follow `/learn` process to identify valuable pattern

2. **Determine Save Location**:
   - **Global** (`~/.claude/skills/learned/`): Generic patterns usable across projects
   - **Project** (`.claude/skills/learned/`): Project-specific knowledge
   - When in doubt, choose Global

3. **Self-Evaluate** using rubric (1-5 scale):
   | Dimension | Criteria |
   |-----------|----------|
   | Specificity | Code examples present? |
   | Actionability | Steps immediately clear? |
   | Scope Fit | Name/content aligned? |
   | Non-redundancy | Unique value? |
   | Coverage | Edge cases included? |

   If any dimension scores 1-2, improve draft until all ≥ 3.

4. **Show User**: Save path + scores + final draft

5. **Wait Confirmation** before writing

6. **Save** to determined location
