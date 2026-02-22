---
description: Phase 0 - Project & Toolchain Setup
---

# Workflow: Toolchain Setup (Admin)

> [!IMPORTANT]
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** ![Gene](docs/product/personas/admin-gene/gene-avatar.png) [Gene](docs/product/personas/admin-gene/gene-persona.md) (Release Manager)

## User Review Gates
- [ ] **Gate 1:** Manifest Configuration Review

---
1. Let the Persona explain what s/he will do!
2. **Manifest Initialization**
   - **Action:** Read [Global Rules](../rules/global-rules.md).
   - **Check:** Does `docs/admin/toolchain-manifest.md` exist?
   - **If NO:** Copy from `.agent/templates/project-manifest.md` to `docs/admin/toolchain-manifest.md`.
   - **If YES:** Read the existing file to check for empty fields.
   - **Explain:** "I am initializing the Project Toolchain Manifest from our template to `docs/admin/toolchain-manifest.md`."

3. **Configuration Interview**
   - **Action:** Identify empty fields in `docs/admin/toolchain-manifest.md`.
   - **Explain:** "I need to fill in the empty fields to establish our Single Source of Truth."
   - **Loop:** Ask user for specific details (Repo URL, Project Key, etc.) for any empty fields.
   - **Execute:** Update the file with user answers.

4. **Manifest Review**
   - **Action:** Read the fully populated manifest.
   - **STOP:** [Gate 1] "Please review the Toolchain Manifest. Is this accurate?"

---
**Next Workflow:** `/workflow-refinement-1-discovery`