# Workflow: Local Testing Suite

> [!IMPORTANT]
> **Adhere to [Global Rules](../global-rules.md).**
> Run this workflow before pushing ANY code to the remote.

This workflow defines the standard for running tests locally to ensure quality before CI/CD.

## 1. Test Setup
- **Action:** Ensure your local environment is up to date.
- **Command:** `docker-compose up -d tender-backend tender-mssql` (if using Docker) or ensure local venv is active.

## 2. Unit & Integration Tests (Backend)
- **Scope:** All unit tests in `backend/tests`.
- **Command:** `pytest backend/tests`
- **Criteria:** All tests must pass. 100% success rate.
- **Coverage:** `pytest --cov=backend/domains backend/tests` (Target: >80%)

## 3. BDD / Feature Tests
- **Scope:** Gherkin scenarios for the feature.
- **Action:** Run the specific BDD test file for your feature.
- **Command:** `pytest backend/tests/bdd/test_[feature].py`
- **Criteria:** All scenarios must pass.

## 4. Frontend Verification (Optional for Backend-only)
- **Action:** If frontend changes were made, run linting/build.
- **Command:** `cd frontend && npm run lint && npm run build`

## 5. Report
- **Action:** Log any failures in the `task.md`.
- **Status:** Only proceed if ALL steps are GREEN.
