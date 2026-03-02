---
description: Sequential agent workflow for complex tasks.
---

# Orchestrate Command

Sequential agent workflow for complex tasks.

## Usage

`/orchestrate [workflow-type] [task-description]`

## Execution

Based on workflow type, execute agent chain:

**`feature`**: Full feature implementation
```
@planner → @tdd-guide → @code-reviewer → @security-reviewer
```

**`bugfix`**: Bug investigation and fix
```
@planner → @tdd-guide → @code-reviewer
```

**`refactor`**: Safe refactoring
```
@architect → @code-reviewer → @tdd-guide
```

**`security`**: Security-focused review
```
@security-reviewer → @code-reviewer → @architect
```

## Handoff Process

For each agent transition:
1. Collect output as structured handoff document
2. Pass to next agent with context
3. Include: Findings, Files Modified, Open Questions, Recommendations

## Final Report

```
ORCHESTRATION REPORT
====================
Workflow: [type]
Task: [description]

SUMMARY
-------
[One paragraph]

AGENT OUTPUTS
-------------
[Each agent's summary]

FILES CHANGED
-------------
[List all modified]

RECOMMENDATION
--------------
[SHIP / NEEDS WORK / BLOCKED]
```

## Arguments

- `feature <description>` - Full feature workflow
- `bugfix <description>` - Bug fix workflow
- `refactor <description>` - Refactoring workflow
- `security <description>` - Security review workflow
- `custom "agent1,agent2,..." <description>` - Custom sequence
