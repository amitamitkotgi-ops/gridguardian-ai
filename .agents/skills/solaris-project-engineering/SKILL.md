---
name: solaris-project-engineering
description: Project-wide engineering rules for SOLARIS AI. Use when planning, modifying, reviewing, documenting, testing, or integrating any SOLARIS AI subsystem.
---

# SOLARIS AI Project Engineering Skill

## Project identity
SOLARIS AI is an AI-powered solar plant monitoring, energy forecasting and storage management demonstrator.

## Non-negotiable rules
- Preserve existing architecture and inspect code before editing.
- Do not introduce React, Next.js, Redis, Kafka, Docker, Kubernetes, microservices or a new database without a clear requirement and explicit approval.
- Make small, reviewable changes; avoid unrelated rewrites.
- Never claim simulated data is physical measurement.
- Label measured, observed, forecast, calculated, predicted and simulated values distinctly.
- Record timestamps in UTC; display local time as Asia/Kolkata.
- Use explicit units and validate ranges.
- Do not invent model accuracy, field results, hardware tests or failure predictions.
- Keep secrets out of source control.
- Add tests for calculations, schemas and edge cases.

## Workflow for every task
1. Inspect current code, docs, tests and Git status.
2. State intended change and affected files.
3. Check compatibility with current architecture.
4. Implement the smallest complete change.
5. Add/update tests and documentation.
6. Run relevant checks and report exact results.
7. Identify remaining risks and unverified assumptions.

## Evidence standard
A feature is complete only when code, test evidence, data provenance and limitations are documented. Use statuses: NOT STARTED, IN PROGRESS, BLOCKED, VERIFIED, DEFERRED.
