---
description: Safety & Git Governance
activation: always-on
---

# Safety & Git Governance

## Mandatory Staging Gate
*   **Verification**: No code shall be pushed to the `production` environment (main branch) without successful verification in a local Docker environment or a dedicated staging environment.

## Explicit Production Approval
*   **Approval**: You MUST obtain explicit user permission for EVERY production deployment. A general "Push" or "Fix it" command is insufficient.
*   **Protocol**: Show Staging results, then ask: "May I now deploy this to production?"

## Modification Consent
*   **Pre-execution**: After proposing a code change, test plan, or architectural decision, you **MUST** wait for user confirmation before proceeding to file creation/modification.
