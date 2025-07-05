# 🔧 Motor Selection & Thrust Calculation

This document breaks down the logic and math behind selecting the optimal motors for **DRONE_SKY_STRIKE**, ensuring sufficient lift, efficiency, and payload delivery capabilities.

---

## 📌 Objective

- Lift a total drone weight of **~2.5 kg**, including ~0.5 kg payload
- Maintain **thrust-to-weight ratio ≥ 2:1** for stable vertical flight
- Ensure **motor + prop combo** matches current limits and provides decent flight time

---

## ⚙️ Key Assumptions

| Parameter               | Value              |
|-------------------------|--------------------|
| Total Weight (W)        | 2.5 kg (24.5 N)     |
| Thrust-to-Weight Ratio  | 2:1 (recommended)   |
| Required Total Thrust   | ~5.0 kg (49 N)      |
| Number of Motors        | 4 (quadcopter)      |
| Required Thrust/Motor   | ~1.25 kg (12.3 N)   |

---

## ✅ Recommended Motor

| Model                  | T-Motor MN3110 700KV / EMAX MT2213 935KV |
|------------------------|-------------------------------------------|
| Voltage                | 11.1–14.8V (3S–4S LiPo)                    |
| Max Continuous Thrust  | ~1300–1400g with 10x4.5 props              |
| Max Current Draw       | 15–18 A                                   |
| Motor Weight           | ~55g each                                 |

---

## ⚙️ Propeller Match

- **10x4.5 or 11x4.7** Carbon Fiber Props
- Low pitch for stable hovering + high lift
- Good efficiency when paired with 700–900 KV motors

---

## 🔋 Power Budget (Rough Estimate)

| Component        | Value                  |
|------------------|------------------------|
| Total Draw       | ~15 A × 4 = 60 A       |
| Battery          | 4S 5200mAh (77 Wh)     |
| Hover Time       | (77 / 60) × 60 ≈ ~77 mins theoretical  
| Real Flight Time | ~10–12 mins (with losses)

---

## ⚠️ Safety Margins

- Use **30A ESCs** for thermal margin (2× motor current)
- Ensure proper cooling and ESC spacing
- Include vibration damping to protect motor mounts

---

## 📝 Notes

- You can upgrade to **T-Motor F90** or **iFlight Xing** series for better thrust.
- Always check prop compatibility with motor shaft and frame clearance.

---

> Next: [battery_selection.md →](./battery_selection.md)
