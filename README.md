
# 🚁 DRONE_SKY_STRIKE

**DRONE_SKY_STRIKE** is an open-source, military-grade drone prototype designed for **precision payload delivery**.  
This repo documents every technical layer — from **CAD modeling** and **component selection** to **current, thrust, and flight time calculations** — enabling you to build, simulate, or optimize high-performance UAVs for defense and strategic applications.

> 💥 The top cylindrical bay is engineered to carry mission-critical payloads, enabling tactical deployment and high-impact delivery.

---

## 📌 What's Inside

- 🧠 Component Selection (Motors, ESCs, Battery, Flight Controller)
- ⚡ Electrical Load & Power Distribution Calculations
- ⚙️ Weight Distribution & Center of Gravity Analysis
- 🛠️ Full CAD Design and STL Files
- 📡 Mission Logic & Payload Triggering
- 📈 Flight Time and Performance Modeling

---

## 🧱 Repository Structure

| Folder                     | Contents                                                  |
|----------------------------|-----------------------------------------------------------|
| `01_COMPONENTS_SELECTION`  | Calculations for thrust, prop sizing, battery & FC        |
| `02_ELECTRICAL_CALCULATIONS` | Current draw, ESC ratings, power budget, wire gauge      |
| `03_MECHANICAL_DESIGN`     | Weight analysis, CAD files, frame load distribution       |
| `04_MISSION_LOGIC`         | Auto-flight modes, payload trigger logic                  |
| `05_WIRING_AND_PLACEMENT`  | Component placement, Pixhawk pinout, wiring diagrams      |

---

## 🔩 Prototype Specs

| Spec                    | Value                           |
|-------------------------|----------------------------------|
| Frame Material          | Carbon Fiber Composite           |
| Max Takeoff Weight      | ~2.5 kg (incl. ~0.5 kg payload)  |
| Motors                  | 700–900 KV (4x)                  |
| Propellers              | 10x4.5” or 11x4.7” Carbon Fiber   |
| Battery                 | 4S 5200 mAh LiPo (≥35C)          |
| Flight Controller       | Pixhawk 4 or CUAV V5+            |
| Flight Time (est.)      | ~10–12 minutes                   |

---

## 🖼️ CAD Preview

> Drone visual with cylindrical payload bay (SolidWorks)  
> 📍 [CAD Files](./03_MECHANICAL_DESIGN/CAD_PREVIEW)

![Drone Render](./03_MECHANICAL_DESIGN/CAD_PREVIEW/parts_exploded.png)

---

## ⚔️ Tactical Use-Case

- Strategic target engagement
- Autonomous strike missions
- Secure payload release (mechanical/electro trigger)

---

## 🌐 Linked Repositories

- 📘 [DRONOPEDIA_1.0](https://github.com/yachitguliani/DRONOPEDIA_1.0): Drone basics & learning stack
- 🔧 `DRONE_SKY_STRIKE`: Complete build documentation of the prototype

---

## 🤝 Contributions

Feel free to fork, suggest improvements, or collaborate.  
This project is built to **push open UAV development into real-world problem-solving** — especially in the defense and surveillance sectors.

> **Rusty Never Stops.** Let's build what's next.  
> — Yachit Guliani

---

## 📎 Tags

`#DroneTech` `#UAVPrototype` `#DefenseTech` `#Pixhawk` `#OpenSourceHardware` `#RustyNeverStops` `#SkyStrike`
