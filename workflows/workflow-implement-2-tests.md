---
description: Phase 2 - Test Design & Doc Impact for Feature Implementation
---
# Workflow: Test Design (Step 2)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Angie](../personas/architect-angie/angie-persona.md) + [Lisa](../personas/tester-lisa/lisa-persona.md)


## User Review Gates
- [ ] **Gate 4:** Documentation impact assessment
- [ ] **Gate 5:** Test scenarios and failure criteria
- [ ] **Gate 6:** Test code implementation review
- [ ] **Gate 7:** Verification of the "Red" (Failure) status

1. **Doc Impact & Rules Check**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Read [Global Rules](../rules/global-rules.md).
   - **Explain:** "I will check `ddd-glossary.md` and `system-design.md` for necessary updates to ensure the domain model is updated."
   - **🛑 STOP:** [Gate 4] Wait for approval to scan docs and present findings.
   - **Execute:** Check docs.
   - **Result:** Propose changes or report no impact.
   - **🛑 STOP:** Wait for user to approve doc changes.

2. **The "Red Case" Discovery (Lisa)**
    - **Display:** `![Lisa](../personas/tester-lisa/lisa-avatar.png)`
   - **Explain:** "Lisa will identify potential failure points (Sad Paths) and edge cases."
   - **🛑 STOP:** [Gate 5] Wait for Lisa to start and list scenarios.
   - **Result:** Lisa lists 2+ Red Scenarios (e.g., 'Empty Result', 'Invalid Input').
   - **🛑 STOP:** Wait for user feedback on scenarios.

3. **Test File Planning**
    - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
    - **Explain:** "I will now draft the actual test code. Here is the plan:"
    - **Explain:** "**Unit Tests:** Focus on individual functions/classes in isolation (e.g., `matcher.match()`). verification of logic correctness."
    - **Explain:** "**Integration Tests:** Verify how components work together (e.g., Database + Matcher). verification of data flow."
    - **Explain:** "**E2E Tests:** Simulate real user behavior from start to finish (e.g., UI Click -> Webhook Trigger). verification of the full feature."
    - **Action:** Ask user which levels are required for this feature.
    - **Constraint:** "Tests must follow the patterns defined in `../.agents/templates/test-unit.md`."
    - **🛑 STOP:** [Gate 6] Wait for approval to draft and present the specific tests.
    - **Result:** Present the **FULL** test code (or complete file content) for review.
    - **Explain:** Walk through the drafted tests, explaining the purpose and assertions of each one.
    - **Action:** Ask: "Do these tests cover the requirements? Do you have any feedback?"
    - **🛑 STOP:** Wait for user feedback and approval to ensure the tests are correct before execution.

4. **Test Execution (The Red Case)**
   - **Explain:** "I will now create the test file and run it to verify it fails as expected (RED phase)."
   - **🛑 STOP:** [Gate 7] Wait for approval to run tests and report failure.
   - **Execute:** Write file and run `pytest`.
   - **Result:** Report failure results.
   - **🛑 STOP:** Confirmation to move to the "Green" implementation phase.
