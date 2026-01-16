# Contributing Guide

Thank you for your interest in contributing to **Celestial Dragon Egg (Project Æ)**! This guide provides instructions for developers (both human and AI) to ensure consistency, performance, and immersion.

## Project Vision

*   **Immersive Experience**: Prioritize "feel" and "atmosphere". Animations must be 60fps smooth.
*   **Vanilla Purity**: We use pure JavaScript, HTML, and CSS. No heavy frameworks. We build our own physics and audio engines.
*   **Audio-Visual Synergy**: Visuals (DOM/Canvas) and Audio (Web Audio API) must be tightly coupled.

## Tech Stack

*   **Frontend**: Vanilla JavaScript (ES6+), HTML5, CSS3.
*   **Audio**: Web Audio API (Oscillators, Gain, Panner).
*   **Hosting**: GitHub Pages.

## AI Collaboration

*   **Primary Assistant**: Google Gemini.
*   **Context**: Always refer to the `.gemini/` directory for the Persona (`PERSONA.md`), System Context (`CONTEXT.md`), and Task Prompts (`GEMINI.md`).
*   **Workflow**: Use `.gemini/SCRATCHPAD.md` for brainstorming before writing code.

## Development Workflow

1.  **Initial Setup**:
    *   Clone the repository.
    *   Run a local server (e.g., `python -m http.server` or VS Code Live Server) to support Web Audio API requirements.
2.  **Branching**: Use feature branches (e.g., `feature/memory-system`, `fix/audio-glitch`).
3.  **Documentation**:
    *   Update `readme.md` if new features change the user experience.
    *   Update `CHANGELOG.md` for notable changes.

## Coding Standards

### Repository Structure
*   `index.html`: Main entry point.
*   `styles.css`: Visual styling and animations.
*   `script.js`: Core logic (Physics, Audio, Interaction).
*   `.gemini/`: AI context files.

### Performance & Quality
*   **Loops**: Use `requestAnimationFrame` for visual updates, never `setInterval`.
*   **Audio**: Always handle `AudioContext` state (resume on user interaction).
*   **Style**: Clean, modern JavaScript. Use `const`/`let`.
*   **Responsiveness**: Mobile-first touch handling.

## Commit Messages
Follow Conventional Commits:
*   `feat:` (New feature)
*   `fix:` (Bug fix)
*   `docs:` (Documentation update)
*   `refactor:` (Code cleanup)
*   `style:` (Formatting, missing semi-colons, etc.)

## Release Process

1.  **Update Changelog**: Move items from `[Unreleased]` to the new version number.
2.  **Tag Release**: Use semantic versioning (e.g., `v1.0.0`).

---

*Last Updated: Phase 1 (Foundation)*