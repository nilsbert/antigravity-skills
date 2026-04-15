---
description: Phase 0.0 - Microservice Bootstrap (Skeleton → Hello World)
---

# Workflow: Microservice Bootstrap (`/workflow-bootstrap`)

> [!IMPORTANT]
> **This workflow brings a skeleton microservice to "Hello World" state.**
> A service is NOT considered "active" until it passes the Bootstrap Gate.
> **Adhere to [Global Rules](../rules/global-rules.md).**

**Persona Requirement:** Angie (Backend Lead) + Gene (DevOps)

---

## Step 1: Infrastructure Scaffold (Gene)

For the target microservice, verify or create these mandatory files:

- [ ] **`main.py`**: FastAPI entry point with `/health` endpoint.
- [ ] **`requirements.txt`**: Minimal deps (pinned versions, no duplicates).
- [ ] **`Dockerfile`**: Production-ready with `PYTHONPATH=/app`.
- [ ] **`.env.example`**: Template with DATABASE_URL + PORT.
- [ ] **`compose.yml`**: Standalone Docker Compose (MS + MSSQL).
- [ ] **`.gitignore`**: Standard Python ignores.

### Minimum `main.py` Template:
```python
import os, uvicorn, logging
from fastapi import FastAPI
from contextlib import asynccontextmanager
from core.database import init_db

logging.basicConfig(level=logging.INFO)

@asynccontextmanager
async def lifespan(app: FastAPI):
    await init_db()
    yield

app = FastAPI(title="<SERVICE_NAME> Microservice", lifespan=lifespan)

@app.get("/health")
def health():
    return {"status": "ok", "service": "<service_name>"}

if __name__ == "__main__":
    uvicorn.run(app, host="0.0.0.0", port=int(os.getenv("PORT", "<PORT>")))
```

### Minimum `requirements.txt`:
```
fastapi==0.109.2
uvicorn==0.27.1
sqlalchemy==2.0.27
aiosqlite==0.19.0
python-dotenv==1.0.1
httpx==0.26.0
```

> [!WARNING]
> **No duplicate entries allowed.** Run `sort -u requirements.txt -o requirements.txt` after editing.

---

## Step 2: Database Layer (Angie)

Create `core/database.py` following the standardized pattern:

```python
import os
from sqlalchemy.ext.asyncio import create_async_engine, AsyncSession, async_sessionmaker
from sqlalchemy.orm import DeclarativeBase

DATABASE_URL = os.getenv("DATABASE_URL", "sqlite+aiosqlite:///./<service_name>.db")
engine = create_async_engine(DATABASE_URL)
SessionLocal = async_sessionmaker(autocommit=False, autoflush=False, bind=engine, class_=AsyncSession)

class Base(DeclarativeBase):
    pass

async def get_db():
    async with SessionLocal() as session:
        yield session

async def init_db():
    async with engine.begin() as conn:
        await conn.run_sync(Base.metadata.create_all)
```

---

## Step 3: Verification (Gene)

// turbo-all

1. **Local Mode:**
   ```bash
   cd <service> && PYTHONPATH=. python main.py
   curl http://localhost:<PORT>/health
   ```
   ✅ Must return `{"status": "ok"}`.

2. **Docker Mode:**
   ```bash
   cd <service> && docker compose up --build
   curl http://localhost:<PORT>/health
   ```
   ✅ Must return `{"status": "ok"}` after MSSQL healthcheck passes.

---

## Step 4: Gate — Bootstrap Complete

- [ ] `/health` responds in Local mode (SQLite)
- [ ] `/health` responds in Docker mode (MSSQL)
- [ ] All 7 documentation files present (README, DOMAIN, API, CONTRACTS, .env.example, compose.yml, docs/STANDALONE.md)
- [ ] `requirements.txt` has zero duplicate entries
- [ ] Port matches root `compose.yml` allocation

**🛑 STOP:** Service cannot be used in `/workflow-implement-*` until this gate passes.

---
*"A microservice that can't say Hello World has no right to exist." — Martin*
