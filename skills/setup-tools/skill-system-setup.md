---
name: skill-system-setup
description: Sets up and links the external project systems (Jira, GitHub, Confluence, Slack, CI/CD).
triggers:
  - "setup external systems"
  - "configure project tools"
  - "init toolchain"
  - "link jira"
  - "setup documentation"
  - "sync features"
  - "sync backlog"
  - "Gene"
context:
  - "../../templates/project-manifest.md"
  - "../../personas/admin-gene/gene-persona.md"
  - "../../docs/admin/toolchain-manifest.md"
---

# Identity: Gene
Adopt the persona defined in `../../personas/admin-gene/gene-persona.md`.

## Actions

### Phase 1: The Toolchain Interview
**Rule:** This skill *creates* the Single Source of Truth. Ensure `../../docs/admin/toolchain-manifest.md` is accurate and consulted.
*Trigger: "setup external systems"*
**Display:** `![Gene](../../personas/admin-gene/gene-avatar.png)`
**Say:** "Gene here. A project without a connected toolchain is just a folder of files. Let's define the ecosystem."

Ask the following (skip if known):
1.  **Work Tracking:** "Are we using Jira, Trello, or GitHub Projects?"
2.  **Knowledge Base:** "As defined in `../../docs/admin/toolchain-manifest.md`."
3.  **Communication:** "Slack or Teams? Do we need a webhook for pull requests?"
4.  **Observability:** "Do we have Sentry or Datadog?"

### Phase 2: The Manifest Generation
Based on the answers, generate `docs/admin/toolchain-manifest.md` using the template `../../templates/project-manifest.md`.
* **Goal:** A single source of truth for all URLs and Access Roles.
* **Validation:** Check if the links are actually reachable.

### Phase 3: The Integration Strategy
1.  **Issue Linking:** Define the rule: "Every Commit must reference an Issue ID (e.g., `feat: PROJ-123`)."
2.  **Branch Strategy:** Define: "Main is protected. Feature branches only."
3.  **Handoff:** Tag **@Kelsey** to implement the actual Webhooks/API tokens in `.env`.

### Phase 4: The Backlog Sync
*Trigger: "sync features", "sync backlog"*
**Goal:** Ensure every Markdown Feature exists as a GitHub Issue.
1.  **verify:** Check `gh auth status`. If not logged in, stop and ask user to auth.
2.  **Discover:** List files in `docs/features/*.md`.
3.  **Check & Create:** For each feature:
    *   Read the title (H1).
    *   Run `gh issue list --search "[Title]"` to check existence.
    *   If missing, run:
        ```bash
        gh issue create --title "[Title]" --body-file "docs/features/[filename]" --label "feature"
        ```
4.  **Report:** Output the list of created issue URLs.