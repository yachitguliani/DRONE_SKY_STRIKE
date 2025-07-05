# ⚡ Power Budget & Distribution Plan

A well-defined power budget ensures that every component in **DRONE_SKY_STRIKE** receives stable, sufficient voltage and current. This document details how power is distributed across the system, including margins, losses, and recommendations.

---

## 🧱 System Power Overview

| Component           | Voltage    | Avg Power (W) | Max Power (W) |
|---------------------|------------|----------------|----------------|
| 4× Brushless Motors | 14.8 V     | 600 W          | 1000+ W        |
| Flight Controller   | 5 V        | 1.5–2 W        | 3 W            |
| GPS + Compass       | 5 V        | 0.75 W         | 1 W            |
| Telemetry Radio     | 5 V        | 1 W            | 1.5 W          |
| Servo (Payload)     | 5 V        | 1.5–2 W (peak) | 2.5 W          |

---

## 🔋 Total Power Requirements

| Mode     | System Draw (A) | Power Use (W) |
|----------|------------------|----------------|
| Hover    | ~45 A            | ~666 W         |
| Cruise   | ~35 A            | ~518 W         |
| Peak     | ~70 A            | ~1036 W        |

Battery capacity: **4S 5200mAh (76–80 Wh usable)**  
Safe discharge current: **> 182 A (35C)**  
✅ Battery is sufficient under all conditions with ~2× margin.

---

## 🔌 Power Distribution Setup

### 🔸 Main Power Line

- **XT60 or XT90 connector**
- 12 AWG silicon wire for main battery leads
- Connects to PDB (Power Distribution Board)

### 🔸 ESC Power Feeds

- ESCs draw directly from PDB
- Grounded through frame or common bus
- 14–16 AWG wire from PDB to each ESC

### 🔸 5V Rail (Low Power Electronics)

- Powered by **5V BEC** or **Pixhawk Power Module**
- Powers:
  - FC
  - GPS
  - Telemetry
  - Servo (momentarily)

### 🔸 Servo Trigger

- Should use **separate UBEC** (5V, 3A recommended)
- Avoid powering servos directly from FC if servo is high torque

---

## 📉 Power Loss Consideration

| Source               | Expected Loss (%) |
|----------------------|-------------------|
| ESC Efficiency       | ~10–12%           |
| Wire Resistance      | ~2–3%             |
| Heat Loss in BEC     | ~5%               |
| Total Est. Loss      | ~15–20%           |

➡️ Realistic power budget = **~1000 W required** under peak  
➡️ Actual usable = **~80–85%** of battery energy

---

## 🧠 Safety Recommendations

- Add voltage and current sensors to Pixhawk for live monitoring
- Log battery data per mission
- Never let LiPo go below **3.5 V/cell**
- Keep **20% reserve** in battery for landing and safety

---

> Next: [wire_gauge_calc.md →](./wire_gauge_calc.md)
