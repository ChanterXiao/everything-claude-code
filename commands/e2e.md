---
description: Generate and run end-to-end tests with Playwright. Creates test journeys, runs tests, captures screenshots/videos/traces, and uploads artifacts.
---

# E2E Command

@e2e-runner Generate and execute end-to-end tests:

## Instructions

1. **Analyze User Flows** - Identify critical user journeys to test:
   - Authentication flows (login, signup, logout)
   - Core business flows (checkout, trading, payments)
   - Navigation flows

2. **Generate Test Journeys** - Create Playwright tests with:
   - Page Object Model pattern
   - Proper selectors (prefer data-testid)
   - Assertions for each step

3. **Run Tests** - Execute across browsers with:
   - Screenshots on failure
   - Video recording
   - Trace collection

4. **Handle Failures** - Analyze and fix or quarantine flaky tests

5. **Upload Artifacts** - Generate HTML reports and JUnit XML

Focus on the user flows the user wants to test.
