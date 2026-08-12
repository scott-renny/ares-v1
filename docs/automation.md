# Automation Design

## Controller responsibilities

ARES-CTRL validates scenario manifests, checks capacity and safety gates, creates a mission record, starts the required guests, confirms snapshots and telemetry, runs approved tasks, captures evidence, calculates detection results, and restores the lab.

## Scenario contract

Each scenario will declare:

- unique ID, version, owner, risk tier, and ATT&CK mappings;
- required guests, networks, accounts, snapshots, and resource budget;
- preflight tests and explicit authorization acknowledgement;
- ordered simulation steps with timeouts and idempotency expectations;
- expected telemetry, detections, and scoring weights;
- abort actions, cleanup, snapshot restoration, and verification;
- evidence retention and redaction requirements.

## Guardrails

- Dry-run is the default execution mode.
- High-risk steps require a second confirmation and active isolation check.
- Tasks use allowlisted modules rather than arbitrary dashboard commands.
- Every action receives a correlation ID and append-only event entry.
- Concurrency is capped by memory, storage latency, and scenario conflicts.
- Failed reset verification blocks the next mission.

## Future layout

```text
automation/
  api/          controller endpoints
  engine/       state machine and task runner
  providers/    Proxmox, guest and AWS adapters
  schemas/      manifest and report validation
  tests/        dry-run and safety-gate tests
```
