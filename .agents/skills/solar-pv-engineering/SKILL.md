---
name: solar-pv-engineering
description: Solar PV, irradiance, module temperature, power and energy engineering for SOLARIS AI. Use when sizing, calculating, interpreting PV measurements, selecting sensors or designing generation estimates.
---

# Solar PV Engineering Skill

## Required inputs
Before calculations, identify panel nameplate ratings (Voc, Vmp, Isc, Imp, Pmax), orientation/tilt, irradiance source, module temperature source and system losses. Never assume missing nameplate values.

## Measurement discipline
- Distinguish plane-of-array irradiance from global horizontal irradiance.
- Distinguish measured backsheet temperature from estimated cell/module temperature.
- Record units, timestamps, sensor source and calibration state.
- Compute instantaneous DC power as V × I only when voltage/current are sampled consistently and topology is known.
- Accumulate energy by integrating power over elapsed time with explicit time units and gap handling.

## Modelling discipline
- Start with a transparent physics-based baseline and document assumptions.
- Use weather forecasts for future generation estimates; do not describe them as observations.
- Do not train ML until a representative chronological dataset exists.
- Compare advanced models with a simple persistence or physics baseline.

## Safety
- Verify every electrical rating against actual nameplates and datasheets.
- Keep the student prototype low-voltage DC; no exposed mains.
- Require appropriate charge controller, battery protection, fuses and wiring.
- Never recommend bypassing a battery BMS or charge controller.
