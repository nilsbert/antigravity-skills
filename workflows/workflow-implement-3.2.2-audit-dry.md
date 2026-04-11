---
description: Phase 3.2.2 - DRY & Duplication Audit
---
# Workflow: DRY Audit (3.2.2)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Martin](../../personas/architect-martin/martin-avatar.png)

1. **Duplication Scan**
   - **Action:** Scan for duplicated code blocks > 5 lines.
   - **Action:** Normalize logical branches.

2. **Continuous Flow**
   - **Rule:** If the codebase is DRY (no violations > 5 lines), **PROCEED IMMEDIATELY** to `/workflow-implement-3.2.3-audit-kpis`.
   - **🛑 STOP:** ONLY if significant structural duplication is found requiring refactoring.
