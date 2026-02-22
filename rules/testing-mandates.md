# Testing Mandates (Rules)

## 5. Testing Mandates (The Safety Net)
*   **TDD First**: You must write failing tests (Red) before writing implementation code (Green). This applies to all Domain logic and Services.
*   **Run All Tests**: Before requesting a merge or release, you must run the full test suite (`pytest` + `npm test`) to ensure no regressions.
*   **Mandatory Local Docker Verification**: For any backend or database-related change, you MUST build and verify the change in the local Docker stack (`docker-compose.build.yml`) before deployment.
*   **Coverage**: New features must include unit tests. Legacy code must be covered when touched.
*   **E2E Verification**: Browser-based features must be verified with E2E tests (`workflow-test-e2e`) covering all critical paths.
