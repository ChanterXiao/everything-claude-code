---
description: Multi-model collaborative development with intelligent routing: Frontend → Gemini, Backend → Codex.
---

# Multi-Workflow Command

Multi-model collaborative development (Research → Ideation → Plan → Execute → Optimize → Review).

## Execution

### Phase 1: Research & Analysis

1. **Prompt Enhancement** (ace-tool MCP):
   - Call `mcp__ace-tool__enhance_prompt`
   - Replace $ARGUMENTS with enhanced result

2. **Context Retrieval**:
   - Call `mcp__ace-tool__search_context`

3. **Completeness Check** (0-10), stop if < 7

### Phase 2: Solution Ideation

**Parallel calls** to Codex and Gemini:
- Codex: Technical feasibility, solutions, risks
- Gemini: UI feasibility, solutions, UX evaluation

Wait for results. **Save SESSION_IDs** (`CODEX_SESSION`, `GEMINI_SESSION`).

Synthesize analyses, present solutions (at least 2), wait for user selection.

### Phase 3: Detailed Planning

**Parallel calls** (resume sessions):
- Codex: Backend architecture
- Gemini: Frontend architecture

Claude synthesizes plan, save to `.claude/plan/task-name.md`.

### Phase 4: Implementation
- Follow approved plan
- Apply project code standards
- Request feedback at milestones

### Phase 5: Code Optimization

**Parallel calls**:
- Codex: Security, performance, error handling
- Gemini: Accessibility, design consistency

Integrate feedback after user confirmation.

### Phase 6: Quality Review
- Check completion against plan
- Run tests to verify
- Report issues and recommendations

## Key Rules

1. Phase sequence cannot be skipped
2. External models have zero filesystem write access
3. Force stop when score < 7 or user does not approve
