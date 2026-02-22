---
description: Phase 5 - Pull Request Review & Team Approval
---

# Phase 5: Pull Request Review & Team Approval

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

This phase ensures that every feature is technically reviewed by the persona collective and approved by the USER before final merging.

## Step 1: Prepare Technical Explanation (Angie)
Angie summarizes the changes, highlighting:
- **Motivation**: Why was this change necessary?
- **Core Changes**: What are the top 3-4 technical impacts?
- **Diff Highlights**: Show the most critical code snippets using `render_diffs` or focused code blocks.

## Step 2: Persona Collective Review (Martin & Lisa)
Simulate review comments from relevant personas:
- **Martin (Architect)**: Focuses on sustainability, ADR compliance, and technical debt.
- **Lisa (QA)**: Focuses on verification results, edge cases, and user experience.

## Step 3: Request USER Approval
Use `notify_user` to present the consolidated review:
- Display the persona avatars:
    - `![Angie](../personas/architect-angie/angie-avatar.png)`
    - `![Martin](../personas/architect-martin/martin-avatar.png)`
    - `![Lisa](../personas/tester-lisa/lisa-avatar.png)`
- Outline the technical summary.
- Show the review comments (Approved/Changes Requested).
- Explicitly ask: **"Do you approve of these changes for the final merge?"**

## Step 4: Final Handover
Once approved:
1. **Sync Task**: Mark Phase 5 as `[x]` in `task.md`.
2. **Final Commit/Push**: Ensure the branch is pushed to the remote repository.
3. **PR Link**: Provide the user with the direct link to create/view the Pull Request on GitHub.
