---
name: hm-init
description: Start a new project with the best tools, structure, and practices. World-class from the first commit.
license: MIT
compatibility: codex
metadata:
  workflow: development
---

## What I Do

You are now in **init mode**. A new project is starting. Your job is to ensure it starts right.

The first commit defines the standard. A world-class project doesn't become world-class later. It starts world-class.

## Your Work

When the founder describes what they want to build, you:

### 1. Evaluate and Choose the Best Stack

Not the popular one. Not the default one. The best for THIS specific project. Use the decision framework:

| Criteria | Weight | Question |
|---|---|---|
| **Fit for problem** | CRITICAL | Does this tool solve the core problem better than alternatives? |
| **Performance** | HIGH | Latency, throughput, cold starts — does it meet project requirements? |
| **Production cost** | HIGH | API calls, hosting, bandwidth — how much does it cost at scale? |
| **Maturity** | MEDIUM | Docs, community, edge cases resolved? Or bleeding-edge with traps? |
| **Ecosystem** | MEDIUM | Libraries, integrations, tooling — does it solve or will you reinvent? |
| **DX (Developer Experience)** | MEDIUM | Iteration speed, debugging, deploy — is the day-to-day fluid? |
| **Hiring pool** | LOW* | If the project will have a team, is there people who know this? |

*Hiring pool is low because Higher Mind projects are builder-first. But counts if scaling team.

**Justify each choice in one sentence.** If two options are close, explain why one wins.

**Anti-patterns of choice:**
- "Everyone uses it" is not a reason
- "It's what I know" is not a reason (unless deadline justifies)
- "We might need it someday" is not a reason to add a dependency

### 2. Define Agent-First Architecture (When Applicable)

If the project has AI/agent component:
- **Agent-first**: the agent executes, the UI provides visibility and override
- **Chat-first**: the main interface is conversation, not forms
- Before creating UI for something, ask: "Can't the agent do this via conversation?"
- Dashboards exist for visibility, not for main input

If the project is purely frontend/tool, skip this step.

### 3. Structure the Project

- Folder structure that makes architecture visible
- Clear and respected boundaries between modules
- Consistent naming conventions
- A senior engineer would understand the project in 10 minutes

### 4. Configure Quality from Day One

- TypeScript strict mode (if applicable) / complete type hints (Python)
- Linting and formatting with opinionated config
- Test framework ready to use
- Environment management (.env with .env.example)
- Git hooks if appropriate

### 5. Set Up Local Infrastructure

- **Docker Compose** as standard for local dev (database, cache, services)
- Documented and non-conflicting ports with other projects
- Named volumes (data is sacred — never lose data)
- Health checks on services
- Setup scripts (one command to bring everything up)
- Automatic migrations on boot

### 6. Build Code Foundation

- Auth (if the project needs it)
- Database schema with migrations
- API structure (routes, middleware, error handling)
- Deploy config (if target is known)

### 7. Establish Cost Constraints

- If using external APIs (LLM, etc): define context limits, avoid unnecessary calls
- If has background jobs: define justified frequency
- Document estimated cost per main operation
- Cost x performance is a design constraint, not future optimization

### 8. Document Decisions

Create ARCHITECTURE.md explaining:
- Chosen stack and why (each tool)
- Architectural decisions and trade-offs
- How to run the project
- Ports and services
- Folder structure

## Standards

- Every dependency needs to justify its existence
- Folder structure must make architecture visible
- No placeholder code. No TODO comments on day one. Everything that exists works.
- Project must run successfully after init
- Data is sacred from the first docker-compose.yml

## Output

After init, the founder should be able to:
1. Understand each technical choice and why
2. Run the project with one command
3. Start building features without setup friction
4. Know how much it will cost to run in production

## Rules

- Don't ask "which framework do you want?" — recommend the best and explain why
- Don't scaffold empty files. Every file that exists has real content.
- Don't use deprecated or unmaintained packages
- Don't configure what isn't needed yet. Scope for what the project needs now.
- If the founder's description is vague, ask ONE clarifying question before proceeding
- Never expose secrets or unnecessary ports
- If the project will have AI agent, architect agent-first from the start — not "add agent later"
