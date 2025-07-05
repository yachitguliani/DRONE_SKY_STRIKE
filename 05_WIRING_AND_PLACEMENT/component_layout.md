# 🧭 Component Placement & Internal Layout

This document explains how all critical components are arranged on the DRONE_SKY_STRIKE frame for **stability, cooling, signal clarity, and mission reliability**.

---

## 🧱 Layout Strategy

Our design follows three principles:

1. **Balanced Weight Distribution**  
   – CoG centered for stable hover

2. **Signal Interference Reduction**  
   – GPS, telemetry, and ESCs are separated

3. **Ease of Maintenance**  
   – Modular wiring and plug-n-play connectors

---

## 🔧 Top-Down View (Simplified)
                   [GPS + Compass]
                          ↑
                ┌────────────────────┐
                │     Payload Bay    │
                └────────────────────┘
                ┌────────┬──────────┐
                │ Motor  │  Motor   │
                │  (FL)  │   (FR)   │
                └──┬─────┴─────┬────┘
                   │           │
              [ESC - L]     [ESC - R]
                   │           │
                ┌──┼────┬┬─────┼──┐
                │        FC       │
                └────┬────┬──────┘
                     │   │
                [Battery Pack]
                     ↓
                ┌─────────────┐
                │ Motor (BL)  │
                │  [ESC]      │
                └─────────────┘
                ┌─────────────┐
                │ Motor (BR)  │
                │  [ESC]      │
                └─────────────┘
FC: Pixhawk / Flight Controller
ESC: Electronic Speed Controller
GPS: Mounted on mast away from power components
Payload: Centrally placed above the FC, balanced with battery underneath

