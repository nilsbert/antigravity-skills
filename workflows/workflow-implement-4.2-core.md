---
description: Phase 4.2 - Core Verification
---
# Workflow: Core Verification (4.2)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Lisa](../../personas/tester-lisa/lisa-avatar.png)

1. **Full Tests**
   - **Execute:** `pytest`.

2. **Coverage Analysis**
   - **Execute:** `pytest --cov`.

3. **Continuous Flow**
   - **Rule:** If tests pass and coverage is > 80%, **PROCEED IMMEDIATELY** to `/workflow-implement-4.3-bdd`.
   - **🛑 STOP:** ONLY if coverage falls below 80% or tests fail.
