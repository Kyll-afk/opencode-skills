# highermind-code-skills

**Before there was a company, there was a mind that decided to build.**

Ten cognitive execution modes for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Built on the Higher Mind philosophy: companies are extensions of the founder's internal architecture. If the code is mediocre, the pattern was mediocre. If the software is world-class, the mind behind it demanded world-class.

Strategic direction skills (`/hm-align`, `/hm-sequoia`) are in [highermind-business-skills](https://github.com/rodrigohighermind/highermind-business-skills).

This is not a prompt pack. It's a pattern, coded once, so you never have to repeat yourself.

---

## The Problem

Every time you open Claude Code, you start from scratch. The agent doesn't know your bar. Doesn't know that "good enough" isn't enough. Doesn't know you think in decades, not sprints. So you repeat:

- "Make it world-class."
- "Check security. All layers."
- "The design needs to be Apple-level."
- "Run tests. Cover everything."

You say the same things, with different words, every time. The output quality depends on how well you translate your pattern in that specific moment.

highermind-code-skills solves this. You translate your pattern once. Then it's always there.

---

## How It Works

Two layers:

**CLAUDE.md** — your identity. Always active. Every project, every session. The agent knows who you are, what your bar is, and that mediocrity is not an option. You never have to explain this again.

**Skills** — cognitive modes you activate when needed. Each puts the agent in a specific mindset with a specific job.

| Skill | When | What It Does |
| --- | --- | --- |
| `/hm-init` | Project start | Best tools, best structure, best practices. World-class from the first file. |
| `/hm-architect` | System design | Patterns, data models, API contracts, scaling strategy. |
| `/hm-engineer` | Validate code | Architecture, security, performance, cost, quality. All layers. Production-grade. |
| `/hm-designer` | Validate interface | Where software is going, not where it was. Sophistication, delight, beauty. |
| `/hm-qa` | Test everything | Run, break, verify it works. Edge cases, flows, agent, infra, real usage. |
| `/hm-deploy` | Validate deploy | Containers, migrations, reproducibility, security. Ready to leave local. |
| `/hm-security` | Security audit | Vulnerabilities, compliance, data protection, attack prevention. |
| `/hm-refactor` | Code improvement | Structure, naming, architecture, technical debt. |
| `/hm-document` | Documentation | ADRs, README, API docs, inline comments. |
| `/hm-optimize` | Performance | Profiling, bottlenecks, caching, database, frontend. |

> Direction skills (`/hm-align`, `/hm-sequoia`) are in [highermind-business-skills](https://github.com/rodrigohighermind/highermind-business-skills).

---

## The Flow

```
/hm-init          you start a new project. it starts right.
[build]           you direct, the agent executes.
/hm-architect     you design the system architecture.
/hm-designer      you validate the interface is at the bar.
/hm-engineer      you validate the code is at the bar.
/hm-qa            you verify it actually works.
/hm-deploy        you validate it builds, runs, and reproduces.
```

You don't need to use all of them every time. Use what the moment requires. `/hm-engineer` and `/hm-designer` can run multiple times while you iterate.

> To validate direction and strategy, use the [business skills](https://github.com/rodrigohighermind/highermind-business-skills): `/hm-align` (is this the right thing?) and `/hm-sequoia` (is it going to the future?).

---

## For Whom This Is

You build because you can't not build. You use Claude Code as your dev team. You know exactly what world-class looks like, but you're tired of translating this standard into words every session.

This encodes your standard once. The agent operates at your level from the first command.

---

## `/hm-init`

**Project start.**

You open a new project. Type `/hm-init` and describe what you want to build. The agent doesn't just scaffold. It makes decisions:

- The best framework for this type of project (with weighted decision framework)
- The best database, ORM, auth solution
- The best folder structure and architecture patterns
- Agent-first as default architectural (when applicable)
- Local infrastructure with Docker Compose from day 1
- Cost constraints as part of design
- Test setup from day one
- Environment management
- Code formatting and linting

Each choice is justified against explicit criteria: fit for problem, performance, production cost, maturity, ecosystem, DX. Nothing is default. Nothing is "we usually use this."

The standard: if a world-class engineering team looked at this project on day one, they would say "this is how you start a project."

---

## `/hm-architect`

**System design.**

You describe what needs to be built. The agent designs the system:

- System boundaries and trust boundaries
- Architecture pattern (monolith, microservices, event-driven, agent-first)
- Data layer design (database choice, schema, indexes)
- API contracts (REST/GraphQL/RPC)
- Scaling strategy (10x and 100x considerations)

The standard: the architecture should be explainable in 30 minutes to a new engineer and should scale without fundamental redesign.

---

## `/hm-engineer`

**Validate code.**

You type `/hm-engineer` and the agent audits everything. Not lint. Not style. Structure, security, cost, and resilience.

Starts with a non-negotiable senior engineer baseline (zero bare except, zero any types, zero fire-and-forget, zero hardcoded secrets). Then audits:

- **Architecture**: responsibilities, boundaries, data flow, agent loops
- **Security**: injection, auth bypass, secrets, trust boundaries, CSRF, exposed ports
- **Performance**: N+1 queries, indexes, re-renders, bundle size, caching, parallel I/O
- **Cost x Performance**: justified API calls, minimum context in LLMs, conscious token usage
- **Sacred data**: no destructive operation without confirmation, named volumes, safe migrations
- **Infrastructure**: Docker rebuild vs restart, health checks, ports, migrations
- **Resilience**: error handling, retry logic, failure modes, race conditions
- **Quality**: meaningful tests, naming, abstractions, dependencies
- **Scale**: bottlenecks at 10x and 100x

The standard: if you were selling this software and the buyer hired the best engineers in the world to audit the codebase, they wouldn't find anything to complain about.

---

## `/hm-designer`

**Validate interface.**

Not "make it pretty." It's vision.

Software design is moving. What looked modern in 2020 looks dated now. What looks modern now will look dated in 2028. `/hm-designer` doesn't validate against today's standard. It validates against where software is going.

The bar:

- **Sophistication**: every element has a reason to exist. Nothing decorative. Nothing filler.
- **Differentiation**: this interface could only belong to this product. Not a template with swapped content.
- **Experience**: using this software needs to feel like something. Not neutral. Not invisible. Intentional.
- **Delight**: moments that make someone pause and think "this is beautifully made."
- **Usability**: effortless. The user never wonders what to do.
- **Beauty**: based on the most beautiful products humanity has built. Apple. Airbnb. Linear. Stripe. Vercel.

What's rejected:
- Anything that looks like it was built from a template
- Anything that could belong to any product
- Anything that uses light mode without considering dark mode
- Anything with default typography, default spacing, everything default
- Anything that prioritizes "ship fast" over "ship right"

The standard: show this interface to someone with taste. Not a designer. Someone with taste. This person should feel that whoever built this deeply cares about the craft.

---

## `/hm-qa`

**Test everything.**

Code that isn't tested doesn't exist. `/hm-qa` runs everything:

- Unit tests for business logic
- Integration tests for API endpoints and data flows
- End-to-end tests for critical user flows
- Edge case tests (empty states, limit values, concurrent operations)
- **Infrastructure verification** (containers start? migrations run? ports correct? data persists?)
- **Agent verification** (tool loops terminate? doesn't hallucinate tools? cost per interaction?)
- **Data integrity** (persistence between restarts, non-destructive migrations, backups)
- **Cost check** (API calls per flow, minimum context, cost per user/month)
- Mobile viewport verification
- Basic performance and accessibility tests

The agent doesn't just run tests. It thinks about what should be tested and isn't. Finds the gaps.

The standard: you would deploy this confidently on a Friday night.

---

## `/hm-deploy`

**Validate deploy and infrastructure.**

You type `/hm-deploy` and the agent validates that the project is reproducible, secure, and ready to leave local.

What it checks:

- **Docker**: containers start, stay healthy, rebuild works, data is protected
- **Environment**: .env.example complete, no secrets exposed, ports documented
- **Database**: automatic migrations, consistent schema, persistent data
- **Health**: health check endpoints, dependency monitoring
- **Reproducibility**: clean clone works with one command
- **Security**: minimum ports, correct CORS, secrets out of logs

The ultimate test: a new engineer joins the team on Monday and has the project running before lunch.

---

## `/hm-security`

**Security audit.**

You type `/hm-security` and the agent finds vulnerabilities before attackers do.

What it audits:
- Authentication & authorization (password storage, sessions, MFA)
- Data protection (encryption at rest/transit, PII handling)
- Injection attacks (SQL, XSS, command injection)
- API security (rate limiting, CORS, secrets)
- Infrastructure (ports, debug endpoints, Docker security)
- Error handling (no stack traces in production)

The standard: no critical or high vulnerabilities. Security is foundation, not feature.

---

## `/hm-refactor`

**Code improvement.**

You type `/hm-refactor` and the agent improves code quality without changing behavior.

What it improves:
- Code structure (extract functions, remove dead code, simplify conditionals)
- Naming (self-documenting variables and functions)
- Architecture (circular dependencies, module boundaries, coupling)
- Type safety (replace `any`, add missing types)
- Performance (N+1 queries, caching, data structures)

The standard: code should be easier to understand, modify, and extend after refactoring.

---

## `/hm-document`

**Documentation.**

You type `/hm-document` and the agent creates docs that actually get read and maintained.

What it creates:
- Architecture Decision Records (ADRs) for significant decisions
- README.md with quick start, prerequisites, setup
- API documentation for every endpoint
- Runbooks for operational tasks
- Inline comments for complex algorithms

The standard: if it's not documented, it doesn't exist. Documentation is a first-class deliverable.

---

## `/hm-optimize`

**Performance optimization.**

You type `/hm-optimize` and the agent makes things faster without sacrificing correctness.

What it optimizes:
- Database (N+1 queries, indexes, query analysis)
- Backend (async I/O, caching, batch operations)
- Frontend (code splitting, lazy loading, memoization)
- Infrastructure (CDN, compression, caching headers)

The standard: measure first, optimize where it matters. The 80/20 rule applies.

---

## Installation

**Requirements:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Git](https://git-scm.com/).

### Step 1: Install the skills

Open Claude Code and run:

```
git clone https://github.com/rodrigohighermind/highermind-code-skills.git ~/.claude/skills/highermind-code-skills && cd ~/.claude/skills/highermind-code-skills && chmod +x setup && ./setup
```

### Step 2: Configure CLAUDE.md

Copy the included template to `~/.claude/CLAUDE.md` and customize:

```
cp ~/.claude/skills/highermind-code-skills/CLAUDE.md.template ~/.claude/CLAUDE.md
```

Edit `~/.claude/CLAUDE.md` to add your name, your projects, and your specifics.

### What is installed

- Skill files in `~/.claude/skills/highermind-code-skills/`
- Symlinks in `~/.claude/skills/hm-init`, `~/.claude/skills/hm-engineer`, etc.
- `CLAUDE.md.template` as a starting point for your global identity file

Everything stays inside `~/.claude/`. Nothing touches your PATH or runs in background.

---

## Adding to a project (optional)

To share skills with the team in a specific repo:

```
cp -Rf ~/.claude/skills/highermind-code-skills .claude/skills/highermind-code-skills && rm -rf .claude/skills/highermind-code-skills/.git && cd .claude/skills/highermind-code-skills && ./setup
```

---

## Update

```
cd ~/.claude/skills/highermind-code-skills && git fetch origin && git reset --hard origin/main && chmod +x setup && ./setup
```

---

## Uninstall

```
for s in hm-init hm-architect hm-engineer hm-designer hm-qa hm-deploy hm-security hm-refactor hm-document hm-optimize; do rm -f ~/.claude/skills/$s; done && rm -rf ~/.claude/skills/highermind-code-skills
```

---

## Philosophy

Built on the [Higher Mind](https://highermind.com.br) philosophy:

**First the founder. Then the company. Then the world.**

The same applies to software. First the standard. Then the code. Then the product. If the standard is world-class, everything that follows will be too.

Companies are just the byproduct. Software is just the byproduct. What matters is the mind that decided to build.

---

## License

MIT

---

Created by [Rodrigo Lopes](https://github.com/rodrigohighermind), founder of [Higher Mind](https://highermind.com.br).
