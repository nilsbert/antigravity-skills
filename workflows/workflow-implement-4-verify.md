---
description: Phase 4-6 - Verification & Handover
---
# Workflow: Feature Verification (Step 4)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Angie](../personas/architect-angie/angie-persona.md) + [Lisa](../personas/tester-lisa/lisa-persona.md) + [Gene](../personas/admin-gene/gene-persona.md)


## User Review Gates
- [ ] **Gate 11:** UI/Browser Walkthrough results
- [ ] **Gate 12:** Single Source of Truth (Doc Sync) review
- [ ] **Gate 13:** Technical Handover (Commit/Push) authorization

1. **Docker Container Update (MANDATORY)**
   - **Action:** Ensure the local Docker environment reflects the latest code.
   - **Explain:** "I am rebuilding the frontend container to ensure all recent changes are applied."
   - **Execute:** `docker compose up -d --build frontend` (or backend if needed).
   - **Result:** Confirm container is running with latest changes.

2. **Browser Walkthrough & Evidence**
   - **Display:** `![Angie](../personas/architect-angie/angie-avatar.png)`
   - **Action:** Read [Global Rules](../rules/global-rules.md).
   - **Explain:** "I will perform a manual walkthrough in the browser (using the subagent) and capture a recording/screenshots as proof."
   - **🛑 STOP:** [Gate 11] Wait for approval to start the browser agent.
   - **Execute:** UI tests/walkthrough.
   - **Result:** Present `walkthrough.md` with embedded media.
   - **🛑 STOP:** Wait for user to confirm the feature meets the "Definition of Done".

2. **Single Source of Truth (SotR) Sync**
   - **Explain:** "I will update the Feature documents, project `task.md`, and any relevant ADRs to 'Finalized'."
   - **🛑 STOP:** [Gate 12] Wait for approval to sync documentation.
   - **Execute:** Update markdown files.
   - **Result:** Confirm sync and provide links to finalized docs.
   - **🛑 STOP:** Final verification of doc integrity.

3. **Duo & Admin Handover**
   - **Explain:** "I am passing the feature to Lisa for final stability check and Gene for branch delivery/merging."
   - **🛑 STOP:** [Gate 13] Authorize Gene to start the commit/push sequence.
   - **Display:** `![Gene](../personas/admin-gene/gene-avatar.png)`
   - **Execute:** `deliver feature [ID]`
   - **Result:** Proclaim the feature delivered and ring the bell 🔔.
   - **🛑 STOP:** End of Feature lifecycle. Pass to [Diana](../personas/coach-diana/diana-persona.md) for Retrospective.
