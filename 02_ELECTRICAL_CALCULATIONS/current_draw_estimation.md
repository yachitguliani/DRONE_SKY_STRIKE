# 🔌 Current Draw Estimation

Estimating the current draw is essential for safe operation, correct battery sizing, wire gauge selection, and ESC reliability. This file documents the expected **hover, cruise, and peak current usage** of DRONE_SKY_STRIKE under full payload conditions.

---

## 📦 System Overview

| Component         | Quantity | Avg Current (A) | Max Current (A) |
|------------------|----------|------------------|------------------|
| Brushless Motors | 4        | 10–12 A each     | 15–18 A each     |
| Flight Controller| 1        | 0.5 A            | 1 A              |
| GPS Module       | 1        | 0.15 A           | 0.2 A            |
| Telemetry Radio  | 1        | 0.2 A            | 0.3 A            |
| Servo/Trigger    | 1        | 0.3 A (on use)   | 0.5 A            |

---

## ⚙️ Calculated Values

### 🔸 Hover Current (Avg)

`4 motors × 10 A = 40 A`  
Total system ≈ **42–45 A**

---

### 🔸 Peak Load Current

`4 motors × 17 A = 68 A`  
Total system ≈ **70–72 A**

> ⚠️ ESCs and battery should handle this for at least 10 seconds.

---

### 🔸 Cruise/Loiter Current

`~8 A per motor × 4 = 32 A`  
System total: **~34–36 A**

---

## 🪫 Energy Consumption

- **Battery:** 4S 5200 mAh = 14.8 V × 5.2 Ah = **76.96 Wh**
- **Avg Power Use:** ~600–800 W (depending on flight profile)

| Mode    | Draw (A) | Time on 5200mAh |
|---------|----------|-----------------|
| Hover   | ~45 A    | ~6.9 min        |
| Cruise  | ~35 A    | ~8.9 min        |
| Max     | ~70 A    | ~4.5 min        |

> ✅ We recommend budgeting **10–15% buffer** and keeping **~10 mins flight envelope**.

---

## ⚠️ Design Implications

- ESCs must be rated **≥30 A continuous**
- Battery should have **≥35C discharge rate**
- Use high-efficiency props to reduce load at hover
- Log current data using telemetry for flight analysis

---

> Next: [power_budget.md →](./power_budget.md)
