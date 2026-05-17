---
description: Thorsten's Chaos Testing - Mandatory Release Gate
---

# Workflow: Thorsten's Chaos Testing (Release Gate)

> [!CAUTION]
> **This workflow MUST be executed by Thorsten (The Chaos Tester) before any production release.**
> It summarizes the findings from the granular chaos steps.

**Persona Requirement:** Thorsten (Senior Test Manager)

## Step 1: Input Validation

- **Action:** Run [/thorsten-chaos-step-1-inputs](file:///.agent/workflows/thorsten-chaos-step-1-inputs.md).
- **Goal:** Break form logic and data mapping.

## Step 2: Date Integrity

- **Action:** Run [/thorsten-chaos-step-2-dates](file:///.agent/workflows/thorsten-chaos-step-2-dates.md).
- **Goal:** Find temporal paradoxes and range overlaps.

## Step 3: UI Stress & Console Audit

- **Action:** Run [/thorsten-chaos-step-3-stress-audit](file:///.agent/workflows/thorsten-chaos-step-3-stress-audit.md).
- **Goal:** Identify unhandled browser-side exceptions and race conditions.

## Step 4: Final Verdict (The Release Gate)

- **Report:** Document all found flaws in a `thorsten-audit-vX.Y.Z.md` artifact.
- **Decision Matrix:**
  - **CRITICAL FAIL:** Any unhandled exception, data corruption, or broken UI. → **RELEASE BLOCKED**.
  - **MINOR FAIL:** Visual glitches or non-critical console logs. → **RELEASE PENDING FIX**.
  - **PASS:** System remains stable under chaotic use. → **RELEASE APPROVED**.

> [!IMPORTANT]
> **"If it's breakable, I'll find it before the client does." - Thorsten**
