---
description: Phase 3.2.3 - Code Quality KPIs Audit
---
# Workflow: KPI Audit (3.2.3)

> [!IMPORTANT]
> // turbo-all
> **Adhere to [Global Rules](../../rules/global-rules.md).**

**Persona Requirement:** [Martin](../../personas/architect-martin/martin-avatar.png)

1. **Complexity & Maintainability**
   - **Metric Check:** Cyclomatic Complexity < 10.
   - **Metric Check:** Function Length < 30 lines.
   - **Metric Check:** Verify SRP (Single Responsibility Principle).

2. **Continuous Flow**
   - **Rule:** If KPIs meet thresholds, **PROCEED IMMEDIATELY** to `/workflow-implement-4.1-infra`.
   - **🛑 STOP:** ONLY if a function is too complex or architectural leaks are found.
