---
description: Phase 1.1 - Technical Setup & Toolchain Validation
---
# Workflow: Technical Setup (1.1)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Prerequisite:** 
1. `/workflow-implement-0.1-blueprint` (Blueprint Finalized)
2. `/workflow-implement-0.2-audit-feature` (Architectural Sign-off)
3. `/workflow-refinement-4-dor` (DoR Handover)

**Persona Requirement:** [Angie](../personas/architect-angie/angie-persona.md)

1. **Toolchain Validation**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Verify the local development environment.
   - **Execute:** // turbo (Check `docker`, `node`, `pip`).
   - **Result:** Report if tools are missing or not in PATH. Automatically fix PATH if possible (e.g., `/usr/local/bin`).
   - **🛑 STOP:** Confirm toolchain is ready before analysis.

2. **Branching Intent**
   - **Explain:** "I intend to create a dedicated feature branch `feat/[feature-name]` to keep the work isolated."
   - **🛑 STOP:** [Gate 1] Wait for user approval to run the git command.
   - **Execute:** `git checkout -b feat/[feature-name]`
   - **Result:** Report that the branch is created.

3. **ADR Preparation**
   - **Explain:** "I will now draft an Architectural Decision Record (ADR) to document our chosen path."
   - **🛑 STOP:** [Gate 3] Wait for approval to write the document.
   - **Execute:** Write ADR to `docs/architecture/adr/`.
   - **Result:** Confirm ADR is written and provide path for review.
   - **🛑 STOP:** Final setup verification before moving to Step 2.
