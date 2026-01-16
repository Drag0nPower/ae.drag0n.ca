# 🔊 Audio Engine Documentation

**Project Æ** features a custom-built audio engine powered by the **Web Audio API**. It relies entirely on real-time synthesis (mathematically generated sound waves) rather than pre-recorded audio samples. This ensures zero load times and infinite dynamic reactivity.

## Core Philosophy

The audio is designed to be **organic and reactive**. It does not just play a sound; it "performs" the sound based on the physics of the egg.

## Architecture

### 1. The "Tap" (Interaction Feedback)
A short, sharp sound triggered immediately upon `mousedown` or `touchstart`.

*   **Waveform**: Sine.
*   **Frequency**: 800 Hz.
*   **Envelope**:
    *   Attack: Instant (0s).
    *   Decay: Exponential ramp to silence over 0.2s.
*   **Purpose**: Provides immediate tactile confirmation of the user's input.

### 2. The Binaural Drone (Atmosphere)
When the egg is dragged or thrown, a continuous drone activates. This is a **Binaural Beat** generator designed to create a 40Hz interference pattern.

#### Frequency Map
| Channel | Base Frequency | Panning |
| :--- | :--- | :--- |
| **Left** | 77 Hz | -1.0 (Hard Left) |
| **Right** | 117 Hz | +1.0 (Hard Right) |
| **Result** | **40 Hz Beat** | (Gamma Range) |

*   **Why 40Hz?** In neuroscience, 40Hz (Gamma waves) is often associated with binding distinct perceptions into a coherent whole—fitting for an "Awakening" phase.

#### LFO Modulation
To enhance the stereo width and texture, two Low Frequency Oscillators (LFOs) modulate the gain (volume) of the left and right channels at 40Hz.
*   **Left LFO**: Phase aligned.
*   **Right LFO**: Inverted phase.
*   **Effect**: This creates a shimmering, rotating sensation that reinforces the binaural beat.

## Dynamic Reactivity

The audio engine is tightly coupled to the Physics Engine. The sound changes based on how fast the user throws the egg.

### Velocity Coupling
The `adjustDragPitch(velocity)` function maps the horizontal velocity (`velX`) to a pitch multiplier.

```javascript
// Calculate pitch factor (0.5x to 2.0x)
const pitchFactor = Math.max(0.5, Math.min(2, (Math.abs(velocity) / 100) + 0.5));

// Apply to carrier frequencies
const baseCarrier = 77 * pitchFactor;
leftOscillator.frequency.setValueAtTime(baseCarrier, ...);
rightOscillator.frequency.setValueAtTime(baseCarrier + 40, ...);
```

*   **Result**:
    *   **Slow Drag**: Deep, rumbling drone (Low pitch).
    *   **Fast Throw**: High, energetic whine (High pitch).
    *   **Constant**: The 40Hz beat difference is maintained regardless of the base pitch.

## Technical Implementation Details

### State Management
Browsers prevent AudioContext from running until a user gesture occurs. We handle this in `handleStart`:
```javascript
if (audioContext.state === 'suspended') {
    audioContext.resume();
}
```

### Click Prevention
To prevent digital "popping" or "clicking" artifacts when sounds stop, we never stop an oscillator instantly. We always ramp the gain down first:
```javascript
gainNode.gain.exponentialRampToValueAtTime(0.001, currentTime + 0.3);
oscillator.stop(currentTime + 0.3);
```

### Garbage Collection
Nodes are disconnected and variables set to `null` in `stopDragSound` to prevent memory leaks, as the Web Audio graph can become expensive if nodes are left dangling.