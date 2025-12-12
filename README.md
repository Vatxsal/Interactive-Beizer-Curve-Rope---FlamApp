# Interactive Cubic Bézier Rope

This project implements a fully manual, interactive **cubic Bézier curve** that behaves like a springy rope. It includes Bézier math, tangent computation, user interaction, and real-time physics — **implemented from scratch**, with no external libraries.

---

## 🎯 **Features**

### ✓ **Cubic Bézier Curve (Manual Implementation)**

Using 4 control points:

* **P0**, **P3** → fixed endpoints
* **P1**, **P2** → dynamic spring-controlled points

Formula used:

```
B(t) = (1−t)^3 P0 + 3(1−t)^2 t P1 + 3(1−t) t^2 P2 + t^3 P3
```

### ✓ **Derivative / Tangent Calculation**

```
B'(t) = 3(1−t)^2 (P1−P0) + 6(1−t)t (P2−P1) + 3t^2 (P3−P2)
```

Tangent vectors are normalized and drawn along the curve.

### ✓ **Spring-Damper Physics for P1, P2**

Simulates rope-like elasticity:

```
acceleration = -k * (pos - target) - damping * velocity
```

This produces smooth, natural motion.

### ✓ **Interactive Input**

Supports:

* **Mouse movement** (pulls control points)
* **Dragging** P1 or P2 directly
* **Device tilt (mobile)** via `DeviceOrientationEvent`

### ✓ **Real-Time Rendering**

* Uses HTML Canvas
* ~60 FPS animation loop
* Draws curve, control polygon, tangents, and control points

---

## 📁 **Files Included**

### **1. `bezier_rope.html`**

The complete implementation containing:

* Canvas setup
* Bézier math
* Physics engine
* Interaction handling
* Rendering loop

### **2. `README.md` (this file)**

Explains:

* Bézier math
* Physics model
* Design choices
* How to run the simulation

---

## ▶️ **How to Run**

1. Save the HTML file as `bezier_rope.html`.
2. Open it in any modern browser:

   * Chrome
   * Firefox
   * Safari
3. Move the mouse or drag P1/P2 to interact.
4. On mobile: tilt the device to influence the rope.

---

