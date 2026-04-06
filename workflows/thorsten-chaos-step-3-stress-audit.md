---
description: Thorsten's Chaos - Mandatory UI Stress & Console Audit
---

# Workflow: Thorsten's UI Stress & Console Audit

> [!CAUTION]
> **Open every screen and check for browser errors and UI consistency.**
> Thorsten's Goal: Identify unhandled front-end exceptions.

**Persona Requirement:** Thorsten (Senior Test Manager)

## 1. Interaction: Rapid UI Stress
- Open every navigation menu and view.
- Perform rapid clicks (double-click "Apply", "Save", "Start").
- Refresh the browser mid-request (e.g., while a spinner is active).
- Open the same action in multiple browser tabs simultaneously.

## 2. Interaction: Interaction Audit
- Check if everything is visible (responsive design check).
- Verify if any buttons are overlapping or hidden on different screen sizes.

## 3. Console Audit (Cmd+Option+J)
- Audit the browser console on every page load and after every action.
- Ensure **ZERO** red error messages (e.g., 404, 500, TypeError).
- Ensure **ZERO** critical warnings (e.g., deprecated dependencies, unsaved data loss).

## 4. Expected Outcome
- **No Console Errors:** All API calls and UI renders must be clean in the background.
- **Single Action Persistence:** Double-clicks must NOT trigger multiple duplicate requests (Optimistic UI locking).
- **Graceful Refresh:** Refreshing during a process must NOT leave the system in an inconsistent state.

> [!IMPORTANT]
> **"If it's red in the console, it's a bug. Fix it." - Thorsten**
