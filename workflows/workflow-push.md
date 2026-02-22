---
description: Phase 5.1 - Feature Push & Synchronization
---

# Phase 5.1: Feature Push & Synchronization

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

This workflow standardizes how code is synced from local development to the remote feature branch.

## Step 1: Quality Check
Ensure the feature is ready for synchronization:
- [ ] Tests are passing.
- [ ] All requested UI adjustments are implemented.
- [ ] Staging environment code is in sync with local changes.

## Step 2: Commit & Push
Execute the synchronization with a descriptive message:
```bash
git add .
git commit -m "feat: [brief description of changes]"
git push origin [feature-branch-name]
```

## Step 3: Inform User
Use `notify_user` to confirm the push:
- Provide a summary of what was pushed.
- Link to the [Walkthrough](./walkthrough.md) for proof of verification.
- Provide the Pull Request creation link if applicable.
