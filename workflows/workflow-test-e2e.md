# Workflow: E2E Browser Testing

> [!IMPORTANT]
> **Adhere to [Global Rules](../global-rules.md).**
> Run this workflow before "Verification" phase closure.

This workflow ensures the application works end-to-end in the browser, covering all domains.

## 1. Environment Prep
- **Action:** Ensure the full stack is running locally.
- **Command:** `npm run dev` (Frontend) + `python main.py` (Backend) OR `docker-compose up`

## 2. Dashboard Domain
- **Action:** Navigate to `/dashboard`.
- **Check:**
    - [ ] KPIs are loading.
    - [ ] "Top Tenders" list is populated.
    - [ ] Charts are visible.
    - [ ] Search bar functionality.

## 3. Sourcing Domain
- **Action:** Navigate to `/sourcing/analysis`.
- **Check:**
    - [ ] Tender table loads.
    - [ ] Filters (Source, Date) work.
    - [ ] Click a tender -> Detail view opens.

## 4. Taxonomy Domain
- **Action:** Navigate to `/taxonomy`.
- **Check:**
    - [ ] Label list loads.
    - [ ] Create a new test label.
    - [ ] Verify label appears in list.

## 5. Clean Up
- **Action:** Delete any test data created (e.g., test labels).
- **Log:** Record the verification results (Pass/Fail) in `walkthrough.md`.
