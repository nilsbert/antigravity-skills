---
description: Phase 0.2 - Feature Audit & Gate
---
# Workflow: Feature Architectural Audit (0.2)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Martin](../personas/architect-martin/martin-persona.md)

1. **Gherkin & BDD Scrutiny**
   - **Display:** `![Martin](../personas/architect-martin/martin-avatar.png)`
   - **Check:** Are the **BDD Scenarios** specific enough to be automated? (No vague assertions).
   - **Check:** Does the feature violate any **Sovereignty Pillars** (e.g., trying to access another service's DB)?

2. **Glossary & Logic Alignment**
   - **Check:** Does the User Story use terms from the **Domain Glossary** correctly?
   - **Check:** Is there a clear **Aggregate Root** defined?

3. **Gate:** Martin's Architectural Sign-off.
   - **Action:** If the feature is architecturally "loose," Martin must reject it and provide specific Gherkin/Domain corrections.
   - **🛑 STOP:** [Gate A-2] Feature must be approved by Martin before Angie starts **Phase 1.1 (Setup)**.
