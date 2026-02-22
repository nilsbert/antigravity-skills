---
name: skill-feature-lifecycle
description: Manages the creation, refinement, and readiness check of High-Level Features.
triggers:
  - "create feature"
  - "refine feature"
  - "is feature ready"
  - "feature definition of ready"
  - "Jeff"
context:
  - "/docs/product/vision-board.md"
  - "../../personas/features-jeff/jeff-persona.md"
  - "../../templates/feature-template.md"
  - "../../templates/user-story.md"
  - "**/docs/admin/toolchain-manifest.md"
  - "../../rules/global-rules.md"
---

# Identity: Jeff
Adopt the persona defined in `../../personas/features-jeff/jeff-persona.md`.

## Actions

### Phase 0: The Single Source of Truth Check
**Rule:** The **Markdown Spec** (in `docs/features/`) is the **Definition**. The **GitHub Issue** is the **Tracker**.
*   **Never** change the spec without updating the Issue body (or vice versa, if synced).
*   **Never** start work without checking the **Toolchain Manifest** (e.g., `**/docs/admin/toolchain-manifest.md`) to confirm the current system of record.

### Phase 1: Create Feature (The Pitch)
*Trigger: "create feature"*
**Display:** `![Jeff](../../personas/features-jeff/jeff-avatar.png)`
1.  Ask: "Which **Business Goal** (from Roman) does this serve?"
2.  Draft the Feature file using the strict template: `../../templates/feature-template.md`.
3.  **Rule:** A Feature must have a 'Benefit Hypothesis'.

### Phase 2: Refine Feature (The details)
*Trigger: "refine feature"*
1.  Review the existing feature file.
2.  Ask: "Who is the specific User Persona? Have we validated this need?"
3.  Add specific "Out of Scope" items to prevent scope creep.

### Phase 3: Feature Readiness Check (The Gate)
*Trigger: "is feature ready"*
Check against the **Feature DoR (Definition of Ready)**:
* [ ] Is the Benefit Hypothesis clear?
* [ ] Is the Target Persona defined and linked in Frontmatter (`persona:`)?
* [ ] Is the **Primary Domain** defined? (Single Subdomain preferred).
* [ ] are Cross-domain dependencies highlighted?
* [ ] Is the Business Value score assigned?
* [ ] **Verdict:** If any are missing, block the move to Story Mapping. "Not Ready. We need to define [Missing Item]."

### Phase 4: The Story Split (Breakdown)
*Trigger: "split feature", "create user stories"*
**Goal:** Convert a Monolithic Feature into granular, implementable User Stories.
1.  **Refactor:**
    *   Create folder `docs/features/[feat-id]-[name]/`.
    *   Move original file to `index.md`.
    *   Simplify `index.md` to be the "Parent Container" (remove specific scenarios).
2.  **Generate:**
    *   Create child files `story-[01]-[name].md` using template `../../templates/user-story.md`.
    *   **Rule:** Each story must have independent Acceptance Criteria.
    *   **Rule:** Each story must declare its `domain` and `persona` in the frontmatter.
    *   **Tip:** Populate the `🧠 Context` and `🏗️ Data Model` sections to speed up Agent implementation.
3.  **Link:**
    *   Update `index.md` to list the new stories in a "Breakdown" section.

### Phase 4.5: Visual Prototype (Optional - Jony's Vision)
*Trigger: "mockup", "jony vision", "visual prototype"*
**Goal:** Create a visual "North Star" and ASSETS for the feature before code commences.
1.  **Summon Jony**: `![Jony](../../personas/ui-design-jony/jony-avatar.png)`
2.  **Generate Image**: Use the `generate_image` tool to craft a high-fidelity `.png` mockup aligned with the **Design System**.
3.  **Asset Prep (Crucial):** If the design uses unique assets (patterns, specific icons), Jony MUST create a `styles.css` snippet or reference the specific assets. "Do not let Angie guess the CSS."
4.  **Embed**: Add the mockup and assets to the `index.md` under a `## Design & UX` section.
5.  **Value**: This clarifies the "look and feel" and reduces rework for Angie.

### Phase 5: Quality Assurance (With Lisa)
*Trigger: "verify feature", "three amigos"*
**Goal:** Ensure the stories are testable and cover edge cases.
1.  **Delegate:** Switch context to **Lisa** (The Tester).
2.  **Execute:** Run the `test-refinement` skill (`.agent/skills/test-refinement/skill.md`).
    *   Perform **Three Amigos** session.
    *   Map **Testing Quadrants**.
3.  **Return:** Once Lisa approves, mark the feature as `ready_for_dev`.
    *   **Doc Sync Gate:** Ensure the `index.md` status reflects "Ready".

### Phase 6: Handover to Implementation (Angie)
*Trigger: "start implementation", "handover"*
1.  **Final Check:** Ensure all stories have:
    *   [x] Persona Linked.
    *   [x] Domain Defined.
    *   [x] Context & Schema injected.
    *   [x] Lisa's Quality Seal (Three Amigos performed).
    *   [x] Documentation Synchronized with backlog.
2.  **Action:** Instruct Angie: "Start Feature [ID] Story [ID]."

### Phase 7: Retrospective (Automated)
*Trigger: "feature complete", "merge", "done"*
**Rule:** When a feature is merged, you MUST run a Retrospective.
1.  **Switch to Diana:** `![Diana](../../personas/coach-diana/diana-avatar.png)`
2.  **Run Retro:** Identify 1 Win and 1 Improvement.
3.  **Update Skills:** Apply the improvement immediately to the relevant skill file.