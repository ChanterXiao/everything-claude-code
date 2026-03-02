---
description: Multi-model collaborative execution - Prototype from plan → Claude implements → Multi-model audit.
---

# Multi-Execute Command

Execute plan using multi-model collaboration.

## Execution

### Phase 0: Read Plan
1. Identify input (plan file path or direct description)
2. Read and parse plan content
3. Extract: task type, steps, key files, SESSION_IDs
4. Confirm with user if plan unclear

### Phase 1: Quick Context Retrieval

**Use MCP tool** `mcp__ace-tool__search_context`:
- Build semantic query from plan's Key Files
- Get complete context for implementation
- NEVER manually explore with find/ls

### Phase 2: Prototype Acquisition

**Route by Task Type**:

**Route A: Frontend/UI → Gemini**
- ROLE: `~/.claude/.ccg/prompts/gemini/frontend.md`
- OUTPUT: Unified Diff Patch ONLY
- **Gemini is frontend design authority**

**Route B: Backend/Logic → Codex**
- ROLE: `~/.claude/.ccg/prompts/codex/architect.md`
- OUTPUT: Unified Diff Patch ONLY
- **Codex is backend logic authority**

**Route C: Fullstack → Parallel**
- Gemini: Frontend part
- Codex: Backend part
- Wait for both with `TaskOutput`

Use `resume <SESSION_ID>` if plan contains SESSION_IDs.

### Phase 3: Code Implementation (Claude executes)

1. **Read Diff** - Parse Unified Diff from models
2. **Mental Sandbox** - Simulate changes, check consistency
3. **Refactor and Clean** - Convert prototype to production-grade
4. **Apply Changes** - Use Edit/Write tools
5. **Self-Verification** - Run lint/typecheck/tests

### Phase 4: Audit and Delivery

**Parallel calls** for review:
- Codex: Security, performance, error handling
- Gemini: Accessibility, design consistency

Wait for results with `TaskOutput`.

**Integrate fixes** and deliver:

```markdown
## Execution Complete

### Change Summary
| File | Operation | Description |

### Audit Results
- Codex: <Passed/Found N issues>
- Gemini: <Passed/Found N issues>

### Recommendations
1. [ ] <Test steps>
2. [ ] <Verification steps>
```

## Key Rules

1. **Code Sovereignty** – All modifications by Claude
2. **Dirty Prototype Refactoring** – Refactor model output to production code
3. **Trust Rules** – Backend: Codex, Frontend: Gemini
4. **Mandatory Audit** – Multi-model review after changes
