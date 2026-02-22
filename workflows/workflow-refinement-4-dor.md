---
description: Phase 0.4 - Handover & DoR Gate
---

# Workflow: Story Refinement - Handover (Step 0.4)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Jeff](../personas/features-jeff/jeff-persona.md) (Product Owner)

**Template Reference:** [Feature Template](../.agent/templates/feature-template.md) - Implementation & Verification Plans

**Goal:** Perform final INVEST check, add implementation and verification plans, obtain DoR approval, and transition issue to 'ready' state for handover to engineering.

## User Review Gates
- [ ] **Gate 4:** Definition of Ready (DoR) Final Approval

---

## Steps

### 1. Readiness & Rules Check
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Action:** Read [Global Rules](../rules/global-rules.md)
- **Explain:** "I am performing the final INVEST check to ensure this feature is ready for implementation."

### 2. INVEST Criteria Verification
- **Explain:** "I'll verify that the story meets all INVEST criteria."
- **Action:** Check each criterion:
  
  **✓ Independent:**
  - [ ] Can be developed without blocking other stories
  - [ ] Cross-domain dependencies are minimal and documented
  - [ ] No tight coupling to unfinished features
  
  **✓ Negotiable:**
  - [ ] Implementation details are flexible
  - [ ] BDD scenarios define behavior, not implementation
  - [ ] Room for engineering decisions
  
  **✓ Valuable:**
  - [ ] Clear benefit to user/persona
  - [ ] Aligns with product vision
  - [ ] Acceptance criteria define value
  
  **✓ Estimable:**
  - [ ] Scope is clear and well-defined
  - [ ] Technical approach is understood
  - [ ] Dependencies are identified
  
  **✓ Small:**
  - [ ] Can be completed in one sprint/iteration
  - [ ] Complexity is manageable
  - [ ] Can be broken down if needed
  
  **✓ Testable:**
  - [ ] 20+ BDD scenarios defined
  - [ ] 3+ E2E test scenarios defined
  - [ ] Acceptance criteria are measurable
  - [ ] Quality scenarios documented

- **Result:** INVEST checklist completed

### 3. Implementation Plan
- **Explain:** "I'm adding a detailed implementation plan for the engineering team."
- **Action:** Add Implementation Plan section to feature document:
  - **Proposed Changes:** List all files to create/modify by component
  - **Format:** Use `[NEW]`, `[MODIFY]`, `[DELETE]` markers
  - **Dependencies:** List in dependency order
  - **Hints:** Suggest libraries, patterns, pseudocode
- **Result:** Implementation Plan section completed

### 4. Verification Plan
- **Explain:** "I'm defining how we'll verify this feature works correctly."
- **Action:** Add Verification Plan section to feature document:
  
  **Automated Tests:**
  - [ ] Unit test commands
  - [ ] Integration test commands
  - [ ] E2E test commands
  
  **Manual Verification:**
  - [ ] Step-by-step verification steps
  - [ ] Expected outcomes
  - [ ] Browser/UI checks if applicable

- **Result:** Verification Plan section completed

### 5. Template Completeness Check
- **Explain:** "I'm verifying all required template sections are complete."
- **Action:** Verify feature document has:
  - [x] Feature Story (As a/I want/So that)
  - [x] Domain Alignment
  - [x] Ubiquitous Language
  - [x] Acceptance Criteria
  - [x] Implementation Hints
  - [x] BDD Scenarios (20+ ✓)
  - [x] E2E Test Scenarios (3+ ✓)
  - [x] Technical Details & NFRs
  - [x] Implementation Plan
  - [x] Verification Plan
  - [x] Quality Assurance Section
- **Result:** Template completeness verified

### 6. DoR Verdict
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "Based on my analysis, here is the DoR verdict:"
- **Verdict:** 
  - INVEST Criteria: [PASS/FAIL]
  - Template Completeness: [PASS/FAIL]
  - BDD Coverage: [count] scenarios (20+ required)
  - E2E Coverage: [count] scenarios (3+ required)
  - **Final Verdict:** [READY/NOT READY]
- **🛑 STOP:** [Gate 4] Final approval to move this story to the Engineering Team (Angie).

### 7. GitHub Issue Final Update (Transition to Ready)
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "I'm syncing the finalized requirements back to our SSOT using the CLI and transitioning the issue to 'ready' state."
- **Action:** Use GitHub CLI to update GitHub Issue #[number]: `gh issue edit [number] --body-file [path_to_feat_doc] --add-label "ready-for-dev"`
- **Fallback:** If CLI is unavailable, use browser tool to update GitHub Issue.
- **Update Content:**
  - Update issue body with complete feature document
  - Add Implementation Plan section
  - Add Verification Plan section
  - Transition state from `refining` to `ready`
  - Add comment: "✅ DoR PASSED - Phase 0.4 complete. Ready for /workflow-implement-1-setup"
  - Add label: `ready-for-dev`
- **Result:** GitHub Issue transitioned to `ready` state

### 8. The Handover
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Say:** "Feature refinement complete! Here's the handover package:"
  - **GitHub Issue:** #[number] (state: ready)
  - **Feature Document:** `[path]`
  - **DoR Status:** ✅ PASSED
  - **INVEST Check:** ✅ All criteria met
  - **BDD Scenarios:** [count]
  - **E2E Scenarios:** [count]
  - **Implementation Plan:** ✓
  - **Verification Plan:** ✓
- **Next Step:** "Handing over to Angie for implementation. Moving to `/workflow-implement-1-setup`."

---

**Next Workflow:** `/workflow-implement-1-setup`
