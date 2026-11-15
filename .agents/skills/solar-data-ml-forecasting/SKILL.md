---
name: solar-data-ml-forecasting
description: Weather ingestion, solar time-series data engineering, generation forecasting and anomaly detection for SOLARIS AI. Use when building datasets, physics baselines, ML pipelines or model evaluation.
---

# Solar Data & ML Forecasting Skill

## Data provenance
For every feature, preserve source, unit, timestamp, retrieval time, valid time and whether it is measured, observed, forecast, calculated, predicted or simulated. Handle missing and stale values explicitly.

## Dataset design
- Use chronological train/validation/test splits.
- Prevent future weather or future telemetry leakage into past predictions.
- Keep a simple baseline (persistence or physics model) for comparison.
- Record plant configuration and model version with each forecast.
- Do not mix synthetic and physical data without a mode/source field.

## Evaluation
Report MAE and RMSE; use percentage metrics only with a justified denominator and handle night-time zero generation appropriately. Compare against a baseline and document test period and sample count.

## Anomaly detection
Start with sensor plausibility rules and engineering thresholds. Introduce ML anomaly detection only when data volume, operating modes and validation labels are adequate. Analyse false positives and false negatives.

## Battery analytics
Do not estimate SOC from voltage alone under variable load. Select a chemistry-appropriate estimation method and validate it against a trusted reference.
