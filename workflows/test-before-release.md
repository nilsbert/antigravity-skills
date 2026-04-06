---
description: Phase 7.5 - Mandatory Testing Before Release
---

# Workflow: Mandatory Testing Before Release (Step 7.5)

> [!IMPORTANT]
> **This workflow MUST be completed before any release (Phase 8).**
> It ensures the system is stable in its target environment (Docker) and fully functional in the browser.

**Persona Requirement:** Angie (Automation Architect) & Lisa (QA)

## 1. Test Plan Generation
- **Explain:** "I'm drafting the mandatory Test Plan for this release."
- **Action:** Create `test-plan-vX.Y.Z.md` in the current session artifact directory.
- **Content:**
    - List of features to be verified.
    - Regression areas (e.g., Search, AI Enrichment, Teams Notification).
    - Browser compatibility check.

## 2. Docker Environment Validation
- **Action:** Run the system in Docker (Compose).
- **Verify:**
    - Backend health: `curl localhost:8000/health`
    - Worker health: Check logs for successful job polling.
    - Database connectivity: Verify data is reachable within the container.
- // turbo
- **Command:** `docker compose up -d --build && sleep 10 && curl -f http://localhost:8000/health`

## 3. Browser-Based E2E Verification
- **Action:** Open the application in the browser.
- **Tasks:**
    - Perform a search.
    - Export keywords.
    - Verify UI responsiveness (PDS compliance check).
- **Result:** Capture screenshots/recordings of the successful flow.

## 4. Sad Path Stress Test
- **Action:** Simulate at least one failure (e.g., API timeout, invalid input).
- **Verify:** Error handling is graceful and user-friendly.

## 5. Handover Verdict
- **Explain:** "Testing complete. Results recorded in walkthrough.md."
- **Decision:** If any critical test fails, the release is **ABORTED**.

---
> *Testing is the heart of stability. - Angie*
