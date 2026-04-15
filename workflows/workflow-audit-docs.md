---
description: Phase 9.2 - Documentation-Code Sync Validation
---

# Workflow: Doc-Code Sync (`/workflow-audit-docs`)

> [!IMPORTANT]
> **Documentation that lies is worse than no documentation.**
> This workflow ensures every documented API, port, and contract matches reality.

**Persona Requirement:** Martin (Lead Architect)
**Trigger:** After any feature implementation, before PR merge.

---

## Step 1: API.md Reality Check

For the target microservice:

1. **Extract documented endpoints** from `API.md`:
   ```bash
   grep -E "^### [0-9]+\.|^## .* Endpoints" <service>/API.md
   ```

2. **Extract actual endpoints** from code:
   ```bash
   grep -rE "@(app|router)\.(get|post|put|delete|patch)" <service>/api/ --include="*.py" | \
     grep -v __pycache__
   ```

3. **Compare:** Every documented endpoint must have a corresponding route decorator.
   - **Missing in code?** → Mark as `[PLANNED]` in API.md.
   - **Missing in docs?** → Add to API.md immediately.

---

## Step 2: Port Integrity

Verify the service's port is consistent across ALL locations:

| Location | How to Check |
| :--- | :--- |
| `main.py` | `grep "port" <service>/main.py` |
| `Dockerfile` | `grep "EXPOSE\|--port" <service>/Dockerfile` |
| `compose.yml` (local) | `grep "ports:" -A1 <service>/compose.yml` |
| `compose.yml` (root) | `grep "<service>" -A5 compose.yml` |
| `API.md` | `grep "Port:" <service>/API.md` |
| `README.md` | `grep "Port:" <service>/README.md` |
| `.env.example` | `grep "PORT=" <service>/.env.example` |

**Rule:** All 7 locations must show the SAME port number.

---

## Step 3: Requirements Hygiene

```bash
# Check for duplicates
sort <service>/requirements.txt | uniq -d

# Check for unpinned versions (production risk)
grep -v "==" <service>/requirements.txt | grep -v "^#" | grep -v "^$"
```

**Rules:**
- Zero duplicates allowed.
- All production dependencies SHOULD be pinned (`==`). Dev dependencies (`pytest`, etc.) may use `>=`.

---

## Step 4: CONTRACTS.md Freshness

1. Check if `CONTRACTS.md` lists all actual consumers:
   ```bash
   # Who actually calls this service?
   grep -r "<SERVICE_URL>\|<SERVICE_PORT>" \
     --include="*.py" --include="*.env*" \
     crawling/ enriching/ rating/ qualification/ dispatching/ dashboard/ ai/ iam/ 2>/dev/null | \
     grep -v node_modules | grep -v .venv
   ```

2. Every discovered consumer MUST appear in the service's `CONTRACTS.md`.

---

## Step 5: Fix & Commit

If any discrepancy is found:
1. Fix the documentation (not the code — docs follow code, never the reverse).
2. Commit with prefix: `docs: sync API.md/CONTRACTS.md with implementation`
3. Push via `/workflow-push`.

**🛑 GATE:** PR cannot be merged if doc-code sync fails.

---
*"The scariest documentation is the one that looks correct but isn't." — Martin*
