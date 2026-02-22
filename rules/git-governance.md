---
description: Safety & Git Governance
activation: always-on
---

# Safety & Git Governance (Rules)

## 1. Safety & Git Governance
*   **Mandatory Staging Gate**: No code Shall be pushed to the `production` environment (main branch) without prior successful verification in a local Docker environment or a dedicated staging environment.
*   **Explicit Production Approval**: You MUST obtain explicit user permission for EVERY production deployment. A general "Push" or "Fix it" command is NOT enough for production. After presenting Staging results, you must ask: "May I now deploy this to production?"
*   **Wait for Approval**: After proposing a code change, test plan, or architectural decision, you **MUST** wait for user confirmation before proceeding to file creation/modification.
