# SOLARIS AI

> **MONITOR. PREDICT. OPTIMIZE. STORE.**

**AI-Powered Solar Plant Monitoring, Energy Forecasting and Storage Management System**

SOLARIS AI is an engineering demonstrator that aims to combine low-voltage solar PV monitoring, weather intelligence, solar generation estimation and forecasting, battery monitoring, anomaly indicators and an operator dashboard.

> **Repository transition note:** This repository originated as the GridGuardian AI solar-battery monitoring prototype. The current Phase 0 branch establishes the SOLARIS AI project identity and engineering baseline. Existing application code and its simulation status must be audited before feature claims or architecture changes are made.

## Project status

**Current milestone: Phase 0 — Project Foundation & Engineering Readiness (IN PROGRESS)**

Phase 0 defines the scope, architecture baseline, hardware assumptions, safety rules, engineering skills, risks and development workflow. It does not claim that physical hardware, weather integration, forecasting or AI models have been implemented or validated.

## Intended system architecture

```
PV Panel + Protected Battery + Sensors
                 |
                 v
       ESP32 Data Acquisition
                 |
          Wi-Fi Telemetry
                 |
                 v
       Existing FastAPI Backend <---- Weather API
                 |
                 v
             SQLite
                 |
                 v
       Solar / AI Intelligence
                 |
                 v
      Existing SOLARIS Dashboard
```

The existing architecture is to be extended, not replaced without a documented requirement. No unnecessary frameworks, brokers, databases or infrastructure should be introduced.

## Project capabilities (planned scope)

- Solar voltage, current, power and energy monitoring.
- Panel backsheet temperature and ambient condition monitoring.
- Weather context with source and forecast/observation distinction.
- Physics-based solar estimates and next-hour / next-day forecasts.
- Battery voltage, current, charging and discharging monitoring.
- Battery SOC estimation after chemistry and measurement method are verified.
- Data-quality checks, anomaly indicators and evidence-based recommendations.
- Historical charts, export and system-health dashboard.

## Data integrity

Every value must be identifiable as **measured**, **observed**, **forecast**, **calculated**, **predicted** or **simulated**. Synthetic telemetry must never be presented as a physical sensor measurement. Forecasts are estimates, not guaranteed future values.

Store timestamps in UTC and display local time in Asia/Kolkata. Use explicit units and retain source, retrieval time, valid time and quality information.

## Phase 0 documentation

| Document | Purpose |
|---|---|
| [Phase 0 Foundation](docs/phase-0/PHASE_0_FOUNDATION.md) | Vision, scope, architecture, safety and exit criteria |
| [Hardware & BOM Baseline](docs/phase-0/HARDWARE_AND_BOM_BASELINE.md) | Candidate hardware and procurement checks |
| [Skills & Learning Roadmap](docs/phase-0/SKILLS_AND_LEARNING_ROADMAP.md) | Professional engineering skills and practical evidence |
| [Risk Register](docs/phase-0/RISK_REGISTER.md) | Technical, data and safety risks |
| [Development Environment](docs/phase-0/DEVELOPMENT_ENVIRONMENT.md) | Local setup and baseline verification |

## Project-specific Antigravity skills

Skills are stored in `.agents/skills/`:

- `solaris-project-engineering` — project-wide architecture and delivery rules.
- `solar-pv-engineering` — PV measurements, calculations and modelling.
- `esp32-iot-telemetry` — firmware, sensors and telemetry.
- `solar-data-ml-forecasting` — weather, time-series ML and evaluation.
- `weather-api-data-quality` — API provenance, caching and validation.
- `battery-systems-safety` — battery design, protection and SOC limitations.
- `testing-and-verification` — unit, integration and hardware verification.
- `technical-documentation` — traceability and engineering records.

## Safety

This project is intended as a low-voltage DC educational prototype. Use a chemistry-compatible charge controller and battery protection, correctly rated fuses and wiring, and regulated power for the ESP32. Do not connect the prototype to exposed mains. Confirm component nameplates and datasheets before purchasing or wiring.

## Development principles

1. Inspect existing code and Git status before modifying anything.
2. Make small, reviewable changes.
3. Preserve the existing stack unless a requirement justifies a change.
4. Add tests for calculations, data schemas and failure cases.
5. Document assumptions and limitations.
6. Report test results only when the tests have actually been run.

## Phase 0 exit gate

Phase 0 is complete when the repository audit, scope, hardware ratings, battery chemistry/protection, telemetry schema, skills plan, development workflow, budget and safety review are documented and reviewed.

---

**Project:** SOLARIS AI  
**Domain:** Renewable Energy · IoT · Embedded Systems · AI/ML  
**Repository milestone:** `solaris-ai/phase-0-foundation`
