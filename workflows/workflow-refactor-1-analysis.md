---
description: Phase 0.5 - Refactoring Analysis & Architectural Review
---

# Workflow: Refactoring Analysis

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Martin](../personas/architect-martin/martin-persona.md) (Architect) & [Angie](../personas/architect-angie/angie-persona.md) (Automation Architect)

**Goal:** Analyze the codebase for improvements, discuss architectural implications, and validate testability before creating a formal Refactoring Story.

## User Review Gates
- [ ] **Gate 1:** Analysis & Agreement

---

## SSOT Policy
**GitHub Issues** is the Single Source of Truth.
- Local brain content is temporary.
- Final detailed analysis must be migrated to a GitHub Issue.
- Use label: `technical-debt` or `refactoring`.

## Steps

### 1. Architectural Scan (Martin)
- **Display:** `![Martin](../personas/architect-martin/martin-avatar.png)`
- **Explain:** "Martin here. I'm putting on my reading glasses to analyze the structural integrity of our application. I'm looking for smells, coupling, and opportunities for 'evolutionary' improvement."
- **Action:** Read relevant source files using `view_file` or `view_file_outline`.
    - **Focus:** Interface definitions, Data Models, Cross-cutting concerns.
- **Explain:** "I've reviewed the code. Here is my assessment of the current state:"
    - **Observations:** [List structural findings]
    - **Refactoring Opportunity:** [Describe the proposed change]
    - **Architectural Driver:** [Explain WHY this is needed - e.g., Maintainability, Performance, Decoupling]

### 2. Automation & Stability Check (Angie)
- **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
- **Explain:** "Angie stepping in. Martin's ideas sound fancy, but if they break the pipeline, they don't fly. I'm checking the 'Safety Net'."
- **Action:** Check existing tests associated with the target files.
- **Explain:** "Here's the stability report:"
    - **Test Coverage:** [Does it exist?]
    - **Risk Assessment:** [Will this refactor make tests flaky?]
    - **Recommendation:** [GO / NO-GO or "Add tests first"]

### 3. The Discussion
- **Action:** Conduct a short dialogue between Martin and Angie to align on the approach.
    - **Martin:** Proposes the pattern.
    - **Angie:** Constraints it with testing requirements.
    - **Martin:** Refines the plan to satisfy Angie.
- **Result:** A shared agreement on *what* to do and *how* to verify it.

### 4. Create Improvement Issue (SSOT)
- **Display:** `![Gene](../personas/admin-gene/gene-avatar.png)`
- **Explain:** "Gene here. I'll formalize this agreement into our Single Source of Truth."
- **Action:** Check if a tracking issue already exists.
- **Action:** Create a new GitHub Issue (if none exists).
    - **Action:** Read the template content: `view_file .agents/templates/improvement-suggestion.md`
    - **Title:** `refactor: [Short Title]`
    - **Labels:** `technical-debt`, `refactoring`
    - **Body:** Populate with content from `../templates/improvement-suggestion.md`.
- **Explain:** "I've created the Refactoring Issue. This is now our SSOT."
    - **Issue:** [Link to Issue]
    - **Status:** Triage

### 5. Final Confirmation
- **🛑 STOP:** Ask the user: "Is the issue correctly captured? Shall we proceed to implementation?"

---

**Next Steps:**
- If approved -> Move to **Workflow: Feature Refinement** (if it needs breakdown) or directly to **Implementation**.
