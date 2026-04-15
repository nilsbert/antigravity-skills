---
description: Phase 9.1 - Microservice Sovereignty Audit (Periodic Health Check)
---

# Workflow: Sovereignty Audit (`/workflow-audit-sovereignty`)

> [!CAUTION]
> **This audit MUST pass before any sprint review or release.**
> It validates that all microservices maintain sovereign independence as defined in `ARCHITECTURE_STANDARDS.md`.

**Persona Requirement:** Martin (Lead Architect)
**Frequency:** Run before every Sprint Review, or after any multi-service change.

---

## Step 1: File Completeness Scan

// turbo

For EVERY microservice directory, verify these files exist:

```bash
for ms in crawling enriching rating qualification dispatching dashboard ai iam; do
  echo "=== $ms ===" 
  for f in main.py Dockerfile requirements.txt .env.example compose.yml README.md DOMAIN.md API.md CONTRACTS.md; do
    [ -f "$ms/$f" ] && echo "  ✅ $f" || echo "  ❌ $f MISSING"
  done
done
```

**🛑 STOP:** If any active service is missing files, trigger `/workflow-bootstrap` before proceeding.

---

## Step 2: Port Consistency Check

// turbo

Validate that port allocations are consistent across all configuration layers:

```bash
echo "=== Port Allocation Audit ==="
# Check root compose.yml
grep -E "^\s+- \"[0-9]+:" compose.yml

# Check per-MS Dockerfiles
for ms in crawling enriching rating qualification dispatching dashboard ai iam; do
  if [ -f "$ms/Dockerfile" ]; then
    echo "$ms Dockerfile:" $(grep "EXPOSE\|--port" "$ms/Dockerfile")
  fi
done

# Check per-MS compose.yml
for ms in crawling enriching rating qualification dispatching dashboard ai iam; do
  if [ -f "$ms/compose.yml" ]; then
    echo "$ms compose:" $(grep -E "^\s+- \"[0-9]+:" "$ms/compose.yml" | head -1)
  fi
done
```

**Expected Port Registry:**

| Service | App Port | Standalone MSSQL |
| :--- | :--- | :--- |
| Crawling | 8001 | 1433 |
| Enriching | 8002 | 1434 |
| IAM | 8003 | 1439 |
| AI | 8004 | 1438 |
| Dispatching | 8005 | 1437 |
| Dashboard | 8009 | *(none)* |
| Rating | 8012 | 1435 |
| Qualification | 8013 | 1436 |

**🛑 STOP:** If any port mismatch is found, fix it immediately. Port conflicts cause silent failures in full-stack mode.

---

## Step 3: Dependency Hygiene

// turbo

Check for duplicate entries and unpinned versions:

```bash
for ms in crawling enriching rating qualification dispatching dashboard ai iam; do
  if [ -f "$ms/requirements.txt" ]; then
    dupes=$(sort "$ms/requirements.txt" | uniq -d | grep -v "^$")
    if [ -n "$dupes" ]; then
      echo "❌ $ms has DUPLICATE dependencies: $dupes"
    else
      echo "✅ $ms requirements clean"
    fi
  fi
done
```

**Rule:** Fix duplicates with `sort -u requirements.txt -o requirements.txt`.

---

## Step 4: API Documentation Alignment

For each service with an `API.md`, verify:

1. **Planned vs Implemented:** Are endpoints marked as `[PLANNED]` if the code doesn't exist yet?
2. **Route Match:** Do the documented routes match the actual `api/routes.py` or `api/__init__.py`?
3. **Port Match:** Does the documented port in `API.md` match the actual port in `main.py`?

```bash
for ms in crawling enriching rating qualification dispatching dashboard ai iam; do
  echo "=== $ms API Routes ==="
  # Actual routes in code
  grep -r "@app\.\|@router\." "$ms/api/" 2>/dev/null | grep -v node_modules | grep -v __pycache__
  echo "---"
done
```

**Action:** If a documented endpoint has no corresponding route in code, add `> ⚠️ **Status: PLANNED**` to the API.md entry.

---

## Step 5: Contract Coherence

For each `CONTRACTS.md`, cross-reference:

1. Does the **Consumer** actually call the documented endpoint?
2. Does the **Provider** actually return the documented fields?
3. Are there undocumented inter-service calls?

```bash
# Find all inter-service URLs in code
grep -r "localhost:80\|CRAWLING_URL\|ENRICHING_URL\|RATING_URL\|AI_URL\|IAM_URL\|DISPATCHING_URL" \
  --include="*.py" --include="*.env*" \
  crawling/ enriching/ rating/ qualification/ dispatching/ dashboard/ ai/ iam/ 2>/dev/null | \
  grep -v node_modules | grep -v .venv
```

---

## Step 6: Gate — Sovereignty Confirmed

Martin produces a compliance summary:

| Check | Result |
| :--- | :--- |
| All files present | ✅/❌ |
| Ports consistent | ✅/❌ |
| Dependencies clean | ✅/❌ |
| API docs aligned | ✅/❌ |
| Contracts coherent | ✅/❌ |

**🛑 STOP:** If any check fails, the sprint cannot be reviewed until resolved.

---
*"Sovereignty is not optional. If we can't audit it, we can't trust it." — Martin*
