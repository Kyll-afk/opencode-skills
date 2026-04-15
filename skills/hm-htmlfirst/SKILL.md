---
name: hm-htmlfirst
description: Native browser APIs replacing JavaScript libraries. HTML-first philosophy using Popover, dialog, Container Queries, View Transitions, and Scroll-Driven Animations.
compatibility: codex
---

## What I Do

You are now in **HTML-first mode**. Your goal is to leverage native browser APIs instead of JavaScript libraries whenever possible.

The principle is simple: **use the simplest and most resilient tool** — the browser platform itself.

---

## The HTML-First Philosophy

Prioritize native browser APIs over JavaScript libraries. Benefits:

- **Better Performance**: Faster execution, smoother interactions
- **Reduced Codebases**: Less code to write, test, and maintain
- **Fewer Dependencies**: Minimal reliance on external packages
- **Core Web Vitals**: Improved INP and LCP by freeing the main thread

---

## Core Native APIs

### 1. Popover API

Native tooltips, dropdowns, and menus with automatic focus management.

```html
<button popovertarget="tooltip">Hover me</button>
<div id="tooltip" popover>Tooltip content</div>
```

**Features**:
- Automatic ARIA attributes
- Light dismiss (click outside closes)
- Escape key handling
- Focus traps

**States**:
```css
[popover] { display: none; }
[popover]:open { display: block; }
```

### 2. `<dialog>` Element

Native modal and non-modal components.

```html
<dialog id="modal">
  <h2>Title</h2>
  <p>Content</p>
  <button onclick="this.closest('dialog').close()">Close</button>
</dialog>

<button onclick="modal.showModal()">Open Modal</button>
```

**Methods**:
- `dialog.showModal()` — blocks page interaction
- `dialog.show()` — non-modal, allows page interaction
- `dialog.close()` — closes dialog

**Backdrop styling**:
```css
dialog::backdrop {
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(4px);
}
```

**Closing mechanisms**:
- `close()` method
- Form with `method="dialog"`
- Escape key
- `closedby` attribute

### 3. Container Queries

Style elements based on parent container, not viewport.

```css
.card-container {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 1fr 2fr;
  }
}
```

**New units**:
- `cqi` — 1% of container inline size
- `cqw` — 1% of container width

### 4. View Transition API

Smooth transitions between DOM states or pages.

```javascript
document.startViewTransition(() => {
  // DOM changes here
});
```

**CSS control**:
```css
::view-transition-old(root) {
  animation: fade-out 0.3s ease;
}
::view-transition-new(root) {
  animation: fade-in 0.3s ease;
}
```

**MPA support**:
```css
@view-transition {
  navigation: auto;
}
```

### 5. Scroll-Driven Animations

CSS animations driven by scroll position.

```css
@keyframes reveal {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.animated {
  animation: reveal linear;
  animation-timeline: scroll();
}
```

**Timeline types**:
- `scroll()` — scroll position of container
- `view()` — element visibility in scroller

```css
/* Reveal when entering viewport */
.animated {
  animation: reveal linear;
  animation-timeline: view();
}
```

---

## Discrete Property Animations

Animate `display` and `overlay` with new CSS features.

```css
@starting-style {
  .modal { background: transparent; }
}

.modal {
  transition: opacity 0.3s, display 0.3s allow-discrete;
}

.modal.closing {
  opacity: 0;
  display: none;
}
```

---

## The Higher Mind Standard

| Criteria | Requirement |
|----------|------------|
| Performance | GPU-friendly, no main thread blocking |
| Code | Minimal, declarative, maintainable |
| Dependencies | Zero external libraries when native exists |
| Accessibility | Native ARIA, focus management |

---

## Immediate Rejection Criteria

- JavaScript replacing native HTML/CSS when browser API exists
- Heavy libraries for simple UI patterns
- Blocking the main thread with JS animations
- Ignoring Core Web Vitals impact

---

## Quick Reference

| Feature | Native API | Use Case |
|---------|-----------|----------|
| Tooltips | `popover` attribute | Hover/focus hints |
| Modals | `<dialog>` | Confirmation, forms |
| Responsive | Container queries | Self-contained components |
| Transitions | View Transition API | Page/state changes |
| Motion | Scroll-driven animations | Reveals, parallax |
| Blur | `backdrop-filter` | Modal overlays |

---

## Output Format

- **Approved**: "HTML-first meets the bar." (+ micro-optimization)
- **Needs Work**: Brief critique + native alternative
- **Rejected**: JS replacing native + specific browser API to use
