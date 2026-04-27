# 💣 Explosion Tetris: UCD-F Core Simulation
**The Chaos Evolution of Constrained Dynamics**

Explosion Tetris is not just a puzzle game; it is a high-performance, deterministic state transition simulation built on the **Universal Constrained Dynamics Framework (UCD-F)**. It takes the classic falling-block formula and injects volatile mechanics driven by environment-harvested entropy.

---

## 🏗 System Architecture (UCD-F Spec)

This simulation is engineered with extreme performance constraints in mind, utilizing:

* **Bit-Packed SoA (Structure of Arrays):** The entire game board is managed within a single `Uint32Array`. Every block's state—color, explosive fuse, clearing flags, and spatial offsets—is packed into a 32-bit integer to ensure zero-allocation during the core logic loop.
* **Deterministic Fixed-Point Arithmetic:** All physics and particle cloud dynamics utilize 16.16 fixed-point math, eliminating floating-point non-determinism across different hardware architectures.
* **Entropy Harvesting:** Device noise and user input are dynamically normalized and internalized as system entropy (E2/E3), directly influencing bomb spawn rates and fatigue levels.
* **Entropy Reversal (E-REV):** A GPU-inspired ring buffer maintains a history of the last 300 frames. This allows users to rewind causality up to 5 seconds, even after a system collapse (Game Over).

---

## 💣 Core Dynamics

### ■ Bomb Entities & Half-Life
Select tetrominos spawn with live explosives. These entities have a fixed half-life (10s default / 5s in Critical state). Failure to disarm through line-clearing results in a kinetic explosion, destroying localized blocks and generating high-intensity "E3 Noise" (Garbage Blocks).

### ■ VIF Dynamics (Velocity / Intensity / Fatigue)
* **Velocity:** Base drop speed increases as the level scales.
* **Intensity:** Scoring and visual feedback scale with your current **COMBO (REN)** chain.
* **Fatigue (DANGER):** Failed disarms and explosions accumulate fatigue. High fatigue lead to **ZERO-LOCK** (System Collapse / Game Over).

### ■ Mega Disarm / Total Evacuation
Clearing a bomb at its critical limit (1 second or less) triggers a **Mega Disarm**, performing a total evacuation of all active entities on the board for a massive score bonus.

---

## 🕹 Interface & Controls

### PC Navigation
| Action | Default Keybind |
| :--- | :--- |
| Move Left/Right | `←` / `→` |
| Rotate (CW) | `↑` |
| Soft Drop | `↓` (Hold for Fast Drop) |
| Hard Drop | `Space` (with Kinetic Impact) |
| Hold Piece | `Shift` |
| **Entropy Reversal** | **`Z` (Hold to Rewind)** |
| Suspend/Pause | `P` |
| Configure Params | `O` |

### Mobile / Touch Interface
* **Tap:** Rotate Entity
* **Swipe Horizontal:** Translate Entity
* **Swipe Down:** Initiate Soft Drop (Continuous)
* **Flick Up:** Trigger Hard Drop
* **Two-Finger Tap:** Hold Entity
* **E-REV Button:** Reverse Entropy

---

## 🛠 Environmental Parameters
Adjust simulation parameters—including **SE Volume**, **Drone Synth BGM**, **Lock Delay**, and **Difficulty (VIF Scaling)**—via the `UCD-F PARAMS` console. All configurations and high-entropy states are persisted via local storage.

---

## 🧬 Development "Vibe"
Created through high-velocity **Vibe Coding**. Powered by the Gemini Canvas & HTML5 Canvas API. Designed for high-stakes cognitive engagement.

**INITIATE UCD-F SYSTEM?**
[ CONNECT ]