# 🎯 Center of Gravity (CoG) Analysis

Proper **Center of Gravity (CoG)** placement is vital to ensure DRONE_SKY_STRIKE maintains **stable flight, accurate targeting**, and does not flip or wobble during payload deployment. This document outlines how we calculated and validated the drone’s CoG.

---

## 📌 CoG Goal

> Keep the **CoG at or very close to the geometrical center** of the drone (both horizontally and vertically).

---

## 🔧 CoG Axes Breakdown

- **X-axis (Front ↔ Back):** Balanced between battery (bottom front) and GPS/payload (top rear).
- **Y-axis (Left ↔ Right):** Symmetry maintained via equal arm + motor/ESC placement.
- **Z-axis (Top ↔ Bottom):** Balanced between top payload and bottom battery.

---

## 🧮 Simplified Moment Calculation

### Assume:
- Frame center = Origin (0,0,0)
- Distances in cm from origin
- Mass × Distance used for torque balance

| Component       | Mass (g) | Z-Distance (cm) | Moment (g·cm) |
|------------------|----------|------------------|----------------|
| Payload          | 500      | +5 (top)         | +2500          |
| Battery          | 500      | -4 (bottom)      | -2000          |
| FC, GPS, Wires   | 150      | +0.5             | +75            |

🟰 Total Moment (Z): `2500 - 2000 + 75 = +575 g·cm`

---

### 🔧 Correction Strategy

- Move **battery 1–1.5 cm further downward** or backward
- Add **counterweight** (30–50g) below the frame if needed
- Use **CoG simulation in CAD** to refine before build

---

## 🎯 Final CoG Target:

- **< ±1 cm** off in any direction from geometric center
- No pitch/roll drift at hover (as seen in flight logs)

---

## 🧪 Testing Methods

- Hang drone by prop tips — observe leveling
- Perform short manual hover test in stabilize mode
- Use **flight log (Pixhawk) accelerometer & gyro data**

---

## 📝 Notes

- Payload deployment may cause CoG shift → mitigate with flight controller tuning or counter-shifted frame design
- Update CoG file if payload or battery changes in future iterations

---

> Next: [CAD_PREVIEW →](./CAD_PREVIEW/)
