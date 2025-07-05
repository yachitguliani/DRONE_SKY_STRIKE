# ⚡ ESC Sizing & Selection

The Electronic Speed Controller (ESC) is a critical interface between the flight controller and brushless motors. This document outlines how we selected an ESC suitable for **DRONE_SKY_STRIKE**, based on motor specs, battery voltage, and current load.

---

## ✅ Requirements

- Handle peak current from each motor (~15–18 A)
- Support 4S LiPo voltage (14.8V)
- Compatible with high-frequency signals (PWM / DShot)
- Thermal headroom for safety and durability

---

## 📊 ESC Calculation

| Parameter             | Value             |
|------------------------|------------------|
| Motor Max Current      | ~18 A             |
| Safety Factor          | × 2               |
| Recommended ESC Rating | ≥30 A             |

---

## 🔧 Selected ESC

| Feature           | Value                                  |
|------------------|------------------------------------------|
| Model            | **BLHeli_S 30A / DShot 600 ESC**         |
| Current Rating   | 30 A continuous, 35–40 A burst           |
| Voltage Support  | 2–4S LiPo                               |
| Protocol         | PWM / OneShot / Multishot / DShot       |
| Weight           | ~8–12g per unit                         |
| Features         | Smooth throttle response, fast refresh  |

---

## ⚙️ Why 30A ESC?

- Provides **2x margin** over peak draw (~18 A)  
- Allows **headroom** for emergency throttle spikes (e.g. during quick ascent or post payload-drop)
- Prevents **thermal shutdowns** under load
- Supports **modern FC firmware (ArduPilot, PX4)**

---

## 🔥 Thermal Safety Notes

- Mount ESCs on **arms for better airflow**
- Use **heat-shrink tubing** with open ends for cooling
- Avoid clustering ESCs near power distribution board (PDB)

---

## 🚨 Important Guidelines

- Use **BEC-free (OPTO) ESCs** if you’re powering the FC separately
- All ESCs must be **calibrated** before first flight
- Sync **firmware versions** if using BLHeli configurator

---

## 🔁 Alternatives

| Model                    | Comments                         |
|--------------------------|----------------------------------|
| Hobbywing XRotor 30A     | Reliable, high-quality           |
| T-Motor F30A ESC         | Compact & powerful               |
| EMAX BLHeli-S 35A        | Great for quad setups            |

---

> Next: [fc_selection.md →](./fc_selection.md)
