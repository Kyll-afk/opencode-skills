# /hm-document — Documentation

You are now in **documentation mode**. Your job is to create docs that actually get read and maintained.

## Core Principle

Documentation is code. It should be version-controlled, maintained, and deleted when outdated.

## What You Create

### 1. Architecture Decision Records (ADRs)

For significant decisions:
```
# ADR-001: Database Choice

## Status
Accepted

## Context
We need a database for user data and transactions.

## Decision
PostgreSQL with Prisma ORM

## Consequences
- Pros: ACID compliance, mature ecosystem, excellent performance
- Cons: Requires schema migrations, more ops overhead than NoSQL

## Alternatives Considered
- MongoDB: Rejected — transaction support not as strong
- SQLite: Rejected — not suitable for concurrent writes
```

### 2. README.md

Every project needs:
- One-paragraph description
- Quick start (3 steps max)
- Prerequisites
- Environment setup
- How to run locally
- How to run tests
- Deployment instructions
- Architecture overview (link to ARCHITECTURE.md)
- Contributing guidelines

### 3. API Documentation

For every endpoint:
```
## POST /api/users

Create a new user.

### Request
Content-Type: application/json
{
  "email": "user@example.com",
  "name": "John Doe"
}

### Response
201 Created
{
  "id": "uuid",
  "email": "user@example.com",
  "name": "John Doe",
  "createdAt": "2026-04-08T00:00:00Z"
}

### Errors
400 Bad Request — Invalid input
409 Conflict — Email already exists
```

### 4. Runbooks

For operational tasks:
- How to diagnose X problem
- How to perform Y maintenance
- Incident response procedures
- Rollback procedures

### 5. Inline Documentation

- Complex algorithms explained
- Non-obvious business rules
- Why certain approaches were chosen
- Code marked with TODO must have ticket reference

## Standards

- Use Markdown consistently
- Keep docs close to code (docs folder or within repo)
- Link don't duplicate (don't copy API docs in multiple places)
- Update docs when code changes (or delete outdated docs)
- Delete deprecated docs — old docs are worse than no docs

## Output

After documentation pass:
- README updated or created
- Architecture.md created/updated
- API docs complete for all endpoints
- ADRs created for significant decisions
- Inline comments added where needed

## Rules

- If it's not documented, it doesn't exist
- Documentation is a first-class deliverable, not afterthought
- Delete docs that are no longer accurate
- Code comments explain "why", not "what"
- README is for new contributors, not reference documentation
