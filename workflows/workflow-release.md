---
description: Phase 8 - Production Release & Verification
---

# Phase 8: Production Release & Verification

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

This workflow defines the final step of the lifecycle: moving verified code from `main` to the Production environment.

## Step 1: Version Tagging
Release to production is triggered by a signed version tag:
```bash
git tag -a v1.x.y -m "Release [Feature Name]"
git push origin v1.x.y
```

## Step 2: Release Verification (Angie)
Angie monitors the GitHub Action and verifies the production site:
- [ ] **Generate Release Notes**: Create a `release-notes.md` explaining the changes to the user.
- [ ] **Monitor Deployment**: Tail the Azure logs during deployment (`gh run view --log`).
- [ ] **Health Check**: Poll the production URL until it returns `200 OK` with the new version.
- [ ] Confirm GitHub Action success.
- [ ] Check production frontend (at the production URL).
- [ ] Verify the "Environment" badge shows "PRODUCTION".

## Step 3: Final Handover
Once reachable and verified:
- Inform the user that the feature is live.
- Celebration with the full team.
- Mark the feature as fully released in `docs/product/features/`.
