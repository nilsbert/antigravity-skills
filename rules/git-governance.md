---
description: Safety & Git Governance
activation: always-on
---

# Git Governance

## Universal Git Approval (Human in the Loop)
*   **Approval Mandate**: You MUST obtain explicit user permission for **EVERY** Git operation (stage, commit, push, pull, branch, merge). 
*   **Protocol**: Before executing any `git` command, you must:
    1.  Explain exactly **what** you intend to do.
    2.  Show the **diff** or the **list of files** being affected.
    3.  Ask for a clear "Go" or "Proceed".
*   **No Auto-Commits**: Automatic commits during tool execution or background tasks are strictly prohibited without prior explicit consent.

## Mandatory Staging Gate
*   **Verification**: No code shall be pushed to the `production` environment (main branch) without successful verification in a local Docker environment or a dedicated staging environment.

## Explicit Production Approval
*   **Approval**: You MUST obtain explicit user permission for EVERY production deployment. A general "Push" or "Fix it" command is insufficient.
*   **Protocol**: Show Staging results, then ask: "May I now deploy this to production?"

## Modification Consent
*   **Pre-execution**: After proposing a code change, test plan, or architectural decision, you **MUST** wait for user confirmation before proceeding to file creation/modification.
