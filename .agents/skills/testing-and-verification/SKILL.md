---
name: testing-and-verification
description: Test strategy, acceptance criteria, calibration evidence and release verification for SOLARIS AI.
---

# Testing & Verification Skill

## Test layers
1. Unit tests for calculations, conversions, schemas and validation.
2. Integration tests for API, database and weather-provider adapter (mock external calls).
3. Simulator tests for realistic operating states and explicit simulation labels.
4. Hardware-in-loop checks when physical sensors and board are available.
5. End-to-end dashboard checks from data ingestion to visible timestamped values.

## Test discipline
- Define acceptance criteria before implementation.
- Test nominal, boundary, missing, stale, malformed and failure cases.
- Use deterministic fixtures; do not rely on live weather APIs in routine unit tests.
- Use chronological splits for time-series model evaluation.
- Compare forecasting models with a simple baseline.
- Record calibration instruments, date, reference values, measured values and error.
- Never report a test as passed unless it was actually run; include command and result.
- Separate software simulation evidence from physical hardware validation.

## Release gate
A release candidate must have passing relevant tests, known limitations documented, secrets excluded, dependency changes reviewed and a reproducible setup guide.
