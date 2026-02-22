---
description: Phase 0.1 - Refinement Discovery & Alignment
---

# Workflow: Story Refinement - Discovery (Step 0.1)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** [Jeff](../personas/features-jeff/jeff-persona.md) (Product Owner)

**Goal:** Discover and validate feature intent, then create or locate the corresponding GitHub Issue following the SSOT policy defined in the [Toolchain Manifest](../docs/admin/toolchain-manifest.md).

**SSOT Policy:** GitHub Issues is the Single Source of Truth. Local brain folder copies are valid ONLY while actively working; final state MUST sync back to GitHub.

## User Review Gates
- [ ] **Gate 1:** Feature Intent & Strategic Handshake

---

## Steps

### 1. Avatar & Strategic Handshake
- **Display:** `![Jeff](../personas/features-jeff/jeff-avatar.png)`
- **Explain:** "Jeff here. I'm stepping in to ensure our next feature is strategically sound. I'll start by summarizing my understanding of the request and how it fits our project goals."
- **🛑 STOP:** Wait for user to acknowledge or provide initial details.

### 2. Context Gathering
- **Action:** Read relevant high-level docs:
  - Vision Board: `docs/product/vision-board.md`
  - Roadmap (if exists)
  - Toolchain Manifest: `docs/admin/toolchain-manifest.md`
- **Explain:** "I've reviewed the project context to understand our strategic direction."
- **🛑 STOP:** "Does this feature directly impact our primary 'Target Group' defined in the Vision Board?"

### 3. Search GitHub Issues (SSOT)
- **Action:** Use GitHub CLI to search issues: `gh issue list --search "[keywords]"`
- **Fallback:** If CLI is unavailable, use browser tool to search GitHub Issues at `https://github.com/nilsbert/tender-finder/issues`
- **Search Query:** Use feature name, keywords, or related terms
- **Explain:** "I'm checking our SSOT (GitHub Issues) using the CLI to see if this feature already exists."

### 4. Issue Decision Point

**If Issue EXISTS:**
- **Action:** Capture issue URL and number (e.g., `#123`)
- **Action:** Note current state (idea/refining/ready/in develop/done)
- **Explain:** "Found existing issue #[number] in state '[state]'. I'll continue refinement from this point."
- **Result:** Proceed to next workflow with existing issue

**If Issue DOES NOT EXIST:**
- **Action:** Create new GitHub Issue using GitHub CLI: `gh issue create --title "[Title]" --body "[Body]" --label "enhancement"`
- **Fallback:** If CLI fails, use browser tool to create the issue.
- **Template:** Select `feature-template.md` structure
- **Required Fields:**
  - Title: `feat: [Short Descriptive Name]`
  - State: `idea`
  - Labels: Add relevant domain/persona labels
  - Initial Content: Brief description only (full refinement in Phase 0.2)
- **Action:** Capture new issue URL and number
- **Explain:** "Created new issue #[number] with state 'idea' in our SSOT."
- **🛑 MANDATORY VALIDATION:** Verify the GitHub Issue is accessible by visiting the URL. Do NOT proceed unless you can confirm the issue exists in GitHub.
- **Result:** Issue URL and number captured for subsequent phases

### 5. Strategic Alignment Check
- **Display:** `![Jeff](docs/product/personas/features-jeff/jeff-avatar.png)`
- **Explain:** "I've established the GitHub Issue as our SSOT. Here's what I found:"
  - Issue Number: #[number]
  - Current State: [state]
  - Strategic Fit: [Brief assessment]
- **Result:** Ready to proceed to detailed refinement in Phase 0.2

---

**Next Workflow:** `/workflow-refinement-2-feature`