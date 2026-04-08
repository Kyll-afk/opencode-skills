# opencode-skills

Ten cognitive execution modes for OpenCode, built on the Higher Mind philosophy.

## Available Skills

- `/hm-init` — Start a new project with the best tools and structure
- `/hm-architect` — Design system architecture, patterns, and data models
- `/hm-engineer` — Validate code across all layers (architecture, security, performance, cost, quality)
- `/hm-designer` — Validate interface against the highest software design standard
- `/hm-qa` — Test everything, find gaps, verify it works
- `/hm-deploy` — Validate infrastructure, containers, reproducibility, and deploy security
- `/hm-security` — Security audit, vulnerability detection, compliance
- `/hm-refactor` — Improve code structure, naming, and reduce technical debt
- `/hm-document` — Create ADRs, README, API docs, inline comments
- `/hm-optimize` — Profile, identify bottlenecks, optimize database, frontend, backend

Each skill has its own SKILL.md in its subfolder with proper OpenCode frontmatter.

## Installation

### For OpenCode

Place skill folders in one of these locations:
- Project: `.opencode/skills/<name>/SKILL.md`
- Global: `~/.config/opencode/skills/<name>/SKILL.md`
- Claude-compatible: `.claude/skills/<name>/SKILL.md`
- Global Claude: `~/.claude/skills/<name>/SKILL.md`

### Using Setup Script

```bash
git clone https://github.com/Kyll-Afk/opencode-skills.git ~/.claude/skills/opencode-skills
cd ~/.claude/skills/opencode-skills
chmod +x setup
./setup
```

## Usage

In OpenCode or Claude Code, type:
```
/hm-init
/hm-architect
/hm-engineer
/hm-designer
/hm-qa
/hm-deploy
/hm-security
/hm-refactor
/hm-document
/hm-optimize
```

## License

MIT

---

## Credits

Based on [highermind-code-skills](https://github.com/rodrigohighermind/highermind-code-skills) by [Rodrigo Lopes](https://github.com/rodrigohighermind) — Built on the Higher Mind philosophy.
