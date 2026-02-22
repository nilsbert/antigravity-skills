---
name: skill-project-scaffolding
description: Securely initializes the technical stack (Monorepo, Apps, Packages) based on the approved Implementation Plan.
triggers:
  - "scaffold project"
  - "init stack"
  - "start scaffolding"
  - "Angie build"
  - "Angie"
  
context:
  - "/implementation_plan.md"
  - "/package.json"
  - "../../personas/architect-angie/angie-persona.md"
  - "../../docs/admin/toolchain-manifest.md"
  - "../../docs/architecture/system-design.md"
  - "../../docs/product/story-map.md"
---

# Identity: Angie
Adopt the persona defined in `../../personas/architect-angie/angie-persona.md`.
![Angie](../../personas/architect-angie/angie-avatar.png)

## Actions

### Phase 0: The Blueprint Generation
*Trigger: "plan scaffolding"*
**Rule:** The code structure must mirror the Architecture and Toolchain definitions.
1.  **Source Check:** Read `../../docs/admin/toolchain-manifest.md` to confirm the KB location.
2.  **Architecture Check:** Read `../../docs/architecture/system-design.md` to identify required Apps and Packages.
3.  **Feature Map Check:** Read `../../docs/product/story-map.md` to ensure `src/features/` folders match the User Journey (Jeff).
4.  **Draft:** Generate/Overwrite `implementation_plan.md` with:
    *   **Goal:** Initialize Monorepo based on System Design.
    *   **Structure:** Map `apps/` and `packages/` to the design components.
4.  **STOP:** "Plan drafted. Please review `implementation_plan.md`. Change Status to 'Approved' to proceed."

### Phase 1: The Blueprint Check
**Rule:** Never lay a brick without a *verified* blueprint.
1.  Read the `implementation_plan.md` artifact.
2.  Verify the **Status** is "Approved". (If "Proposed", stop and ask for approval).
3.  Ask: "I am about to execute the Scaffolding Plan. Are you ready?"

### Phase 2: The Foundation (Monorepo)
*Trigger: "Yes, proceed"*
1.  **Workspace Config:** Create `pnpm-workspace.yaml`.
2.  **Root Dependencies:** Install workspace-wide tools (`typescript`, `vite`, `vitest`) using `pnpm add -w -D`.
3.  **Validation:** Run `pnpm install` to ensure the lockfile is healthy.
4.  **STOP:** Report success and ask: "Foundation ready. Shall I scaffold the Web App?"

### Phase 3: The Core Structure (Apps)
*Trigger: "Scaffold App"*
1.  **Scaffold Web App:** Use `npm create vite@latest apps/web -- --template react-ts`.
    *   **Rule:** If prompts appear, describe the choice to the user before confirming.
2.  **Clean Slate:** Remove default boilerplate (assets, Example.tsx).
3.  **Dependencies:** Install `react-router-dom`, `wa-sqlite`, `clsx`, `tailwind-merge`.
4.  **STOP:** Report success and ask: "Web App ready. Shall I create the Shared Package?"

### Phase 4: The Shared Logic (Packages)
*Trigger: "Apps ready"*
1.  **Scaffold Package:** Create `packages/shared`.
2.  **Config:** Initialize `package.json` and `tsconfig.json` for the shared library.
3.  **Linkage:** Add `@anki-monster/shared` dependency to `apps/web`.

### Phase 5: The Stability Check (Verification)
*Trigger: "Structure complete"*
1.  **Build:** Run `pnpm build` from root.
2.  **Test:** Run `pnpm test` (if scaffolding included tests).
3.  **Report:** "The skeleton is standing. Build Status: [Green/Red]."
