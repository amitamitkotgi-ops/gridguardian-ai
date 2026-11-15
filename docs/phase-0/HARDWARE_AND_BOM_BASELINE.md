# SOLARIS AI — Hardware & BOM Baseline

**Status:** Preliminary engineering candidate list — not a purchase order.

## Existing project baseline
The current GridGuardian AI README describes a 20 W solar panel, 12 V 7 Ah battery, ESP32, charge controller, ACS712 current sensor, voltage sensing, temperature sensor, OLED, relay, buzzer and LM2596 buck converter. These are inherited project notes, not a verified as-built inventory.

## Candidate system blocks

| Block | Candidate | Selection rule / open question |
|---|---|---|
| PV source | 20 W panel (existing project note) | Confirm Voc, Vmp, Isc, Imp from label |
| Controller | ESP32 development board | Confirm exact module, supply and GPIO |
| PV measurement | DC voltage + current sensing | Select range and topology from maximum current |
| Battery measurement | Voltage + bidirectional current sensing | Sensor must support charge and discharge current |
| Panel temperature | DS18B20 | Mount to backsheet; do not call it cell temperature |
| Ambient conditions | BME280 | Shield from direct sun and panel heat |
| Irradiance | Reference cell / suitable irradiance sensor (optional) | Needed for stronger irradiance-normalized analysis |
| Storage | Existing note: 12 V 7 Ah | Confirm chemistry, charge profile and BMS/protection |
| Charge controller | Compatible solar charge controller | Confirm PV input, battery chemistry and current ratings |
| DC load | Fused low-voltage DC load | Size for safe demonstrator and energy budget |
| Protection | Fuses, holders, wiring, terminals, enclosure | Select from worst-case current and conductor sizing |
| Power conversion | Regulated DC-DC converter | Confirm input/output voltage, current and thermal rating |

## Required measurements before purchasing
1. Panel nameplate: Voc, Vmp, Isc, Imp, rated power and tolerance.
2. Battery label: chemistry, nominal voltage, capacity, maximum charge/discharge current and charging profile.
3. Charge controller: supported chemistry, PV input limits, charge current and load output limits.
4. Expected maximum current in every measurement path.
5. ESP32 board input requirements and sensor logic levels.
6. Cable length, wire gauge, connector type, fuse location and enclosure plan.

## Sensor selection notes
- Do not assume INA219 is suitable for every PV/battery path; its bus-voltage and shunt-current limits must fit the actual circuit.
- ACS712 is a candidate only after checking current range, supply, sensitivity, offset, noise and calibration.
- A resistor divider must be designed for maximum possible input voltage, ADC range, resistor power and fault conditions.
- Battery SOC cannot be reliably inferred from voltage alone under changing load. Prefer calibrated coulomb counting / a suitable battery monitor, with battery-specific validation.
- Do not route panel or battery current through ESP32 board traces or a breadboard.

## Safe power-flow concept
PV panel → compatible solar charge controller → protected battery → fused DC load.

ESP32 and sensors receive power from a properly regulated supply. Grounds and measurement references must follow the selected sensor topology and manufacturer's instructions.

## Procurement gate
No component should be marked APPROVED TO BUY until its datasheet/nameplate, electrical limits, compatibility and safety role have been checked. This document intentionally does not invent prices or final ratings.
