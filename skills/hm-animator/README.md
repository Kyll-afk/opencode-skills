# hm-animator

World-class SVG animation expert. High-performance motion using icon libraries or pure SVG/CSS.

## Usage

In OpenCode:
```
/hm-animator
```

## Techniques

| Technique | Best Use Case |
|-----------|---------------|
| Line Drawing (`stroke-dashoffset`) | Self-drawing logos, signatures |
| Pulse Effects (`animation-delay`) | Loading spinners, dots |
| Scroll Sync (`animation-timeline`) | Scroll-based reveals |
| Icon Morphing (path `d` attribute) | State transitions (hamburger→X) |
| SMIL (`<animate>` tag) | Portable standalone assets |

## Examples

See `examples/` folder:
- `menu-test.html` — Hamburger → X transition
- `theme-toggle.html` — Sun ↔ Moon toggle
- `play-pause.html` — Play ↔ Pause button
- `animation-test.html` — SVG/CSS basics

## Icon Libraries

- **Phosphor Icons** — ph-sun, ph-moon, ph-list
- **Heroicons** — outline/solid variants
- **Lucide** — clean, minimal icons
