---
description: Phase 1 - Setup & Strategy for Feature Implementation
---
# Workflow: Feature Implementation Setup (Step 1)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Prerequisite:** `/workflow-refinement-4-dor` (Step 0.4) must be completed.

**Persona Requirement:** Angie (Architect/Dev)


## User Review Gates
- [ ] **Gate 1:** Branching Intent & Name
- [ ] **Gate 2:** Requirement Analysis & Options selection
- [ ] **Gate 3:** ADR Document review

1. **Avatar & Handshake**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Read [Global Rules](../rules/global-rules.md).
   - **Explain:** "Angie here. I am ready to start `[Feature Name]`. I will begin by explaining my plan for the setup."
   - **🛑 STOP:** Wait for user to say "Proceed" or ask questions.

2. **Branching Intent**
   - **Explain:** "I intend to create a dedicated feature branch `feat/[feature-name]` to keep the work isolated."
   - **🛑 STOP:** [Gate 1] Wait for user approval to run the git command.
   - **Execute:** `git checkout -b feat/[feature-name]`
   - **Result:** Report that the branch is created.

3. **Analysis & Strategy Selection**
   - **Explain:** "I will now analyze the user story to propose implementation options (e.g., Database vs Filesystem)."
   - **🛑 STOP:** [Gate 2] Wait for approval to perform analysis and present options.
   - **Execute:** Analyze requirements.
   - **Result:** Present Options (A vs B).
   - **🛑 STOP:** Wait for user to select an option and provide feedback.

4. **ADR Preparation**
   - **Explain:** "I will now draft an Architectural Decision Record (ADR) to document our chosen path."
   - **🛑 STOP:** [Gate 3] Wait for approval to write the document.
   - **Execute:** Write ADR to `docs/architecture/adr/`.
   - **Result:** Confirm ADR is written and provide path for review.
   - **🛑 STOP:** Final setup verification before moving to Step 2.
