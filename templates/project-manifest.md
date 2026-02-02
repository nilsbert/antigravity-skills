# 🛠️ Project Toolchain Manifest

> **Owner:** Gene (Release Manager)
> **Last Updated:** YYYY-MM-DD
> **Status:** [Active]

---

## 1. Core Repositories (Version Control)
* **Provider:** GitHub
* **Repository URL:** [Insert Link]
* **Branch Strategy:** [e.g., GitFlow or Trunk-Based]
* **Protection Rules:** Require 1 Reviewer, Passing CI.

---

## 2. Work Management (The "What")
* **System:** [e.g., Jira Cloud]
* **Project Key:** `[KEY]`
* **Backlog URL:** [Insert Link]
* **Integration:** ✅ GitHub Smart Commits enabled.

---

## 3. Knowledge Base (The "How")
* **System:** [e.g., Confluence / GitHub Wiki]
* **Home Page:** [Insert Link]
* **ADR Location:** `/docs/adr` (In Repo)

---

## 4. Communication & ChatOps
* **System:** [e.g., Slack]
* **Channel:** `#project-antigravity`
* **Alerts Configured:**
    * [ ] CI Failure -> Channel
    * [ ] PR Created -> Channel

---

## 5. Observability & CI/CD
* **Pipeline:** GitHub Actions
* **Error Tracking:** [e.g., Sentry]
* **Uptime Monitor:** [e.g., UptimeRobot]

---

## 6. Access Control (Who has keys?)
* **Admin:** Gene, [User Name]
* **Developers:** [List Teams]
* **Onboarding:** "Add new dev to [GitHub Team] to grant access."

---

## 7. Secrets Management (Security)
* **Provider:** [e.g. GitHub Secrets, 1Password, Vault]
* **Rotation Policy:** 90 Days.
* **Rule:** NEVER commit `.env` files.