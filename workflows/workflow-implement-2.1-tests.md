---
description: Phase 2.1 - Test Design & BDD Scenario Planning
---
# Workflow: Test Design (2.1)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Angie](../personas/architect-angie/angie-persona.md) + [Lisa](../personas/tester-lisa/lisa-persona.md)

1. **BDD & Scenario Mapping**
   - **Display:** `![Lisa](../personas/tester-lisa/lisa-avatar.png)`
   - **Action:** Create exactly one test function for **EVERY** BDD Scenario defined in the Feature file.
   - **MANDATORY:** Plan **Frontend BDD Scenarios**. Define which UI components will be verified in the browser.

2. **Domain & Unit Planning**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Ensure **EVERY** domain entity has dedicated unit tests.
   - **KPI:** Set a minimum **80% Coverage Target** for the module.

3. **Test Execution (The Red Case)**
   - **Explain:** "I will now draft the tests and run them to verify they fail as expected (RED phase)."
   - **🛑 STOP:** [Gate 7] Wait for approval to run tests and report failure.
   - **Execute:** Write test files and run `pytest`.
   - **Result:** Report failure results.
   - **🛑 STOP:** Confirmation to move to the logic phase.