---
description: Phase 4.1 - Infra Verification
---
# Workflow: Infra Verification (4.1)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Angie](../../personas/architect-angie/angie-avatar.png)

1. **Build**
   - **Execute:** `docker compose up -d --build [service]`.

2. **Health Check**
   - **Execute:** `curl [service]/health`.
   - **Action:** Verify logs for runtime errors.

3. **Continuous Flow**
   - **Rule:** If container is healthy and build succeeded, **PROCEED IMMEDIATELY** to `/workflow-implement-4.2-core`.
   - **🛑 STOP:** ONLY on build failure or health-check crash.
