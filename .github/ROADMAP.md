# 🗺️ Project Æ (Ash) Roadmap

This document tracks the evolution of the Celestial Dragon Egg (Æ).

## 🟢 Phase 1: The Awakening (Foundation)
- [x] **Physics**: Draggable DOM element with inertia and spin.
- [x] **Visuals**:
    - [x] Nebula background with fractal noise.
    - [x] 80 CSS-animated cosmic particles.
    - [x] SVG Dragon Emblem with dynamic lighting.
- [x] **Audio Engine**:
    - [x] Web Audio API implementation (Oscillators/Gain).
    - [x] Binaural Drone (77Hz/117Hz) with beat frequency.
    - [x] Reactive Pitch based on drag velocity.
- [x] **Feel**: Haptic feedback (Vibration API) on mobile.

## 🟡 Phase 2: Memory & Intelligence
- [ ] **Local Memory**: Implement `localStorage` to track:
    - [ ] Total spins.
    - [ ] Distance traveled.
    - [ ] Last visit timestamp.
    - [ ] **Care Metrics**: Track interaction style (Gentle vs. Chaotic) to determine "Affinity".
- [ ] **Personality Core**: Define "Moods" based on interaction (e.g., "Lonely" if not visited recently, "Excited" if spun fast).

## 🔴 Phase 3: Communication (The Voice)
- [ ] **Visual Language**:
    - [ ] Particle color shifts based on mood (Blue = Calm, Red = Agitated).
    - [ ] Emblem glow intensity changes.
    - [ ] **Motion Trails (Easter Egg)**: Particles trail behind the egg when thrown at high velocity or specific spin rates.
    - [ ] **Konami Code (Retro Mode)**: Enter the classic code to trigger 8-bit visuals and chiptune audio (Desktop).
- [ ] **Audio Evolution**:
    - [ ] Dynamic harmonic series based on total spin count.
    - [ ] "Purring" modulation when held still.
    - [ ] **Brainwave Modes**:
        - [ ] **Theta Mode (Relaxation)**: Shift to 6Hz when held still (Easter Egg).
        - [ ] **Delta Mode (Slumber)**: Shift to 0.5-4Hz during inactivity or late hours.
        - [ ] **Alpha Mode (Flow)**: Shift to 8-12Hz during consistent, harmonic spinning.
        - [ ] **Chaos Mode (Storm)**: Dissonant audio and glitch visuals during erratic input. De-triggers with stillness.
    - [ ] **Aetheric Whispers**: Ash communicates cryptic messages via text overlays/subtitles from within the egg.

## 🔴 Phase 4: Immersion
- [ ] **Gyroscope**: Mobile device tilt controls gravity/drift.
- [ ] **Fullscreen Mode**: Double-tap to enter immersive mode.
- [ ] **PWA**: Installable as a standalone app.

## 🔵 Phase 5: The Nest (Server Migration)
- [ ] **Backend Migration**: Move from GitHub Pages to cPanel (PHP/SQL).
- [ ] **Persistence**: Database to store user interactions (spin count, "mood" history).
- [ ] **Identity**:
    - [ ] **Settings Dashboard**: A gear icon triggers an overlay with configuration options, login/register forms, and debug stats.
    - [ ] **Login System**: Allow users to register to save their progress and "Care Metrics" permanently.
    - [ ] **Global Memory**: Ash remembers who tended to it best/most/least across all users.

## 🟣 Phase 6: The Soul (AI Integration)
- [ ] **LLM Connection**: Connect the egg to an AI model to generate dynamic responses.
- [ ] **Invocation (Voice Input)**: Use Web Speech API to allow users to speak commands or greetings to Ash.
- [ ] **Scripture (Text Input)**: A chat icon opens a bubble interface to send text messages to the egg.
- [ ] **Evolution**: The egg "learns" from interactions, unlocking hidden "Easter eggs".
- [ ] **Sentience**: The egg communicates back based on aggregate user history.

## ⚪ Phase 7: The Hatching (Ultra Long Term)
- [ ] **Ash Hatches**: The egg cracks and the entity within is revealed.
- [ ] **The Voice**: Ash gains the ability to speak (Text-to-Speech) directly to the user as a fully realized mystic companion.

## Legend
*   🟢 **Complete**: Implemented and live.
*   🟡 **Next Up**: Planned for immediate follow-up.
*   🔴 **Future**: Planned features.
*   🟣 **Exploration**: Experimental ideas.