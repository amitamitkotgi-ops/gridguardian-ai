---
name: weather-api-data-quality
description: Weather API integration, solar irradiance variables, forecast provenance, caching and stale-data handling for SOLARIS AI.
---

# Weather API & Data Quality Skill

- Read the provider's current official API documentation before coding.
- Distinguish observations, forecasts, reanalysis and climatology; never label one as another.
- Store provider, endpoint/product, retrieval timestamp, valid timestamp, timezone, units and location coordinates.
- Select variables only when their meaning and units are understood: GHI, DNI, DHI and/or plane-of-array irradiance are not interchangeable.
- Check whether the API supplies actual irradiance or modelled irradiance and record that distinction.
- Use explicit request timeouts, bounded retries, caching and rate-limit awareness.
- Mark stale or missing data; never silently substitute synthetic values.
- Validate units, timestamp alignment, daylight/night-time behaviour and physically implausible values.
- Keep API keys out of source control; use environment configuration where keys are required.
- Add tests for timeout, malformed response, missing fields, stale values, timezone conversion and unit conversion.
