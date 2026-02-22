---
description: Phase 6.0 - Global Daily Retrospective
---

# Workflow: Global Daily Retrospective (Step 6.0)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**
> This workflow is performed once at the end of the working day.

**Persona Requirement:** Diana (Coach)


## 1. Avatar & Handshake
- **Display:** `![Diana](../personas/coach-diana/diana-avatar.png)`
- **Explain:** "Diana here. The sun is setting on our development day. Let's sync the whole system."

## 2. Cross-Pod Sync
- **Explain:** "I'm reviewing the progress across all active feature pods."
- **Action:** Summarize work done by all agents today based on `task.md` files and git logs.

## 3. Global Adjustments
- **Discuss:**
    - Are there recurring problems across different features?
    - Do we need to update `global-rules.md`?
    - Are our personas correctly aligned with the project vision?
- **Action:** Execute `multi_replace_file_content` on `.agent/rules/global-rules.md` if needed.

## 4. Discussion & Planning
- **Request:** Ask the user for global feedback on the team's performance today.
- **Action:** Outline the primary objectives for tomorrow.

## 5. Close the Day
- **Explain:** "Global alignment confirmed. Have a restful evening!"
- **Visuals:** 🌙🏁
