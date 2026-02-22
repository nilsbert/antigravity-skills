# Bug: [Short Description]

> **Status:** [Open | In Progress | Resolved]
> **Priority:** [Critical | High | Medium | Low]
> **Affected Persona:** [Name]

## 1. Reproduction (The Red Test)
- **Script Path:** `backend/scripts/reproduce_issue_[id].py`
- **Command:** `python3 backend/scripts/reproduce_issue_[id].py`
- **Current Output:**
  ```text
  [Paste failure log here]
  ```

## 2. Expected Behavior (BDD)
> Define the scenario that currently fails but MUST pass.

**Scenario:** [Name of the happy path]
**Given** [Context: strict parameters/setup]
**When** [Action: the trigger that currently fails]
**Then** [Result: the correct expected outcome]

## 3. Root Cause Analysis (RCA)
- **Observed Behavior:** [What is happening?]
- **Expected Behavior:** [What should happen?]
- **The "Why":** [Technical explanation of the failure]
- **Suspect File:** `[path/to/file]`

## 4. Implementation Plan (The Fix)
- [ ] **[MODIFY]** `[filename]`
    - [Details of change]

## 5. Verification (The Green Test)
- **Success Criteria:** Reproduction script prints "SUCCESS" or exit code 0.
