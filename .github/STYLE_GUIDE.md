# 🎨 Coding Style Guide

To maintain a clean, performant, and immersive codebase for **Project Æ**, please adhere to the following styles.

## ⚡ JavaScript (Vanilla)

### General
*   **Version**: ES6+.
*   **Variables**: Use `const` by default, `let` when reassignment is needed. Avoid `var`.
*   **Formatting**: 4 Spaces indentation. Semicolons are required.

### Performance & Physics
*   **Animation Loop**: Always use `requestAnimationFrame()` for visual updates. Never use `setInterval()` for rendering.
*   **DOM Access**: Cache DOM elements (e.g., `const egg = document.getElementById('egg')`) outside the loop.
*   **Math**: Pre-calculate constants where possible.

### 🔊 Web Audio API
*   **Context**: Always check for `AudioContext` state (`suspended` vs `running`) and resume on first user interaction.
*   **Cleanup**: When stopping sounds, ramp gain down to 0 (e.g., `0.001`) before stopping oscillators to avoid "clicking" artifacts.
*   **Nodes**: Disconnect nodes after use to prevent memory leaks.

### Naming Conventions
*   **Variables/Functions**: `camelCase` (e.g., `spinVelocity`, `playTapSound`).
*   **Constants**: `UPPER_CASE` (e.g., `MAX_PARTICLES`).

---

## 🎨 CSS & Visuals

### General
*   **Layout**: Use Flexbox for centering and Grid for complex layouts.
*   **Units**: Use responsive units (`vw`, `vh`, `clamp()`) to ensure the experience scales from mobile to desktop.

### Animations
*   **Performance**: Animate `transform` and `opacity` properties only. Avoid animating `top`, `left`, `width`, or `height` in loops to prevent reflows.
*   **Naming**: Use kebab-case for classes (e.g., `.celestial-egg`, `.dragon-emblem`).

---

## 🌐 HTML Structure
*   **Semantics**: Use semantic tags where appropriate.
*   **SVG**: Inline SVGs are preferred for dynamic manipulation (like the Dragon Emblem).

---

## 📁 File Naming
*   **Source Files**: `lowercase.ext` (e.g., `script.js`, `styles.css`).
*   **Documentation**: `UPPERCASE.md` (e.g., `README.md`, `PROJECT_PLAN.md`).