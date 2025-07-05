# 🔋 Battery Selection & Flight Time Estimation

Choosing the right battery is crucial to ensure that **DRONE_SKY_STRIKE** balances endurance, performance, and payload delivery. This document outlines how the battery was selected based on **weight, current draw, capacity, and discharge rate**.

---

## 🎯 Requirements

- Support peak current draw from all 4 motors (approx. **60 A total**)
- Provide enough capacity for **10–12 mins flight time**
- Not exceed weight budget or compromise CoG

---

## 📐 Battery Specs Chosen

| Parameter              | Value                      |
|------------------------|----------------------------|
| Type                   | LiPo (Lithium Polymer)     |
| Cell Count             | 4S (14.8V nominal)         |
| Capacity               | 5200 mAh                   |
| Discharge Rate (C)     | ≥35C                       |
| Max Discharge Current  | 35 × 5.2 = **182 A**       |
| Weight                 | ~400–500 g                 |

---

## ⚡ Why 4S?

- **Better efficiency** than 3S (higher voltage = lower current draw)
- Ideal for 700–900 KV motors with 10x4.5” props
- Improves stability during payload carry & release

---

## 🕒 Flight Time Calculation

### 🔸 Step 1: Estimate Total Power Consumption

- Avg current draw: **~60 A** (full system)
- Battery energy = 4 × 4.2 V × 5.2 Ah = **~87.4 Wh**

### 🔸 Step 2: Theoretical Max Time

> `Flight Time = (Battery Energy / Power Draw) × 60`

`= (87.4 / (60 × 14.8)) × 60 ≈ 11.8 mins`

✅ **Expected real-world time** (accounting for losses, wind, telemetry, etc.):  
**~9–12 mins** (with 15–20% reserve)

---

## ✅ Discharge Rate Justification

| Metric           | Value         |
|------------------|---------------|
| Max Current Draw | ~60 A         |
| Battery Burst    | 182 A (35C)   |
| Headroom         | Safe (3× load)|

---

## ⚖️ Battery Weight & Placement

- Keep battery near center of frame (below payload)
- Affects Center of Gravity (CoG) → Refer: `/03_MECHANICAL_DESIGN/center_of_gravity.md`
- Use straps + vibration foam for secure mount

---

## 🔋 Alternate Options

| Option           | Pros                        | Cons                       |
|------------------|-----------------------------|----------------------------|
| 3S 6200 mAh      | Lower weight                | Less power for motors      |
| 4S 6200 mAh      | More flight time            | Heavier (~600g)            |
| 6S (if upgraded) | Efficient for T-Motor F40+  | Requires ESC & motor change|

---

> Next: [esc_sizing.md →](./esc_sizing.md)
