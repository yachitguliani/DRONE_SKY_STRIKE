# ⚙️ Weight Distribution & Frame Design

A well-balanced frame is essential for flight stability, efficient control, and safe payload handling.  
This document outlines the weight distribution strategy used in **DRONE_SKY_STRIKE**, including key component weights and positioning logic.

---

## 📦 Estimated Weight Breakdown

| Component             | Qty | Weight (g) | Position                |
|------------------------|-----|-------------|--------------------------|
| Frame (Carbon Fiber)   | 1   | 500         | Central base             |
| Motors (700–900 KV)    | 4   | 55 × 4 = 220| Ends of each arm         |
| ESCs (30A BLHeli-S)    | 4   | 10 × 4 = 40 | On arms near motors      |
| Propellers (10x4.5”)   | 4   | 10 × 4 = 40 | Attached to motors       |
| Pixhawk FC             | 1   | 40          | Center, slightly forward |
| GPS Module             | 1   | 25          | Rear or top-mounted      |
| 4S LiPo Battery        | 1   | 500         | Bottom center (balanced) |
| Payload (explosive)    | 1   | ~500        | Top central bay          |
| Servo (trigger)        | 1   | 30          | Near payload latch       |
| Wiring + Connectors    | —   | ~100        | Spread across frame      |

---

## ⚖️ Total Estimated Takeoff Weight

**~2.5 kg (2500 g)** including payload.

---

## 📍 Placement Strategy

- 🔋 **Battery:** Bottom plate, centered to balance payload mass on top.
- 📦 **Payload:** Cylindrical warhead placed above CG — aligned with thrust axis for minimal pitch shift on release.
- 🧠 **Flight Controller (Pixhawk):** Slightly forward of center (optimizes GPS + servo routing).
- 📡 **GPS + Compass:** Mounted on a mast at the rear or top to reduce interference.
- 🔌 **ESCs:** On arms, under propeller wash for passive cooling.

---

## 🧠 Design Considerations

- Keep **CoG at geometric center** for stable hover
- Avoid placing all heavy items on top → use **counterbalancing**
- Use **symmetric arm lengths** and **equal motor spacing**
- Allow for **vibration damping** under FC and payload

---

## 💡 Tips

- Use a scale to measure individual components during assembly
- Use foam or silicone grommets to isolate FC from vibration
- Test dry runs without payload before live trials

---

> Next: [center_of_gravity.md →](./center_of_gravity.md)
