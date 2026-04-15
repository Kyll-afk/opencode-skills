---
name: hm-deploy
description: Validate infrastructure, containers, reproducibility, and deploy security. Ready to leave local.
compatibility: codex
---

## What I Do

You are now in **deploy mode**. Your job is to ensure the project is ready to leave local and go to the world. Or that the local environment is healthy and reproducible.

## Core Principle

Deploy is not the last step. It's a layer of engineering. If the deploy is fragile, the product is fragile. If raising the environment depends on tribal knowledge, the project isn't ready.

## When to Use

- Before going to production for the first time
- When the local environment stopped working
- When infrastructure changed (new service, new port, new variable)
- To validate that anyone can bring up the project from scratch
- After significant refactoring

## What You Validate

### 1. Docker & Containers

**Startup:**
- Does `docker compose up` start all services without error?
- Do all containers stay healthy? (not just running — healthy)
- Is dependency order correct? (database before API, etc)
- Do container logs show clean startup?

**Rebuild:**
- Are code changes reflected after `docker compose build <service> && docker compose up -d <service>`?
- Does the Dockerfile use multi-stage build when appropriate?
- Is cache of layers optimized? (deps before code copy)
- Does the final image have unnecessary dev tools?

**Sacred Data:**
- Are volumes named (never anonymous)?
- Does `docker compose down` (without -v) preserve all data?
- Does database data survive container rebuild?
- If there's production data locally, is it protected against `down -v`?

### 2. Environment & Configuration

- Does `.env.example` exist and have ALL necessary variables?
- Are no secrets hardcoded in code or docker-compose.yml?
- Are sensitive variables marked as such in .env.example?
- Do default values make sense for local dev?
- Are ports documented and not colliding with other projects?

**Port Checklist (Higher Mind projects):**
| Project | API | Web | Postgres | Redis |
|---|---|---|---|---|
| higher-mind-os | 8000 | 3000 | 5432 | 6379 |
| scout | 8001 | 3000 | 5433 | 6381 |
| hm-finance | 8003 | 3001 | 5434 | — |

If the project is new, choose ports that don't collide.

### 3. Database & Migrations

- Do migrations run automatically on container boot?
- Are migrations in order with no gaps?
- Is no migration destructive without being reversible?
- Does the current schema reflect all applied migrations?
- Does app-to-database connection work right after startup?

### 4. Health & Monitoring

- Does health check endpoint exist? (`/health` or `/api/health`)
- Does health check return status of dependent services (database, cache, etc)?
- Are logs structured and useful (not too verbose)?
- Are errors logged with enough context to debug?

### 5. Reproducibility

The ultimate test: **clean clone**.
1. Clone the repo
2. Copy `.env.example` to `.env`
3. Run `docker compose up`
4. Does the project work?

If any extra step is needed, documentation or automation is missing.

### 6. Deploy Security

- No unnecessary port exposed
- No debug service active in production configuration
- CORS configured correctly (not `*` in production)
- HTTPS configured (if production)
- Secrets not in build logs
- `.env` is in `.gitignore`
- `.dockerignore` excludes node_modules, .env, .git, etc.

### 7. Scripts & DX

- Does a README or ARCHITECTURE.md exist with setup instructions?
- Is setup one command (or at most two)?
- Are development scripts documented? (how to run tests, how to rebuild, etc)
- Do Makefile or convenience scripts exist if needed?

## Output Format

```
CONTAINERS
[Service]: healthy/unhealthy (details)
Build: OK/FAILED (details)
Data: protected/at risk (details)

ENVIRONMENT
.env.example: complete/incomplete (missing variables)
Secrets: secure/exposed (details)
Ports: OK/conflict (details)

DATABASE
Migrations: OK/failed (details)
Connection: OK/failed
Data persistent: yes/no

HEALTH
Endpoint: exists/doesn't exist
Services: all healthy/X unhealthy

REPRODUCIBILITY
Clean clone: works/fails at step X

SECURITY
[Check]: OK/issue (details)

VERDICT
Ready to deploy / X issues to fix first
```

## Rules

- Never assume "it works on my machine" is sufficient
- Data is sacred. If validation shows risk of data loss, it's CRITICAL.
- Every finding has a specific fix. Not just "configure better."
- If the project doesn't start from scratch with one command, it's a finding.
- If a secret is exposed, it's CRITICAL. No exceptions.
- Test the clean clone mentally (or for real). Each manual step is technical debt.
- The standard: a new engineer joins the team on Monday and has the project running before lunch.
