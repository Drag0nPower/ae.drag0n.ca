# ⚛️ Physics Engine Documentation

**Project Æ** utilizes a custom, lightweight physics engine built with Vanilla JavaScript. It relies on a `requestAnimationFrame` loop to handle inertia, friction, and boundary constraints, ensuring 60fps performance on most devices.

## Core Concepts

### 1. The Loop (`animate`)
The heart of the physics is the `animate()` function. It runs every frame and calculates the egg's position based on its current state:
- **Dragging**: Physics are paused; position is 1:1 with the pointer.
- **Released**: Physics are active; velocity is applied and decayed.

### 2. State Variables
| Variable | Description |
| :--- | :--- |
| `posX`, `posY` | Current absolute position (pixels). |
| `velX`, `velY` | Current velocity vector (pixels per frame). |
| `spinVelocity` | Rotational velocity (degrees per frame). |
| `rotateZ` | Current rotation angle. |
| `isDragging` | Boolean flag to toggle between "Control" and "Simulation" modes. |

## Mechanics

### Inertia & Friction
We use **Exponential Decay** for friction. Instead of subtracting a fixed amount, we multiply the velocity by a factor less than 1.0 every frame.

```javascript
// Inside animate() loop
spinVelocity *= 0.95; // Retains 95% of speed per frame (Low friction)
velX *= 0.90;         // Retains 90% of speed per frame (High friction)
velY *= 0.90;
```

*   **Result**: The egg stops moving across the screen quickly (heavy feel) but continues to spin for a long time (gyroscopic feel).

### The "Throw"
When the user drags the egg, we calculate the "Throw Velocity" based on the speed of the mouse *just before* release.

```javascript
// Inside handleMove()
velX = (x - lastMouseX) * 2; // Multiplier adds "pop" to the throw
```

### Boundary Constraints
The egg is clamped to the viewport to prevent it from flying off-screen.
- **X-Axis**: `50px` margin.
- **Y-Axis**: `66px` margin.

### Audio Coupling
The physics engine drives the audio engine. The pitch of the binaural beats is directly modulated by the horizontal velocity (`velX`).

```javascript
adjustDragPitch(velX); // Faster drag = Higher pitch
```

## Hybrid Rendering

The rendering uses a hybrid approach for smoothness:
1.  **JS Physics**: Updates `transform` (rotate) and `top`/`left` (position) every frame.
2.  **CSS Transitions**: On release (`handleEnd`), a CSS transition is applied:
    `transition: all 0.3s cubic-bezier(...)`
    
    *Note: This creates a "settling" effect where the browser interpolates the final movements, smoothing out any jitter from the manual JS updates.*

## Future Improvements

- [ ] **Wall Bounce**: Currently, the egg sticks to the wall (`Math.min/max`). We could invert velocity (`velX *= -0.5`) to make it bounce.
- [ ] **Tilt Gravity**: Use `DeviceOrientationEvent` to let gravity pull the egg on mobile devices.