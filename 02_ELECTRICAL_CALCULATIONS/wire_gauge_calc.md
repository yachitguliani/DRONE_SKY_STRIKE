# 🔌 Wire Gauge Selection & Voltage Drop Estimation

Wire gauge plays a crucial role in maintaining **efficient power delivery**, avoiding voltage drops, and preventing overheating. This file outlines the recommended wire sizes for each part of the drone based on current draw and length.

---

## 📐 Wire Gauge Selection Formula

We use the **voltage drop formula**:

> `V_drop = (2 × L × I × R_per_meter)`

Where:  
- `L` = Length of wire (one-way, in meters)  
- `I` = Current (in Amps)  
- `R_per_meter` = Resistance of wire per meter (based on AWG)  
- Multiply by 2 to account for the return path (forward + ground)

---

## 🔧 Recommended Wire Gauges

| Application           | Current (A) | Length (m) | Recommended Wire | V Drop (Approx) |
|------------------------|-------------|------------|------------------|------------------|
| Battery to PDB         | 60–70 A     | ~0.3 m     | **12 AWG**       | ~0.2 V           |
| PDB to ESCs            | 15–18 A     | ~0.2 m     | **16 AWG**       | ~0.1–0.15 V      |
| ESC to Motors          | 15–18 A     | ~0.1 m     | **16 AWG**       | Minimal          |
| BEC to FC/GPS/Radio    | <2 A        | ~0.2 m     | **22–24 AWG**    | Negligible       |
| Servo (Payload Trigger)| ~2–3 A      | ~0.3 m     | **20 AWG**       | <0.1 V           |

---

## 📊 Wire Resistance Reference Table

| AWG  | Max Amps | Ohm/m (approx) | Usage                      |
|------|----------|----------------|-----------------------------|
| 10   | 85 A     | 0.00328 Ω/m     | Heavy-duty drones           |
| 12   | 70 A     | 0.00521 Ω/m     | Battery main lines          |
| 14   | 50 A     | 0.00829 Ω/m     | Mid-range power             |
| 16   | 35 A     | 0.01317 Ω/m     | ESC power wires             |
| 18   | 20 A     | 0.02095 Ω/m     | LED/low-load ESC            |
| 22–24| <7 A     | 0.05–0.085 Ω/m  | FC, GPS, RC receiver, etc.  |

---

## ⚠️ Tips & Best Practices

- **Shorter wires = better efficiency**
- Use **flexible silicone insulation** for vibration resistance
- Twist motor wires to reduce EMI
- Avoid mixing wire types/brands with different resistance levels

---

## 🔐 Safety Note

- Never undersize battery wires — risk of fire and brownouts
- Always solder with high-quality flux-core wire
- Add fuses or circuit breakers for field use prototypes

---

> With this, electrical calculations are complete.  
> Next up: [`03_MECHANICAL_DESIGN/weight_distribution.md`](../03_MECHANICAL_DESIGN/weight_distribution.md)
