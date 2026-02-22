---
description: Phase 3 - Implementation Logic (Red/Green)
---
# Workflow: Code Implementation (Step 3)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Angie](../personas/architect-angie/angie-persona.md)

1. **Avatar & Strategic Handshake**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Read [Global Rules](../rules/global-rules.md).
   - **Explain:** "Angie here. Time to make those tests pass. I'll start with the architectural skeleton."


## User Review Gates
- [ ] **Gate 8:** API Skeleton / Method Signatures
- [ ] **Gate 9:** Core Logic implementation
- [ ] **Gate 10:** Integration & Stability check (Green phase)

2. **The Skeleton**
   - **Explain:** "I will define the classes and method signatures (The API surface/Contract) first to ensure architectural alignment."
   - **🛑 STOP:** [Gate 8] Wait for approval to code and present the skeleton.
   - **Execute:** Create skeleton.
   - **Result:** Present the skeleton code.
   - **🛑 STOP:** Wait for user approval of the structure.

3. **Logic Implementation Planning (TDD)**
   - **Explain:** "I will now outline the implementation plan, starting with the Test Case."
   - **TDD:** Write the *failing* test case first (if not done in Step 2).
   - **🛑 STOP:** [Gate 9a] Wait for approval to design the logic.
   - **Result:** Present the plan/pseudocode and the Red Test.
   - **Action:** Ask: "Does this logic match the requirements?"
   - **🛑 STOP:** Wait for approval of the plan.

4. **Code Implementation & Review**
   - **Explain:** "I will now translate the approved plan into code to make the test pass (Green)."
   - **Execute:** Write logic to the file.
   - **Check:** Run the specific test case to confirm it passes (Green).
   - **Result:** Display the implemented code and the Passing Test result.
   - **Action:** Ask: "Here is the implemented code. Shall we proceed to verification?"
   - **🛑 STOP:** [Gate 9b] Wait for code review and approval.

5. **Build & Test Verification**
   - **Explain:** "I will now run the full test suite and a smoke build to verify the system is stable."
   - **🛑 STOP:** [Gate 10] Wait for approval to run the verification commands.
   - **Execute:** // turbo (Run tests/build).
   - **Result:** Report Green status and provide the test log.
   - **🛑 STOP:** Decision point: Ready for verification or needs refactoring?
