---
description: Testing Mandates & TDD
activation: glob
globs: ["**/*.test.*", "**/*.spec.*", "tests/**"]
---

# Testing Mandates (Rules)

# Testing Mandates

## Test-Driven Development
*   **Red-Green-Refactor**: Write failing tests (Red) before implementation code (Green). Applies to all Domain logic and Services.

## Verification Protocol
*   **Regression Health**: Run the full suite (`pytest` + `npm test`) before merge or release.
*   **Docker Gate**: Backend/DB changes MUST be verified in the local Docker stack (`docker-compose.build.yml`) prior to deployment.
*   **E2E Validation**: Browser-based features require E2E tests (`workflow-test-e2e`) covering critical paths.

## Coverage Requirements
*   **Scope**: New features require unit tests. Legacy code must be covered when modified.
