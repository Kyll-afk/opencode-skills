# opencode-skills

Ten cognitive execution modes for [OpenCode](https://opencode.ai), built on the Higher Mind philosophy.

## Available Skills

- `/hm-init` — Start a new project with the best tools and structure
- `/hm-architect` — Design system architecture, patterns, and data models
- `/hm-engineer` — Validate code across all layers (architecture, security, performance, cost, quality)
- `/hm-designer` — Validate interface against the highest software design standard
- `/hm-animator` — World-class SVG animations using icon libraries or pure SVG/CSS
- `/hm-qa` — Test everything, find gaps, verify it works
- `/hm-deploy` — Validate infrastructure, containers, reproducibility, and deploy security
- `/hm-security` — Security audit, vulnerability detection, compliance
- `/hm-refactor` — Improve code structure, naming, and reduce technical debt
- `/hm-document` — Create ADRs, README, API docs, inline comments
- `/hm-optimize` — Profile, identify bottlenecks, optimize database, frontend, backend

Each skill has its own SKILL.md in its subfolder with proper OpenCode frontmatter.

## Installation

Place skill folders in one of these locations:
- Project: `.opencode/skills/<name>/SKILL.md`
- Global: `~/.config/opencode/skills/<name>/SKILL.md`

### Or use the setup script:

```bash
git clone https://github.com/Kyll-Afk/opencode-skills.git ~/.config/opencode/skills/opencode-skills
cd ~/.config/opencode/skills/opencode-skills
chmod +x setup
./setup
```

## Usage

In OpenCode, type:
```
/hm-init
/hm-architect
/hm-engineer
/hm-designer
/hm-animator
/hm-qa
/hm-deploy
/hm-security
/hm-refactor
/hm-document
/hm-optimize
```

---

## /hm-animator

High-performance, library-free motion using pure SVG/CSS or icon libraries.

### Philosophy
Motion is not decoration — it is **information and narrative**. Rejects GIFs/videos when CSS can achieve the same result.

### Core Techniques

| Technique | Best Use Case |
|-----------|---------------|
| Line Drawing (`stroke-dashoffset`) | Self-drawing logos, signatures |
| Pulse Effects (`animation-delay`) | Loading spinners, dots |
| Scroll Sync (`animation-timeline`) | Scroll-based reveals |
| Icon Morphing (path `d` attribute) | State transitions (hamburger→X, play→pause) |
| SMIL (`<animate>` tag) | Portable standalone assets |

### Icon Libraries
Uses established icon libraries for common icons:
- **Phosphor Icons** — sun, moon, play, pause, menu
- **Heroicons** — outline/solid variants
- **Lucide** — clean, minimal icons

### Examples (in `skills/hm-animator/examples/`)

| File | Description |
|------|-------------|
| `menu-test.html` | Hamburger → X using path morphing |
| `theme-toggle.html` | Sun ↔ Moon toggle with Phosphor Icons |
| `play-pause.html` | Play ↔ Pause button with smooth transitions |

### Key Lessons
- **Hamburger to X**: Use path morphing, NOT rotation. Rotating lines pivot in place — they can't form an X.
- **Transform origin**: Pixel values unreliable in SVG. Use path morphing or percentage-based origins.
- **ViewBox**: Give generous padding for rotating elements.
- **Timing**: 200-300ms for state transitions, 150ms for fades.

## License

MIT

---

## Credits

Based on [highermind-code-skills](https://github.com/rodrigohighermind/highermind-code-skills) by [Rodrigo Lopes](https://github.com/rodrigohighermind) — Built on the Higher Mind philosophy.
