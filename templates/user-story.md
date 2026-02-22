---
title: 'Story: [Short Action-Oriented Name]'
parent: [Parent Feature ID, e.g., feat-001]
domain: [e.g., Study]
persona: [Name, e.g., Haruki]
---

## Story
**As a** [Specific Persona]
**I want** [Specific Action]
**So that** [Specific Benefit]

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

##  Context (Agent Instructions)
*Pre-read these files to understand the system state.*
- **Core Feature**: `docs/features/...`
- **Design Spec**: `docs/ui/...`
- **Global Rules**: `docs/admin/toolchain-manifest.md`

## Rules & Constraints (DO NOT BREAK)
- [ ] **Mobile-First**: Touch targets > 48px.
- [ ] **Local-First**: No external API calls without explicit approval.
- [ ] **Strict Types**: No `any` types.

## 🏗️ Data Model & Schema
*Example of expected types or schema changes.*
```typescript
interface Example {
  id: string;
}
```

## BDD Scenarios

### 1. Happy Path: [Name]
**Given** [Context]
**When** [Action]
**Then** [Outcome]

### 2. Edge Case: [Name]
**Given** [Context]
**When** [Action]
**Then** [Outcome]

## Quality Assurance (Lisa)
### Quality Scenarios (NFRs)
*Format: Source -> Stimulus -> Environment -> Response -> Measure*

**Scenario 1: [Attribute, e.g. Usability]**
- **Stimulus**: [e.g. User taps button]
- **Environment**: [e.g. Mobile / One-handed]
- **Response**: [e.g. Button is reachable]
- **Measure**: [e.g. Target > 48px]

### Exploratory Charters (Q3)
- [ ] **Charter:** Explore [Flow] with [Persona] to find [Risk].
- [ ] **Clarified Rules:** [From Three Amigos]

### Test Strategy (Isolation)
- **Mock:** [Service/Component to mock] -> [Generic behavior]
- **Dummy:** [Data used]
