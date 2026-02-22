---
description: The high-level lifecycle for the project from Setup to MVP and Kanban.
---

# 🌀 Project Lifecycle Workflow

This is the "Source of Truth" for the project's operational phases. **Amy** (The Safety Guardian) facilitates the transitions between these phases.

## Phase 1: Environment Setup
**Persona:** Gene (Release Manager)
- [ ] Initialize Repository and Tooling.
- [ ] Create `docs/admin/toolchain-manifest.md`.
- [ ] Setup CI/CD and Branch protection.

## Phase 2: MVP Development (The "Walking Skeleton")
*Goal: Complete all Slice 1 Features.*
For each feature:
1.  **Vision Alignment (Roman)**: Verify Story/Persona impact.
2.  **Architecture (Martin)**: Define NFRs, ADRs, Context Map, and update the Glossary.
3.  **Refinement (Jeff + Angie + Lisa)**: "Three Amigos" session to break feature into implementation-ready User Stories.
4.  **Implementation (Angie)**: Code logic using TDD and "Duo Mode" with Lisa.
5.  **Quality Assurance (Lisa)**: Final validation and "Red Scenario" verification.
6.  **Handover (User)**: Present feature for final approval and Close Issue.
7.  **Retro (Diana)**: Mini-Retrospective (PDCA) to optimize the system for the next feature.

## Phase 3: MVP Wrap-Up & Launch
**Personas:** Gene & Roman
- [ ] **Full Demo**: Showcase all Slice 1 features in a single flow.
- [ ] **Release Docs**: Create Release Notes, mandatory organizational documents, and finish `walkthrough.md`.
- [ ] **Official Release**: Merge all features and tag the release version.

## Phase 4: Post-MVP Maintenance (Kanban)
**Persona:** Amy
- [ ] Shift from "Phase-Gate" to a pure **Kanban System**.
- [ ] Enforce WIP Limits (Max 1 Implementation at a time).
- [ ] Continuous backlog grooming with Roman and Jeff.
- [ ] Regular System Health Checks with Diana.
