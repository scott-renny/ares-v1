# Dashboard Concept

## Primary views

- **Mission Control:** launch eligible scenarios, inspect prerequisites, start/reset, and invoke emergency stop.
- **Live Mission:** timeline, guest health, running step, telemetry arrival, alerts, and safety status.
- **Results:** expected-versus-observed detections, weighted score, gaps, evidence links, and analyst notes.
- **History:** searchable mission records, scenario versions, trends, and report export.
- **Lab Health:** resource headroom, snapshot age, storage health, agent status, and blocked conditions.

## Interaction rules

- Destructive or high-risk controls show target scope and require confirmation.
- Emergency stop is persistent, prominent, and accessible without opening a mission detail.
- The UI never exposes raw credentials or permits arbitrary shell execution.
- A reset is shown as complete only after verification checks pass.

## Detection score

An initial score can combine telemetry arrival, analytic alert, alert fidelity, response action, and evidence completeness. Scores must retain the raw observations so a percentage never hides why a mission passed or failed.
