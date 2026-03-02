---
description: Restate requirements, assess risks, and create step-by-step implementation plan. WAIT for user CONFIRM before touching any code.
---

# Plan Command

Invoke the planner agent to create a comprehensive implementation plan.

## Execution

@planner Analyze the user's request and create a detailed implementation plan following these steps:

1. **Restate Requirements** - Clarify what needs to be built in clear terms
2. **Break Down into Phases** - Create specific, actionable implementation steps
3. **Identify Dependencies** - List components that depend on each other
4. **Assess Risks** - Surface potential issues and blockers with severity (HIGH/MEDIUM/LOW)
5. **Estimate Complexity** - Provide time estimates for each phase
6. **WAIT for Confirmation** - Do NOT proceed with implementation until user explicitly confirms

Present the plan in a clear format and ask: "**Proceed with this plan?** (yes/no/modify)"
