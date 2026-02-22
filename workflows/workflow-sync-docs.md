---
description: Documentation Synchronization with External Platforms
---

# Phase X - Documentation Synchronization with External Platforms

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** Gene (DevOps & Flow Strategist)

## Purpose
Synchronize local documentation files with external document management platforms (GitHub Issues, Jira, Miro, etc.) to ensure consistency across all project documentation spaces.

## Prerequisites
- Access tokens/API keys configured for target platforms
- Local documentation structure is organized and up-to-date
- Clear mapping between local docs and external platform items

## Steps

### 0. Avatar & Handshake
- **Display:** `![Gene](docs/product/personas/admin-gene/gene-avatar.png)`
- **Action:** Read [Global Rules](../rules/global-rules.md).
- **Explain:** "Gene here. I'm ready to help you synchronize your local documentation with external platforms like GitHub Issues, Jira, and Miro. This is all about maintaining **The Single Source of Truth** across your toolchain. I'll ensure your documentation flows seamlessly between systems and remains traceable. Let me walk you through the synchronization workflow."
- **🛑 STOP:** Wait for user to say "Proceed" or ask questions.

### 1. Inventory Local Documentation
**Objective**: Identify all documentation that should be synchronized

**Actions**:
- List all documentation files in `docs/` directory
- Categorize documentation by type:
  - Architecture Decision Records (ADRs) → GitHub Issues/Wiki
  - User Stories/Features → Jira Stories
  - Architecture Diagrams → Miro Boards
  - API Documentation → GitHub Wiki/Confluence
  - Process Workflows → Miro/GitHub Wiki
- Create a mapping file: `docs/sync-mapping.json` to track relationships

```bash
# List all documentation files
find docs/ -type f -name "*.md" | sort
```

### 2. Configure Integration Settings
**Objective**: Set up authentication and connection details

**Actions**:
- Create `.env.sync` file with platform credentials:
  ```
  GITHUB_TOKEN=<your-token>
  JIRA_API_TOKEN=<your-token>
  JIRA_BASE_URL=<your-jira-url>
  MIRO_ACCESS_TOKEN=<your-token>
  CONFLUENCE_API_TOKEN=<your-token>
  ```
- Verify connectivity to each platform
- Document platform-specific configuration in `docs/sync-config.md`

```bash
# Test GitHub API access
curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user

# Test Jira API access
curl -u email@example.com:$JIRA_API_TOKEN $JIRA_BASE_URL/rest/api/3/myself
```

### 3. Define Synchronization Rules
**Objective**: Establish what gets synced and how

**Actions**:
- Create `docs/sync-rules.md` documenting:
  - **ADRs** → Sync to GitHub Issues with label `adr`, link back to source
  - **User Stories** → Sync to Jira as Stories, maintain bidirectional links
  - **Architecture Diagrams** → Export to Miro boards, embed links in docs
  - **Workflows** → Keep in both local `.agents/workflows/` and GitHub Wiki
  - **Meeting Notes** → Sync to Confluence/GitHub Discussions
- Define sync direction for each doc type:
  - `local → external` (push only)
  - `external → local` (pull only)
  - `bidirectional` (two-way sync with conflict resolution)

### 4. Implement Sync Scripts
**Objective**: Create automation scripts for synchronization

**Actions**:
- Create `scripts/sync-docs.sh` as the main orchestrator
- Create platform-specific sync scripts:
  - `scripts/sync-github-issues.py` - Sync ADRs to GitHub Issues
  - `scripts/sync-jira.py` - Sync user stories and features
  - `scripts/sync-miro.py` - Sync architecture diagrams
  - `scripts/sync-confluence.py` - Sync general documentation
- Add metadata headers to local docs for tracking:
  ```yaml
  ---
  external_id: PROJ-1234
  platform: jira
  last_synced: 2026-02-05T20:00:00Z
  sync_direction: bidirectional
  ---
  ```

Example sync script structure:
```python
#!/usr/bin/env python3
# scripts/sync-docs.py

import os
import yaml
from pathlib import Path

def sync_to_github_issues(doc_path):
    # Parse document metadata
    # Create or update GitHub issue
    # Update local doc with external_id
    pass

def sync_to_jira(doc_path):
    # Parse document
    # Create or update Jira ticket
    # Link to local doc
    pass

def sync_to_miro(doc_path):
    # Parse diagrams
    # Upload to Miro board
    # Embed link in doc
    pass
```

### 5. Perform Initial Synchronization (Push)
**Objective**: Push existing local documentation to external platforms

**Actions**:
- Run dry-run mode first to preview changes
- Execute sync for each platform in order:

// turbo
```bash
# Dry run to preview changes
python scripts/sync-docs.py --dry-run --all

# Push ADRs to GitHub Issues
python scripts/sync-docs.py --sync-github-issues

# Push user stories to Jira
python scripts/sync-docs.py --sync-jira

# Push diagrams to Miro
python scripts/sync-docs.py --sync-miro
```

- Review created items in each platform
- Verify links and metadata in local docs

### 6. Validate Synchronization
**Objective**: Ensure all documents are properly synchronized

**Actions**:
- Check each external platform for created/updated items
- Verify bidirectional links are working
- Confirm metadata headers are populated in local docs
- Test search/discoverability in external platforms

```bash
# Generate sync report
python scripts/sync-docs.py --report

# Expected output:
# - Total docs synced: X
# - GitHub Issues created: Y
# - Jira tickets created: Z
# - Miro boards updated: W
# - Sync errors: 0
```

### 7. Set Up Continuous Synchronization
**Objective**: Automate regular synchronization

**Actions**:
- Add git pre-commit hook to detect doc changes:
  ```bash
  # .git/hooks/pre-commit
  #!/bin/bash
  python scripts/sync-docs.py --changed-only
  ```
- Set up scheduled sync job (cron/GitHub Actions):
  ```yaml
  # .github/workflows/sync-docs.yml
  name: Sync Documentation
  on:
    push:
      paths:
        - 'docs/**'
    schedule:
      - cron: '0 */6 * * *'  # Every 6 hours
  ```
- Document manual sync procedure for on-demand updates

### 8. Handle Conflicts and Updates
**Objective**: Manage conflicts when docs are updated in multiple places

**Actions**:
- Define conflict resolution strategy in `docs/sync-rules.md`:
  - **Strategy 1**: Local takes precedence (overwrite external)
  - **Strategy 2**: External takes precedence (pull updates)
  - **Strategy 3**: Manual review required (flag conflicts)
- Implement conflict detection in sync scripts
- Create conflict report: `docs/sync-conflicts.md`

```bash
# Pull updates from external platforms
python scripts/sync-docs.py --pull --all

# Review conflicts
cat docs/sync-conflicts.md

# Resolve conflicts manually, then re-sync
python scripts/sync-docs.py --resolve-conflicts
```

### 9. Documentation and Handover
**Objective**: Document the synchronization system for team use

**Actions**:
- Create comprehensive guide: `docs/sync-guide.md` including:
  - How to add new documents to sync
  - How to manually trigger sync
  - How to resolve conflicts
  - Troubleshooting common issues
- Update README with sync status badge
- Add sync health check to CI/CD pipeline
- Train team on sync workflow

### 10. Monitor and Maintain
**Objective**: Ensure ongoing synchronization health

**Actions**:
- Review sync logs weekly
- Update API tokens before expiration
- Monitor rate limits for each platform
- Collect feedback from team on sync effectiveness
- Iterate on sync rules based on actual usage patterns

```bash
# Check sync health
python scripts/sync-docs.py --health-check

# View recent sync activity
python scripts/sync-docs.py --log --days 7
```

## Success Criteria

✅ All local documentation is catalogued with clear platform mapping  
✅ Integration with GitHub Issues, Jira, and Miro is configured and tested  
✅ Initial sync completed successfully with all items created/updated  
✅ Bidirectional links between local docs and external items are working  
✅ Automated sync is running on schedule without errors  
✅ Team can manually trigger sync when needed  
✅ Conflict resolution process is documented and working  
✅ Sync health monitoring is in place  

## Notes

- **Rate Limits**: Be aware of API rate limits for each platform
- **Data Privacy**: Ensure sensitive information is not synced to public platforms
- **Versioning**: Consider how document versioning is handled across platforms
- **Archival**: Define process for archiving/deleting synced items when local docs are removed
- **Notifications**: Set up alerts for sync failures or conflicts
