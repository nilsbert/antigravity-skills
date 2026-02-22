---
description: Phase 0.3 - Validation & Sad Path Analysis
---

# Workflow: Story Refinement - Validation (Step 0.3)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Jeff](../personas/features-jeff/jeff-persona.md) (Product Owner)

**Template Reference:** [Feature Template](../.agents/templates/feature-template.md) - BDD Scenarios & E2E Tests

**Goal:** Expand BDD scenarios to minimum 20, define E2E test scenarios, validate NFRs, and analyze sad paths comprehensively.

## User Review Gates
- [ ] **Gate 3:** Acceptance Criteria & Sad Path Review

---

## Steps

### 1. Validation Setup & Rules Check
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Action:** Read [Global Rules](../rules/global-rules.md)
- **Explain:** "I will now perform comprehensive validation, expanding our BDD scenarios and analyzing all sad paths."

### 2. BDD Scenario Expansion (Minimum 20 Required)
- **Explain:** "The feature template requires minimum 20 BDD scenarios. I'll expand our initial scenarios to cover all paths."
- **Action:** Expand BDD scenarios in feature document to include:
  
  **Happy Path (5+ scenarios):**
  - Primary use case
  - Alternative successful flows
  - Optimal conditions
  
  **Problem Path (5+ scenarios):**
  - Data missing or incomplete
  - System under load/slow response
  - Concurrent user actions
  - Partial failures with recovery
  
  **Error Path (5+ scenarios):**
  - Invalid input validation
  - Authentication/authorization failures
  - External service unavailable
  - Database connection errors
  - Timeout scenarios
  
  **Edge Cases (5+ scenarios):**
  - Boundary values (min/max)
  - Empty states
  - Very large datasets
  - Special characters/encoding
  - Race conditions

- **Action:** Use Scenario Outlines with Examples tables for data-driven tests
- **Action:** Add Background sections for shared context
- **Result:** Minimum 20 BDD scenarios documented

### 3. Sad Path Deep Analysis
- **Explain:** "I'm analyzing what happens when things go wrong. What if data is missing? What if the system is slow? I'll present these scenarios for your confirmation."
- **Action:** For each sad path, document:
  - Trigger condition
  - Expected system behavior
  - Error message/user feedback
  - State preservation/rollback
  - Recovery path
- **🛑 STOP:** Wait for user to confirm or adjust the edge case handling.

### 4. E2E Test Scenarios (Minimum 3 Required)
- **Explain:** "I'm defining end-to-end test scenarios from the user's perspective."
- **Action:** Create minimum 3 E2E test scenarios covering:
  - Complete user journey (happy path)
  - Error recovery flow
  - Edge case user experience
- **Format:** Step-by-step user actions with expected UI outcomes
- **Result:** E2E test scenarios documented in feature doc

### 5. NFR Validation
- **Explain:** "I'm validating Non-Functional Requirements."
- **Action:** Document NFRs in feature doc:
  - **Performance:** Response time expectations, throughput
  - **Security:** Authentication, authorization, data protection
  - **Dependencies:** External services, libraries, APIs
  - **Scalability:** Expected load, concurrent users
  - **Usability:** Accessibility, mobile responsiveness
- **Result:** Technical Details & NFRs section completed

### 6. UI/UX Linkage (If Applicable)
- **Action:** If UI is involved, cross-check with PDS guidelines
- **Action:** Reference PDS components needed (buttons, forms, modals, etc.)
- **Action:** Verify mobile-first requirements (touch targets > 48px)
- **🛑 STOP:** "I've verified the PDS components needed for this story. Are there any specific visual constraints I should document here?"

### 7. Quality Assurance Section
- **Explain:** "I'm adding quality scenarios for Lisa (QA) to review."
- **Action:** Add Quality Scenarios using format: Source → Stimulus → Environment → Response → Measure
- **Action:** Add Exploratory Charters
- **Action:** Define Test Strategy (mocks, test data)
- **Result:** Quality Assurance section completed

### 8. GitHub Issue Update (Sync Validation Results)
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "I'm syncing validation results back to our SSOT (GitHub Issues)."
- **Action:** Use browser tool to update GitHub Issue #[number]
- **Update Content:**
  - Update issue body with expanded BDD scenarios
  - Add E2E test scenarios
  - Add NFR validation results
  - Add comment: "Phase 0.3 complete - Validation done, 20+ BDD scenarios, 3+ E2E tests"
  - Keep state as `refining` (not ready until DoR passes)
- **Result:** GitHub Issue updated with validation results

### 9. Validation Summary
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "Validation complete. Here's the summary:"
  - BDD Scenarios: `[count]` (minimum 20 ✓)
  - E2E Test Scenarios: `[count]` (minimum 3 ✓)
  - Sad Paths Analyzed: `[count]`
  - NFRs Documented: ✓
  - Quality Scenarios: ✓
- **Result:** Ready for DoR gate in Phase 0.4

---

**Next Workflow:** `/workflow-refinement-4-dor`
