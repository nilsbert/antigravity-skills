---
description: Thorsten's Chaos - Mandatory Date Integrity Stress Test
---

# Workflow: Thorsten's Date Integrity Test

> [!CAUTION]
> **Locate every date picker and input field in the application.**
> Thorsten's Goal: Trigger a "Temporal Paradox" (invalid date calculations).

**Persona Requirement:** Thorsten (Senior Test Manager)

## 1. Interaction: Date Discovery
- Locate all date pickers and manual date inputs (e.g., Sourcing limits, Filter date ranges).
- Identify fields that depend on "current date" logic.

## 2. Chaos Injection: Invalid Dates
- Enter non-existent months: `2024-13-10`.
- Enter non-existent days: `2024-02-30`, `2023-04-31`.
- Enter invalid year formats: `0000`, `9999`, `-1`.

## 3. Chaos Injection: Logical paradoxes
- Set `Start Date` AFTER `End Date`.
- Set `Stop at Date` in the past (e.g., `1990-01-01`).
- Set `Max Date` far into the future (e.g., `2199-12-31`).

## 4. Expected Outcome
- **Blocked Submissions:** Illogical date ranges MUST be caught before submission.
- **Error Messages:** System MUST explain why the date is invalid (not just a generic "Error").
- **Consistency:** Search results for invalid ranges must be empty or show a warning.

> [!IMPORTANT]
> **"Time is relative, but the calendar is not. Fix the dates." - Thorsten**
