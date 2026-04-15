# Codex Skills

Cognitive execution modes for [Codex](https://developers.openai.com/codex). Each skill brings specialized expertise to different aspects of software development.

## Skills Overview

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `/hm-init` | Start projects with best tools and structure | New project setup |
| `/hm-architect` | System architecture, patterns, data models | Design phase |
| `/hm-engineer` | Code validation across all layers | Code review, auditing |
| `/hm-designer` | Interface validation against highest standards | UI/UX review |
| `/hm-animator` | SVG animations with icon libraries or pure CSS | Motion design |
| `/hm-qa` | Testing everything — unit, integration, e2e | Quality assurance |
| `/hm-deploy` | Infrastructure, containers, deploy security | Pre-deployment |
| `/hm-security` | Security audits and vulnerability detection | Security review |
| `/hm-refactor` | Code structure improvement, reduce debt | Code improvement |
| `/hm-document` | ADRs, README, API docs, runbooks | Documentation |
| `/hm-optimize` | Performance profiling and optimization | Performance tuning |

## Installation

```bash
# Clone to Codex's skills folder
git clone https://github.com/Kyll-Afk/opencode-skills.git ~/.agents/skills

# Or install specific skills
cp -r skills/hm-animator ~/.agents/skills/
```

## Usage

In Codex, invoke skills with `$` or use `/skills`:

```
$hm-animator    # SVG animation
$hm-designer    # UI/UX validation
$hm-engineer    # Code auditing
$hm-security    # Security review
...
```

## Codex-Specific Features

These skills follow the Agent Skills standard and support:

- **`allow_implicit_invocation`**: Control auto-invocation via `agents/openai.yaml`
- **Progressive disclosure**: Metadata loads first, full content loads on use
- **`agents/openai.yaml`**: Configure UI metadata, icons, and invocation policy
- **Skill installer**: `$skill-installer` to add curated skills

## Project Structure

```
~/.agents/skills/
├── hm-init/
│   ├── README.md
│   └── SKILL.md
├── hm-architect/
├── hm-engineer/
├── hm-designer/
├── hm-animator/
│   ├── README.md
│   ├── SKILL.md
│   └── examples/
├── hm-qa/
├── hm-deploy/
├── hm-security/
├── hm-refactor/
├── hm-document/
├── hm-optimize/
└── hm-security-auth/
```

## License

MIT
