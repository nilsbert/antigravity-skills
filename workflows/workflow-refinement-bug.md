# Workflow: Bug Refinement (Streamlined)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Jeff](../personas/features-jeff/jeff-persona.md) (Product Owner) + [Lisa](../personas/tester-lisa/lisa-persona.md) (QA)

**Goal:** Rapidly reproduce, analyze, and plan a fix for a reported bug. Focus is on *Reproduction* rather than extensive feature documentation.

## User Review Gates
- [ ] **Gate 1:** Reproduction Confirmed
- [ ] **Gate 2:** Fix Plan Approved

---

## Steps

### 1. Triage & Persona Activation
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "Jeff here. I see a bug report. Let's triage this."
- **Action:** Analyze the bug report (Issue or Chat).
- **Checks:**
    - Is it a regression?
    - Is it critical (blocker)?
    - Which Persona is affected? (Activate them!)

### 2. Reproduction First (The Red Test)
- **Explain:** "I need to see it fail before I can fix it."
- **Action:** Create a reproduction script (e.g., `scripts/reproduce_issue_[id].py`) or a failing test case.
- **Rules:** 
    - The script MUST fail currently.
    - It MUST mimic the user's reported scenario.
- **Result:** A failing script/test.
- **🛑 STOP:** [Gate 1] Confirm the bug is reproduced.

### 3. Root Cause Analysis (RCA)
- **Explain:** "Now that I've caught the bug, let's find the root cause."
- **Action:** Use logging/debugging to pinpoint the failure.
- **Display:** `![Lisa](../personas/tester-lisa/lisa-avatar.png)`
- **Lisa says:** "Is this an edge case or a core logic failure? Let's check the boundaries."

### 4. Fix Planning (Lightweight)
- **Explain:** "I have a plan to fix this."
- **Action:** Create `implementation_plan.md` (Short form).
- **Content:**
    - **RCA:** What is broken.
    - **Fix:** What files to change.
    - **Verification:** How the reproduction script will pass.
- **Result:** Plan ready for review.
- **🛑 STOP:** [Gate 2] Wait for approval to apply the fix.

### 5. GitHub Sync
- **Explain:** "Syncing findings to GitHub."
- **Action:** Update the Issue with:
    - Reproduction steps/script.
    - Root Cause Analysis.
    - Implementation Plan.
- **Label:** `bug`, `ready-for-dev`.

---

**Next Workflow:** `/workflow-implement-1-setup`
