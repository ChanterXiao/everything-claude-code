---
description: Multi-model collaborative planning - Context retrieval + Dual-model analysis → Generate step-by-step implementation plan.
---

# Multi-Plan Command

Multi-model collaborative planning using Codex + Gemini.

## Execution

### Phase 1: Context Retrieval

1. **Prompt Enhancement** (if ace-tool MCP available):
   - Call `mcp__ace-tool__enhance_prompt` with $ARGUMENTS
   - Use enhanced prompt for subsequent phases

2. **Context Retrieval**:
   - Call `mcp__ace-tool__search_context` with semantic query
   - Gather relevant code context

3. **Completeness Check**:
   - Score requirement clarity (0-10)
   - If < 7, ask clarifying questions

### Phase 2: Multi-Model Analysis

**Parallel calls** to Codex and Gemini:

1. **Codex Analysis**:
   - ROLE: `~/.claude/.ccg/prompts/codex/analyzer.md`
   - Focus: Technical feasibility, architecture, risks

2. **Gemini Analysis**:
   - ROLE: `~/.claude/.ccg/prompts/gemini/analyzer.md`
   - Focus: UI/UX impact, visual design

Wait for both results with `TaskOutput`. **Save SESSION_IDs**.

### Phase 3: Generate Plan

Synthesize both analyses into implementation plan:

```markdown
## Implementation Plan: <Task>

### Task Type
- [ ] Frontend (→ Gemini) / [ ] Backend (→ Codex) / [ ] Fullstack

### Technical Solution
<Synthesized from Codex + Gemini>

### Implementation Steps
1. <Step 1>
2. <Step 2>
...

### Key Files
| File | Operation | Description |

### Risks and Mitigation

### SESSION_ID
- CODEX_SESSION: <id>
- GEMINI_SESSION: <id>
```

Save to `.claude/plan/<feature-name>.md` and present to user.

**STOP HERE** - Do not execute. User must run `/multi-execute` separately.

## Key Rules

- Plan only, no implementation
- External models have zero filesystem write access
- Include SESSION_IDs for `/multi-execute` handoff
