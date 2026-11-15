# SOLARIS AI — Phase 0 Risk Register

| ID | Risk | Impact | Mitigation / evidence required | Status |
|---|---|---|---|---|
| R-01 | Wrong sensor range for PV/battery current | Damage or invalid readings | Measure maximum current; check datasheet limits; fuse circuit | OPEN |
| R-02 | Battery chemistry not confirmed | Unsafe charging / battery damage | Read label; use chemistry-compatible controller/BMS | OPEN |
| R-03 | Incorrect voltage divider / ADC scaling | ESP32 damage or inaccurate voltage | Calculate worst-case voltage and power; validate with meter | OPEN |
| R-04 | SOC estimated from voltage alone | Misleading battery status | Use calibrated current integration and battery-specific validation | OPEN |
| R-05 | Forecast weather shown as actual weather | Misleading dashboard | Store source/type, issue time, valid time and retrieval time | OPEN |
| R-06 | Simulated values mistaken for physical telemetry | False project claims | Add explicit mode badge and provenance field | OPEN |
| R-07 | Too little real data for ML | Overfit and unsupported accuracy claims | Start with physics/rules; collect representative data; time-based evaluation | OPEN |
| R-08 | Data leakage in forecasting | Unrealistically high test scores | Use chronological splits and walk-forward validation | OPEN |
| R-09 | Sensor drift/noise or poor mounting | False anomalies | Calibration, filtering, plausibility checks and maintenance log | OPEN |
| R-10 | Stale API data or network loss | Incorrect current status | Timeouts, retries, caching, stale-data indicator and no fake fallback | OPEN |
| R-11 | Scope expansion / unnecessary stack | Delay and complexity | Preserve current stack; justify every new dependency | CONTROLLED |
| R-12 | Unsafe wiring or short circuit | Injury, fire or equipment damage | Low-voltage-only prototype, fuses, enclosure and supervised procedures | OPEN |
| R-13 | Exposed secrets in Git | Account/service compromise | Ignore local .env; commit placeholders only; rotate leaked keys | OPEN |
| R-14 | Unverified claims in poster/demo | Loss of technical credibility | Label simulation, measurement, calculation and prediction separately | CONTROLLED |

Review this register before procurement, wiring, public demonstration and every major architecture change.
