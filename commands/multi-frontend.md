---
description: Frontend-focused workflow (Research → Ideation → Plan → Execute → Optimize → Review), Gemini-led.
---

# Multi-Frontend Command

Frontend-focused multi-model workflow, Gemini-led.

## Execution

### Phase 1: Research
- Gather context about UI task
- Use ace-tool MCP if available
- Requirement completeness check (0-10), stop if < 7

### Phase 2: Ideation (Gemini-led)

Call Gemini with:
- ROLE: `~/.claude/.ccg/prompts/gemini/analyzer.md`
- Output: UI feasibility, solutions (at least 2), UX evaluation
- **Save SESSION_ID** (`GEMINI_SESSION`)

Present solutions, wait for user selection.

### Phase 3: Planning (Gemini-led)

Call Gemini (resume session):
- ROLE: `~/.claude/.ccg/prompts/gemini/architect.md`
- Output: Component structure, UI flow, styling approach

Claude synthesizes plan, save to `.claude/plan/task-name.md`.

### Phase 4: Implementation
- Follow approved plan
- Apply design system and code standards
- Ensure responsiveness, accessibility

### Phase 5: Optimization (Gemini-led review)

Call Gemini:
- ROLE: `~/.claude/.ccg/prompts/gemini/reviewer.md`
- Focus: Accessibility, responsiveness, performance, design consistency
- Integrate feedback after user confirmation

### Phase 6: Quality Review
- Check completion against plan
- Verify responsiveness and accessibility
- Report issues and recommendations

## Trust Rules

1. **Gemini frontend opinions are trustworthy**
2. Codex frontend opinions for reference only
3. External models have zero filesystem write access
