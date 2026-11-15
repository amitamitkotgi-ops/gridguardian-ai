---
name: battery-systems-safety
description: Battery chemistry, solar charge control, SOC estimation, DC protection and safe low-voltage prototype design for SOLARIS AI.
---

# Battery Systems & Safety Skill

## Before design
Confirm battery chemistry, nominal voltage, capacity, maximum charge/discharge current, permitted charge voltage/current, temperature limits and manufacturer instructions.

## Safety rules
- Use a charge controller matched to the battery chemistry and PV input.
- Retain the battery BMS/protection required by the battery manufacturer.
- Never bypass BMS, fuses or charge controller protections.
- Fuse conductors close to the energy source and size wiring/connectors for expected fault and operating current.
- Keep student prototype low-voltage DC; do not connect to exposed mains.
- Do not make wiring changes while energized.
- Never power ESP32 directly from an unregulated battery rail; use a correctly rated regulated converter.

## Measurement and estimation
- Measure charge and discharge current with known sign convention and topology.
- Voltage-only SOC is unreliable under variable load and temperature.
- Coulomb counting requires current offset calibration, known initial SOC, time integration and periodic correction.
- Do not claim battery SOH or remaining useful life without validated reference data and an appropriate method.
- Add over/under-voltage, over-current and temperature alarms as monitoring features; do not imply the software replaces hardware protection.
