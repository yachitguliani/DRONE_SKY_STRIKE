# 🎯 Payload Trigger Logic & Deployment Mechanism

This document describes the logic, design, and electrical/mechanical implementation of the **payload release system** in DRONE_SKY_STRIKE. The mechanism is designed to trigger at a specific mission point via a **servo or relay** controlled by the flight controller.

---

## 🔧 Trigger Methods

### Option A: **Servo-Based Mechanical Release**

- **How it works:**  
  Servo rotates an arm/latch that unlocks the payload bay or releases a spring-loaded pin.

- **Wiring:**  
  - Servo signal to AUX OUT (e.g., Channel 9)
  - Powered by UBEC (5V, 3A min)

- **Mission Command:**  
  - `DO_SET_SERVO` → Channel 9 → PWM: 1000 (locked), 1900 (release)

- **Best For:**  
  - Simple drop mechanisms
  - Reusable systems

---

### Option B: **MOSFET Relay (Electrical Trigger)**

- **How it works:**  
  A low-power digital signal from the Pixhawk triggers a MOSFET switch that powers a solenoid or actuator, releasing the payload.

- **Wiring:**  
  - Relay/MOSFET switch connected to **AUX OUT** (e.g., channel 10)
  - Powered by a separate 5–12V source
  - GND of switch and FC must be shared

- **Mission Command:**  
  - `DO_SET_RELAY` → Channel 0 → ON (release)

- **Best For:**  
  - High-force releases or ignition triggers  
  - Secure one-time deployment

---

## 🛠️ Trigger Mounting Design

| Component         | Mount Location        | Notes                             |
|-------------------|------------------------|------------------------------------|
| Servo             | Under payload bay      | Pulls latch or pin                 |
| Relay/MOSFET      | Inside main fuselage   | Lightweight, isolated from payload |
| Payload Bay       | Top-mounted cylinder   | Drops straight down (vertical)     |

---

## 🧪 Testing Procedure

1. Power drone without propellers
2. Load servo test mission in QGroundControl
3. Confirm:
   - Servo PWM reaches correct values
   - Relay toggles with `DO_SET_RELAY`
4. Test trigger mechanism with **dummy weight** first
5. Add small vibration damping if servo gets stuck

---

## 🧠 Additional Logic (Advanced)

- Add **manual trigger override** via RC switch (mapped to AUX)
- Add **time delay** or conditional trigger (e.g., release only after speed < X m/s or at GPS coordinate Y)
- Log trigger timestamp using Pixhawk onboard logging

---

## 🔐 Safety Notes

- Always ground test trigger 10+ times
- Secure wiring against vibration
- Use redundant mechanical safety (clip/pin) during transport
- Never arm drone with live payload unless in mission zone

---

> Next: [05_WIRING_AND_PLACEMENT/component_layout.md →](../05_WIRING_AND_PLACEMENT/component_layout.md)
