---
description: Phase 5.2 - Branch Merge & Celebration
---

# Phase 5.2: Branch Merge & Celebration

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

This workflow formalizes the transition from a feature branch to the `main` branch, signaling the start of the staging-to-production lifecycle.

## Step 1: Release Notes Entry
Before merging, add the technical documentation for the feature:
- [ ] Update `frontend/src/config/release-notes.json` with the new version and details.

## Step 2: Merge to Main
Execute the merge locally and push to trigger Staging deployment:
```bash
git checkout main
git merge [feature-branch-name]
git push origin main
```

## Step 3: Team Celebration & Pod Retro
Simulate a team celebration via `notify_user`:
- **Angie**: Summarizes the milestone.
- **Martin & Lisa**: Express their excitement and approval of the merge quality.
- **Visuals**: Use the celebration emoji 🥂✨.
- **Next Step:** Trigger `/workflow-retro-pod` (Step 5.3) for local system optimization.

## Step 4: Staging Deployment Check
Verify that the `push to main` correctly triggered the GitHub Action and that the changes are landing on the staging site.
