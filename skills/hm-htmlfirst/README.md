# hm-htmlfirst

Native browser APIs replacing JavaScript libraries. HTML-first philosophy using Popover, dialog, Container Queries, View Transitions, and Scroll-Driven Animations.

## Usage

In OpenCode:
```
/hm-htmlfirst
```

## Core Principles

- **Use native browser APIs** instead of JavaScript libraries
- **Reduce dependencies** — zero external packages when native exists
- **Improve performance** — offload to browser's rendering engine

## Native APIs

| Feature | API | Example |
|---------|-----|---------|
| Tooltips/Dropdowns | Popover API | `popovertarget="id"` |
| Modals | `<dialog>` | `showModal()`, `show()` |
| Responsive | Container Queries | `@container` |
| Transitions | View Transition API | `startViewTransition()` |
| Motion | Scroll-Driven Animations | `animation-timeline` |

## When to Use

- Creating tooltips or dropdowns
- Building modals or dialogs
- Making responsive components
- Adding page/state transitions
- Implementing scroll animations

## Performance Benefits

- Improved Core Web Vitals (INP, LCP)
- Reduced main thread blocking
- Smaller bundle sizes
- Less code to maintain
