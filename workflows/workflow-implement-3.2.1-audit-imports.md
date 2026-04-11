---
description: Phase 3.2.1 - Imports & Dependency Audit
---
# Workflow: Imports Audit (3.2.1)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Martin](../../personas/architect-martin/martin-avatar.png)

1. **Dead Code Scan**
   - **Action:** Manual and automated scan for unused imports and variables.
   - **Action:** Check for orphaned logic paths.

2. **Import Integrity**
   - **Check:** Zero unresolvable paths.
   - **Check:** No cross-submodule relative imports.

3. **Continuous Flow**
   - **Rule:** If no orphans or unresolvable imports are found, **PROCEED IMMEDIATELY** to `/workflow-implement-3.2.2-audit-dry`.
   - **🛑 STOP:** ONLY if a critical dependency violation or logic rot is identified.
