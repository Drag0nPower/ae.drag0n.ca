# Changelog

All notable changes to **Project Æ (Celestial Dragon Egg)** will be documented in this file.

## [Unreleased]
### Added
- **Project Structure**: Added `.gemini` and `.github` folders.
- **Documentation**: Added `docs/PHYSICS.md` and `docs/AUDIO.md`.
- **Roadmap**: Expanded with "Settings Dashboard", "Chat UI", "Brainwave Modes", "Konami Code", "Care Metrics", "Motion Trails", and "The Hatching".
- **Audio**: Added `playBounceSound()` for wall impacts (Triangle wave).
- **Documentation**: Added `docs/CONTRA.md` detailing the planned Konami Code Easter egg.
### Fixed
- **Audio**: Added `audioContext.resume()` on first interaction to prevent browser autoplay blocking.
### Changed
- **Performance**: Optimized particle creation using `DocumentFragment` to reduce DOM reflows during initialization.
- **Physics**: Implemented elastic wall collisions (bouncing) instead of clamping.
- **Physics**: Reduced friction for longer spins and floatier movement.
- **Physics**: Increased torque sensitivity for faster rotation on drag.

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