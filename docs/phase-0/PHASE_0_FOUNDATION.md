# SOLARIS AI — Phase 0: Project Foundation & Engineering Readiness

**Project:** SOLARIS AI  
**Full title:** AI-Powered Solar Plant Monitoring, Energy Forecasting and Storage Management System  
**Tagline:** MONITOR. PREDICT. OPTIMIZE. STORE.  
**Status:** IN PROGRESS — planning baseline  
**Baseline date:** 2026-11-15

## 1. Purpose
Phase 0 establishes the engineering baseline before implementation changes. It confirms project identity, scope, architecture boundaries, technical assumptions, safety constraints, required skills, development workflow and verification criteria.

Phase 0 does not claim that physical hardware, weather integration, forecasting, battery estimation or AI models are already implemented or validated.

## 2. Project vision
Build a low-voltage solar demonstrator that measures real PV and battery behaviour, combines measurements with clearly labelled weather information, estimates and forecasts solar generation, detects unusual operating patterns and presents useful information in a professional dashboard.

Every value must be classified as one of:
- **Measured:** directly read from a physical sensor.
- **Observed weather:** provider observation/current-condition product, with provider and timestamp.
- **Forecast weather:** numerical weather prediction, not a future measurement.
- **Calculated:** derived from inputs using a documented equation.
- **Predicted:** model output, with model version and forecast horizon.
- **Simulated:** generated test data, visibly labelled as simulation.

## 3. Problem statement
Small solar installations and educational prototypes often provide limited visibility into generation, environmental conditions, battery behaviour and expected future output. SOLARIS AI combines low-cost sensing, weather context, engineering calculations, forecasting, anomaly indicators and an operator dashboard in one demonstrator.

## 4. Scope

### Included in the intended prototype
1. PV voltage, current, power and accumulated energy monitoring.
2. Panel backsheet temperature and ambient temperature/humidity monitoring.
3. Weather integration with source, retrieval time, units and stale-data handling.
4. Solar generation estimates and next-hour / next-day energy forecasts.
5. Battery voltage/current and charge/discharge monitoring.
6. Battery SOC estimation only after battery chemistry, sensor topology and calibration are confirmed.
7. Rule-based alarms and data-quality checks.
8. ML anomaly detection and forecasting only after suitable data and evaluation baselines exist.
9. Dashboard, historical charts, export and system-health visibility.

### Excluded from the initial prototype
- Direct connection to grid or exposed mains.
- Utility-scale plant control or inverter control.
- Claims of certified battery SOH, exact remaining useful life or guaranteed fault prediction.
- Industrial certification or production-grade claims without validation.
- Multi-site fleet management before a single-node demonstrator is validated.

## 5. Architecture baseline
PV panel + protected battery/charge controller + sensors  
→ ESP32 acquisition and local validation  
→ Wi-Fi telemetry  
→ existing FastAPI backend  
→ SQLite persistence  
→ calculation / weather / AI services  
→ existing dashboard and WebSocket updates.

Weather data is ingested by the backend on a separate schedule; it is not sampled at the ESP32 telemetry interval.

**Architecture rule:** extend the existing project only where required. Do not introduce React, Next.js, Redis, Kafka, Docker, Kubernetes, microservices or a new database without a documented requirement and approval.

## 6. Technical assumptions requiring verification

| Item | Working assumption | Verification required |
|---|---|---|
| PV source | Existing README describes a 20 W panel | Read label: Voc, Vmp, Isc, Imp |
| Storage | Existing README describes a 12 V, 7 Ah battery | Confirm chemistry, charge profile, BMS/protection and condition |
| Controller | ESP32 | Confirm exact board and GPIO/power constraints |
| Current sensing | Existing README mentions ACS712 | Select range/topology after maximum current is known |
| Voltage sensing | Voltage divider / suitable monitor | Verify range, resistor power, ADC scaling and calibration |
| Panel temperature | DS18B20 candidate | Mount on rear sheet; label as backsheet temperature |
| Ambient conditions | BME280 candidate | Keep away from panel heat and direct sun |
| Backend | FastAPI | Audit existing code before changing |
| Database | SQLite | Preserve current schema unless migration is justified |
| Weather | Open-Meteo candidate | Select endpoint, variables, timezone and update policy |
| ML | scikit-learn baseline | No accuracy claims without traceable data and time-based evaluation |

## 7. Measurement and data contracts
Every telemetry record should carry device_id, plant_id, UTC timestamp, parameter values and units, source/mode, quality flags, and firmware/schema version where practical.

Use SI units consistently: V, A, W, Wh, kWh, °C, W/m², %, hPa and km/h. Store timestamps in UTC and display in Asia/Kolkata.

Never silently replace missing sensor/weather values with fabricated values. Mark missing, stale, invalid, estimated and simulated values explicitly.

## 8. Engineering safety baseline
- Keep the student prototype low-voltage DC; do not connect it to exposed mains.
- Never connect a battery directly to ESP32 supply pins.
- Use a correctly rated charge controller and battery protection/BMS for the confirmed chemistry.
- Add correctly rated fuses close to energy sources; protect against reverse polarity and short circuits.
- Verify panel open-circuit voltage and short-circuit current against every downstream component limit.
- De-energize before rewiring; use insulated tools and supervised lab procedures.
- A panel backsheet probe is not a cell-junction temperature measurement.

## 9. Phase 0 exit criteria
- [ ] Existing repository and code paths audited.
- [ ] Project scope and non-goals approved.
- [ ] Hardware nameplates and sensor ranges recorded.
- [ ] Battery chemistry and protection strategy confirmed.
- [ ] System block diagram and telemetry schema reviewed.
- [ ] Data provenance rules implemented in the design.
- [ ] Skills and learning plan accepted.
- [ ] Development environment and test commands documented.
- [ ] Budget and procurement list reviewed.
- [ ] Safety review completed before physical wiring.

## 10. Immediate next actions
1. Audit dashboard, simulator, firmware and database.
2. Confirm this repository is the canonical SOLARIS AI codebase.
3. Record exact panel, battery, charge controller and sensor part numbers.
4. Freeze telemetry schema and hardware measurement topology.
5. Start Phase 1 requirements after the foundation is reviewed.

## 11. Status discipline
Use NOT STARTED, IN PROGRESS, BLOCKED, VERIFIED or DEFERRED. A feature is not VERIFIED until its acceptance test and evidence are recorded.
