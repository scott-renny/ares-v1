# Architecture

## Design principles

- **Isolation first:** lab traffic is denied access to the home LAN and Internet by default.
- **Reproducibility:** every mission has prerequisites, expected telemetry, cleanup, and reset validation.
- **Control-plane separation:** ARES-CTRL orchestrates; target guests do not hold management credentials.
- **Measured evolution:** v1 proves software and workflows before v2 hardware decisions.
- **Fail safe:** emergency stop can disable lab interfaces and stop scenario tasks without depending on a compromised guest.

## Logical planes

| Plane | Components | Purpose |
|---|---|---|
| Management | Proxmox UI/API, admin workstation | Host administration; tightly restricted |
| Control | ARES-CTRL, scenario definitions, secrets references | Orchestration and state management |
| Exercise | AD, Windows, Kali, web and Linux guests | Controlled attack/defense activity |
| Evidence | Telemetry, scores, mission records, reports | Validation and audit trail |
| External | AWS lab account | Optional cloud missions through an explicit boundary |

## Mission lifecycle

`DRAFT → READY → PREFLIGHT → RUNNING → ABORTED|COMPLETED → COLLECTING → RESETTING → VERIFIED`

A mission is not complete until evidence is saved, temporary access is revoked, and reset verification passes.

## Availability on the starting host

The FX-8320 provides enough logical cores for a small lab, but 16 GB RAM and a single HDD are the primary constraints. Ares therefore schedules only the guests needed for a mission. The controller rejects launches that exceed the configured resource budget.
