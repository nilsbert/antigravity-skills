---
description: Phase 0.2 - User Story & BDD Generation
---

# Workflow: Feature Refinement - Feature Drafting (Step 0.2)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Jeff](../personas/features-jeff/jeff-persona.md) (Product Owner)

**Template Reference:** [Feature Template](../.agent/templates/feature-template.md)

**Goal:** Draft comprehensive feature documentation following the feature template structure, including domain alignment, ubiquitous language, and initial BDD scenarios.

## User Review Gates
- [ ] **Gate 2:** Feature Definition & BDD Review

---

## Steps

### 1. Feature Document Creation
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "I'm now drafting the complete feature document following our feature template structure."
- **Action:** Create feature document in brain folder: `brain/[conversation-id]/feat-[number]-[name].md`
- **Template Sections to Complete:**
  - Feature Story (As a/I want/So that)
  - Domain Alignment (Primary Domain, Cross-Domain Dependencies)
  - Ubiquitous Language (DDD terms)
  - Acceptance Criteria (initial list)
  - Implementation Hints
  - BDD Scenarios (start with 5-10, will expand in Phase 0.3)
  - Technical Details & NFRs
- **Result:** Feature document path provided

### 2. Domain Alignment Check
- **Explain:** "I'm ensuring this feature aligns with our DDD bounded contexts."
- **Action:** Identify primary domain (e.g., Tender Management, Search, Upload)
- **Action:** Document any cross-domain dependencies
- **Action:** Define key ubiquitous language terms
- **Result:** Domain section completed in feature doc

### 3. Persona Mapping
- **Explain:** "I'll ensure the 'As a [Role]' part specifically matches our defined Personas."
- **Action:** Review available personas in `docs/product/personas/`
- **Action:** Map feature to specific persona (e.g., Haruki, Admin)
- **🛑 STOP:** "Does this feature accurately represent the needs of `[Selected Persona]`?"

### 4. Initial BDD Scenarios
- **Explain:** "I'm drafting initial BDD scenarios using the structured template below. The template requires minimum 20 scenarios covering Happy, Problem, Error, and Edge cases."
- **Template Format (MANDATORY):**
  ```gherkin
  Scenario: [Descriptive name with context]
    Given [precondition - system state]
    And [additional precondition if needed]
    When [user action or trigger event]
    Then [expected outcome - observable result]
    And [additional expected outcome]
  ```

- **Quality Checklist:** Each scenario MUST:
  - [ ] Have a descriptive name that explains the context
  - [ ] Include specific, testable preconditions (no vague "user is logged in")
  - [ ] Describe concrete actions (no "user does something")
  - [ ] Define observable outcomes (no "system works correctly")
  - [ ] Be implementable as an automated test

- **Example - GOOD Scenario:**
  ```gherkin
  Scenario: Consultant views release notes for first time after v1.1.0 deployment
    Given the user is authenticated as "Birgit" (consultant persona)
    And the system has release notes for version "1.1.0"
    And the user has not dismissed the release notes modal before
    When the user clicks the "Release Notes" button in the header
    Then a modal appears with the heading "Release Notes"
    And the modal displays version "1.1.0" with date "2026-02-04"
    And the first change listed is "Expanded search engine to include full_text and contact_name"
  ```

- **Example - BAD Scenario (too fuzzy):**
  ```gherkin
  Scenario: User sees release notes
    Given user is logged in
    When user clicks button
    Then notes are shown
  ```

- **Action:** Create 5-10 initial scenarios covering:
  - **Happy Path** (2-3 scenarios): Primary use case with different user contexts
  - **Error Path** (2-3 scenarios): Validation failures, missing data, permission errors
  - **Edge Case** (1-2 scenarios): Boundary conditions, empty states, maximum limits
- **Note:** "We'll expand to 20+ scenarios in Phase 0.3 during validation."
- **Result:** Initial BDD scenarios documented with concrete Given/When/Then statements

### 5. Clarification & Assumptions
- **Explain:** "I've drafted the feature. Now, I need to verify my assumptions and ask for clarification."
- **Action:** List all assumptions made during drafting
- **Action:** Ask specific clarifying questions about:
  - Edge cases or business logic
  - NFR expectations (performance, security)
  - UI/UX requirements
  - Integration points
- **🛑 STOP:** [Gate 2] Wait for user answers and review of the draft.

### 6. GitHub Issue Update (Sync to SSOT)
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "I'm now syncing the refined feature back to our SSOT (GitHub Issues) using the CLI."
- **Action:** Use GitHub CLI to update GitHub Issue #[number]: `gh issue edit [number] --body-file [path_to_feat_doc] --title "feat: [Title]"`
- **Fallback:** If CLI is unavailable, use browser tool to update GitHub Issue.
- **Update Content:**
  - Replace issue body with feature document content
  - Update state from `idea` to `refining`
  - Add labels: domain label, persona label
  - Add comment: "Phase 0.2 complete - Feature drafted and ready for validation"
- **Result:** GitHub Issue updated and state transitioned to `refining`

### 7. Handoff Summary
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "Feature drafting complete. Here's what we have:"
  - Feature Document: `[path]`
  - GitHub Issue: `#[number]` (state: refining)
  - Primary Domain: `[domain]`
  - Persona: `[persona]`
  - Initial BDD Scenarios: `[count]`
- **Result:** Ready for validation phase

---

**Next Workflow:** `/workflow-refinement-3-validation`