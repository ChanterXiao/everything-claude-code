---
description: Backend-focused workflow (Research → Ideation → Plan → Execute → Optimize → Review), Codex-led.
---

# Multi-Backend Command

Backend-focused multi-model workflow, Codex-led.

## Execution

### Phase 1: Research
- Gather context about backend task
- Use ace-tool MCP if available
- Requirement completeness check (0-10), stop if < 7

### Phase 2: Ideation (Codex-led)

Call Codex with:
- ROLE: `~/.claude/.ccg/prompts/codex/analyzer.md`
- Output: Technical feasibility, solutions (at least 2), risks
- **Save SESSION_ID** (`CODEX_SESSION`)

Present solutions, wait for user selection.

### Phase 3: Planning (Codex-led)

Call Codex (resume session):
- ROLE: `~/.claude/.ccg/prompts/codex/architect.md`
- Output: File structure, function/class design, dependencies

Claude synthesizes plan, save to `.claude/plan/task-name.md`.

### Phase 4: Implementation
- Follow approved plan
- Apply backend code standards
- Ensure error handling, security, performance

### Phase 5: Optimization (Codex-led review)

Call Codex:
- ROLE: `~/.claude/.ccg/prompts/codex/reviewer.md`
- Focus: Security, performance, error handling, API compliance
- Integrate feedback after user confirmation

### Phase 6: Quality Review
- Check completion against plan
- Run tests to verify
- Report issues and recommendations

## Trust Rules

1. **Codex backend opinions are trustworthy**
2. Gemini backend opinions for reference only
3. External models have zero filesystem write access
