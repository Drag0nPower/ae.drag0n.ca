# Changelog

All notable changes to **Project Æ (Celestial Dragon Egg)** will be documented in this file.

## [Unreleased]
### Added
- **Project Structure**: Added `.gemini` and `.github` folders.
- **Documentation**: Added `docs/PHYSICS.md` and `docs/AUDIO.md`.
- **Roadmap**: Expanded with "Brainwave Modes" (Theta/Delta/Alpha/Chaos), "Care Metrics", and "The Hatching" (Phase 7).
### Fixed
- **Audio**: Added `audioContext.resume()` on first interaction to prevent browser autoplay blocking.
### Changed
- **Performance**: Optimized particle creation using `DocumentFragment` to reduce DOM reflows during initialization.

## [1.0.0] - 2024-05-22
### Added
- **Interactive Egg**: Draggable DOM element with inertia physics.
- **Visuals**:
  - Nebula background with fractal noise SVG.
  - 80 CSS-animated particles.
  - SVG Dragon Emblem.
  - Dynamic lighting/shadows based on state.
- **Audio Engine**:
  - Web Audio API implementation.
  - 800Hz "Tap" sine wave.
  - Binaural drone (77Hz L / 117Hz R) with 40Hz beat frequency.
  - Pitch modulation based on drag velocity.
- **Haptics**: Vibration patterns for mobile devices.
- **Core**: Responsive layout handling.