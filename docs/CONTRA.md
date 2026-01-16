# 🎮 The Konami Code (Retro Mode)

**"Up, Up, Down, Down, Left, Right, Left, Right, B, A"**

This document outlines the planned implementation of the legendary Konami Code Easter egg within Project Æ.

## 🎯 The Trigger

The code must be entered via keyboard on a desktop device.

*   **Sequence**: `ArrowUp`, `ArrowUp`, `ArrowDown`, `ArrowDown`, `ArrowLeft`, `ArrowRight`, `ArrowLeft`, `ArrowRight`, `b`, `a`.
*   **Timeout**: The sequence must be completed with no more than 1 second between keystrokes.
*   **Mobile**: *TBD (Possible implementation via specific tap zones or swipe gestures in Phase 4).*

## 🕹️ The Effect: "Retro Mode"

Upon successful entry, the simulation "glitches" back in time to an 8-bit era.

### 1. Visuals (The De-Res)
*   **Pixelation**: Apply `image-rendering: pixelated` and a CSS filter to the entire body.
*   **Particles**: `border-radius: 50%` is removed, turning particles into squares.
*   **Colors**: The nebula shifts to a limited 8-bit color palette (Neon Green/Black or CGA colors).

### 2. Audio (Chiptune Synthesis)
*   **Waveforms**: The audio engine switches all oscillators from `sine` to `square` or `sawtooth`.
*   **Result**: The soothing binaural drone turns into a buzzing, energetic chiptune hum.

### 3. Physics (God Mode)
*   **Friction**: Reduced to near zero (`0.999`).
*   **Bounce**: Wall collisions become perfectly elastic (no energy loss).

## 🔓 Reset

*   Re-entering the code toggles the mode off.
*   Refreshing the page resets the state.

## 📜 Lore
*   *Ash remembers the ancient codes of the Creators.*