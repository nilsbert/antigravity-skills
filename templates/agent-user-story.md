# Agent User Story: [Title]

## 1. Context (Load This First)
*Instructions for the Agent: Run `view_file` on these paths before doing anything else.*
- **Core Feature:** [Path to Feature Spec, e.g. `docs/features/feat-001...`]
- **Design Spec:** [Path to UI Spec, e.g. `docs/ui/components/...`]
- **Tech Stack:** `package.json`

## 2. The Goal
**As a** [Role]
**I want** [Action]
**So that** [Benefit]

## 3. BDD Scenarios (The Behavior)
*Implement these exact scenarios in the test suite.*

### Happy Path (Success)
*The ideal user flow.*
```gherkin
Given [Context]
When [Action]
Then [Expected Result]
```

### Problem Path (Business Logic Rejection)
*User mistakes or validation errors.*
```gherkin
Given [Context]
When [Invalid Action]
Then [Warning/Error Message]
```

### Error Path (System Failure)
*Technical failures (Network, Crash).*
```gherkin
Given [System is Offline/Down]
When [Action]
Then [Graceful degradation / Retry button]
```

## 4. Specifications (The "Contract")
### Rules & Constraints (DO NOT BREAK)
- [ ] Must use `[Library Name]` for [Functionality].
- [ ] Must NOT introduce new dependencies without permission.
- [ ] Must follow the Domain Model defined in `docs/domain/glossary.md`.

### Data Model Changes
```typescript
// Add new interfaces or DB schema changes here
interface AgentOutput {
  success: boolean;
}
```

## 5. Step-by-Step Implementation Plan (Agent Instructions)
*Follow these steps sequentially. Do not skip.*

1.  **Scaffold Files:** Create `src/features/[name]/[Component].tsx`.
2.  **Implement Logic:** Write the core logic in `...hook.ts` or `...store.ts`.
3.  **Build UI:** Implement the JSX structure using Tailwind classes from `index.css`.
4.  **Wire Up:** Connect the Logic to the UI.

## 6. Verification (Definition of Done)
*Run these commands to verify your work.*

- **Automated Check:** `npm test src/features/[name]`
- **Visual Check:**
    1.  Start app: `npm run dev`
    2.  Navigate to: `http://localhost:5173/[route]`
    3.  Verify that [Specific Element] is visible.
