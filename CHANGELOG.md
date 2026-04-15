# Changelog

All notable changes to this project will be documented here.

Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

---

## [3.0.0] — 2026-04-15

Complete evolution with multi-AI tool support and new skills.

### Added

#### New skill: `/hm-htmlfirst`
- Native browser APIs replacing JavaScript libraries
- Popover API for tooltips/dropdowns
- `<dialog>` for modals
- Container Queries for responsive components
- View Transition API for page transitions
- Scroll-Driven Animations
- Discrete property animations

#### New skill: `/hm-animator`
- SVG animation expert with icon libraries or pure CSS
- Line drawing, morphing, pulse effects
- Scroll sync with animation-timeline
- Multi-phase logo reveals
- Modal/dialog animations
- GPU-friendly properties (transform, opacity)

#### Multi-tool support
- `main` branch: OpenCode skills
- `claude` branch: Claude Code skills with `allowed-tools`, `disable-model-invocation`
- `cursor` branch: Cursor skills with Agent Skills standard
- `codex` branch: Codex skills with progressive disclosure

### Updated

- All skills now have individual README.md files
- Unified frontmatter across all tools
- Clean git history with proper commit messages

---

## [2.0.0] — 2026-04-03

Complete evolution of skills based on real-world learnings from 5+ projects.

### Added

#### New skill: `/hm-deploy`
- Complete infrastructure validation, containers, and reproducibility
- Docker checklist (upload, rebuild, sacred data)
- Environment and secrets validation
- Database and migrations checklist
- Health checks and monitoring
- Reproducibility test (clean clone)
- Deploy security (ports, CORS, HTTPS, secrets)

#### `/hm-init` — Stack decision framework
- Weighted criteria table for stack evaluation (fit, performance, cost, maturity, ecosystem, DX, hiring)
- Explicit anti-patterns for choices
- Agent-first architecture as default (when applicable)
- Local infrastructure with Docker Compose from day 1
- Cost restrictions as part of design (API calls, hosting, bandwidth)
- Mandatory documentation via ARCHITECTURE.md
- "Data is sacred" principle since first docker-compose.yml

#### `/hm-engineer` — Senior standard and new audit layers
- Non-negotiable senior baseline (zero bare except, zero any types, zero fire-and-forget, zero hardcoded secrets, zero queries without limit)
- New layer: **Cost x Performance** (justified API calls, minimum context in LLMs, conscious token usage)
- New layer: **Sacred Data** (no destructive operation without confirmation, named volumes, non-destructive migrations)
- New layer: **Infrastructure** (Docker rebuild vs restart, automatic migrations, health checks, ports)
- Performance expansion: parallel I/O, memoization
- Architecture expansion: agent loop validation (max iterations, token limits, timeout)
- Rule: data at risk is always CRITICAL

#### `/hm-designer` — Agent-first UI and pixel perfect
- Agent-first philosophy: UI = visibility + override, not main input
- A24 aesthetic reference added
- **Pixel perfect** section: zero tolerance for misalignment, breaks, cuts
- Technical patterns: full-width layout, shimmer (not spinner), dark-first, inline styles when framework doesn't cooperate, 200-300ms transitions
- New anti-patterns: forms where agent should execute, generic spinners, centered layout on large screens
- Rule: architectural misalignment (form vs agent) is a finding

#### `/hm-qa` — Infrastructure, agent, and cost as tests
- New section: **Infrastructure verification** (containers, migrations, ports, volumes, rebuild, .env)
- New section: **Agent verification** (tool loops, tool hallucination, token usage, cost per interaction)
- New section: **Data integrity** (persistence, non-destructive migrations, backups, destructive operations)
- New section: **Cost check** (API calls per flow, minimum context, redundant calls, cost per user/month)
- Expanded output with Infrastructure, Agent, Data Integrity, and Cost sections

### Changed

- Skill count: 4 → 5 (added `/hm-deploy`)
- Parent SKILL.md updated to reflect 5 skills
- All skills now consider agent-first as paradigm (when applicable)
- Performance expanded from "no N+1" to include external API costs and token management

---

## [1.0.0] — 2026-03-12

Initial release.

### Skills
- `/hm-init` — Project start with best tools and structure
- `/hm-engineer` — Code validation across all layers
- `/hm-designer` — Interface validation against highest standard
- `/hm-qa` — Complete quality assurance

### Infrastructure
- Setup script with automatic symlinks
- CLAUDE.md.template as starting point
- Global and per-project installation
