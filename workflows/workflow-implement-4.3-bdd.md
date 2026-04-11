---
description: Phase 4.3 - BDD Validation
---
# Workflow: BDD Walkthrough (4.3)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Lisa](../../personas/tester-lisa/lisa-avatar.png)

1. **Proof-by-Scenario**
   - **Action:** Execute browser subagent for EVERY BDD scenario.
   - **Action:** Generate `walkthrough.md`.

2. **Continuous Flow**
   - **Rule:** If all scenarios are proven in the browser, **PROCEED IMMEDIATELY** to `/workflow-implement-4.4-handover`.
   - **🛑 STOP:** ONLY if a scenario fails its acceptance criteria.
