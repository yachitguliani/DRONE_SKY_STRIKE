# 🧠 Flight Controller (FC) Selection

The flight controller (FC) is the brain of the drone — responsible for stabilization, mission execution, sensor integration, and communication with external modules.  
This document explains the reasoning behind choosing a reliable, mission-capable FC for **DRONE_SKY_STRIKE**.

---

## 🛠️ Requirements

| Mission Needs                        | Why It's Important                      |
|--------------------------------------|------------------------------------------|
| Autonomous waypoint missions         | Strike target without manual input       |
| Payload release logic                | Trigger on command or GPS waypoint       |
| High GPS accuracy & telemetry        | Precise flight path + ground communication |
| Redundancy support (IMU, GPS)        | Mission failsafe                         |
| Open firmware customization          | PX4 / ArduPilot for full control         |

---

## ✅ Selected FC: **Pixhawk 4**

| Feature              | Value                                      |
|----------------------|--------------------------------------------|
| Processor            | 32-bit STM32F765                           |
| IMUs                 | 3 × redundant IMUs                         |
| Barometer            | Dual high-res baros                        |
| GPS Compatibility    | uBlox M8N & RTK support                    |
| Ports                | 8 PWM outputs, 6 AUX outputs               |
| Failsafe Options     | Geo-fence, battery failsafe, RC loss       |
| Firmware             | PX4 / ArduPilot (open source)             |

---

## ⚙️ Why Pixhawk 4?

- **Proven stability** in critical UAV systems
- **Extensive documentation + active dev community**
- Supports **DShot, telemetry radios, and servo triggers**
- Can log full flight data for mission debriefing
- Works seamlessly with companion computers if added

---

## 📦 Alternatives

| Model           | Pros                         | Cons                            |
|------------------|------------------------------|----------------------------------|
| CUAV V5+         | More compact, newer hardware | Slightly higher cost             |
| Holybro Durandal | Great performance            | Slightly bulkier                 |
| Pixhawk 6X       | Overkill for this mission    | More expensive, dev board feel   |

---

## 🔌 Companion Modules

- **GPS**: uBlox NEO-M8N (w/ compass)
- **Telemetry**: 433/915 MHz radio for GCS communication
- **RC Input (optional)**: SBUS or PPM receivers
- **Servo Trigger**: AUX OUT channel or relay logic

---

## 🎯 Mission Application

- Upload full mission plan via **QGroundControl / Mission Planner**
- Use **AUTO or GUIDED** mode for strike
- Trigger payload with **waypoint command, auxiliary output, or radio switch**

---

## 🔐 Failsafe Logic (To be detailed in `04_MISSION_LOGIC/auto_mode.md`)

- RTL (Return To Launch) on RC/GPS/Battery fails
- Land or loiter if unable to complete mission
- Optional: Emergency disarm or neutral payload release

---

> Next: Start `02_ELECTRICAL_CALCULATIONS/current_draw_estimation.md`
