# 📡 Auto Mode & Mission Planning (PX4/ArduPilot)

This file explains how **DRONE_SKY_STRIKE** executes **autonomous missions** using waypoint navigation, return-to-launch (RTL), and payload delivery using PX4/ArduPilot mission modes.

---

## 🧠 Flight Modes Overview

| Mode           | Purpose                                 | Trigger Type     |
|----------------|------------------------------------------|------------------|
| STABILIZE      | Manual angle control                     | Pilot input      |
| LOITER         | Hover at current GPS location            | RC/GCS override  |
| AUTO           | Fully autonomous waypoint navigation     | Mission plan     |
| RTL            | Return to home (failsafe or end mission) | Auto/RC          |
| GUIDED         | Real-time movement commands from GCS     | Companion/GCS    |

---

## 🎯 Mission Flow (Example)

1. **Takeoff**  
   → AUTO takeoff at defined altitude (e.g., 10m)

2. **Waypoint Navigation**  
   → Fly to 2–3 GPS coordinates using AUTO mode

3. **Payload Deployment**  
   → Trigger servo at final waypoint

4. **Post-Strike Return**  
   → Automatically RTL and land at home location

---

## 🔗 Mission Planning Tools

- [Mission Planner](https://ardupilot.org/planner/)
- [QGroundControl](https://docs.qgroundcontrol.com)
- Plan with:
  - Waypoints (NAV_WAYPOINT)
  - DO_SET_SERVO (for trigger)
  - RTL or LAND command at end

---

## ⚙️ Mission Parameters

| Parameter                | Value                        |
|--------------------------|-------------------------------|
| Takeoff Altitude         | 10–20 meters                 |
| Waypoint Spacing         | ≥10m (for safety)            |
| Payload Drop Point       | Final waypoint or Loiter      |
| Return Behavior          | RTL with 20% battery margin   |

---

## 🔄 Triggering Payload Mechanism

### Option A: **Servo (Pin Trigger)**

- Connect servo to **AUX OUT** (Pixhawk)
- Use `DO_SET_SERVO` in mission plan
- Example:  
  `Set Servo #9 → PWM = 1900 → Drop`

### Option B: **Relay (MOSFET Switch)**

- Use `DO_SET_RELAY → ON` to fire small solenoid or FET switch
- More secure for electrical detonation-based triggers

---

## 🛑 Failsafe Logic

| Failsafe Condition  | Action Taken       |
|----------------------|--------------------|
| GPS Loss             | Hover / Land       |
| RC Signal Loss       | RTL                |
| Low Battery (<20%)   | RTL or LAND        |
| Motor Failure        | Disarm (unsafe)    |

---

## 🔐 Security Notes

- Use **GCS lockout** or switch-based arming to prevent accidental payload release
- Arm only after safety checks complete
- Always **simulate** mission in SITL (software-in-the-loop) before live deployment

---

> Next: [payload_trigger_logic.md →](./payload_trigger_logic.md)
