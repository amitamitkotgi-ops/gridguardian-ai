# SOLARIS AI — Professional Skills & Learning Roadmap

This project needs applied engineering skills, not just more libraries. Learn each skill alongside a small project deliverable.

## Priority 1 — Required for the first working prototype

| Skill area | What to learn | Practical evidence |
|---|---|---|
| Solar PV fundamentals | I–V / P–V curves, Voc, Vmp, Isc, Imp, irradiance, temperature coefficient, tilt/azimuth | PV calculation notebook and panel datasheet review |
| DC electrical safety | Polarity, fuses, wire sizing, grounding, battery protection, charge controllers | Reviewed low-voltage wiring diagram and safety checklist |
| ESP32 embedded development | GPIO, ADC limitations, I2C, 1-Wire, Wi-Fi, watchdogs, non-blocking loops | Sensor firmware with calibration and error states |
| Sensor engineering | Range, accuracy, resolution, calibration, noise, sampling and filtering | Calibration log and sensor validation test |
| Python engineering | Virtual environments, typing, logging, configuration and packaging | Reproducible backend setup |
| FastAPI/API design | Pydantic schemas, validation, error handling, health endpoints and WebSockets | Versioned telemetry API and API tests |
| Data engineering | Time-series records, UTC timestamps, units, provenance and stale data | Validated telemetry schema and data-quality tests |
| Git/GitHub | Branches, commits, pull requests, issues and changelogs | Small reviewable commits |

## Priority 2 — Forecasting and intelligence

| Skill area | What to learn | Practical evidence |
|---|---|---|
| Solar weather data | GHI, DNI, DHI, GTI, cloud cover, forecast vs reanalysis vs observation | Weather ingestion with source and retrieval timestamp |
| PV performance modelling | Temperature correction, system losses, orientation and module parameters | Physics-based baseline with stated assumptions |
| Statistics | Time-based train/test split, leakage, residuals, uncertainty and seasonality | Baseline evaluation report |
| ML forecasting | Persistence baseline, linear/tree models, feature engineering and walk-forward validation | MAE/RMSE comparison against naive baseline |
| Anomaly detection | Engineering rules first, then Isolation Forest or justified alternatives | Labelled test cases and false-alarm analysis |
| Battery fundamentals | Battery chemistry, charge stages, SOC, coulomb counting and temperature effects | Battery-specific SOC validation plan |
| Dashboard engineering | Accessible visual hierarchy, responsive layout, charts and status states | Operator dashboard acceptance checklist |

## Priority 3 — Professionalization
- Automated tests and CI checks.
- Secure configuration and secret handling.
- Authentication if remote access is introduced.
- Logging, monitoring, backup and recovery.
- Technical writing, architecture diagrams and test reports.
- Calibration traceability and repeatable experiments.
- Threat modelling for exposed network interfaces.
- Deployment and release discipline.

## Recommended learning order
1. Electrical safety + solar PV basics.
2. Read actual panel, battery and controller datasheets.
3. ESP32 and sensor interfacing.
4. Python and FastAPI fundamentals.
5. Telemetry schema, database and tests.
6. Weather data and solar physics.
7. Forecasting evaluation and anomaly detection.
8. Battery estimation and dashboard integration.
9. Security, deployment and documentation.

## Learning rule
Do not collect certificates or install tools just to make the stack look impressive. Each skill must produce a tested project artifact. Prefer official documentation and datasheets over random tutorials.
