# VM Inventory

| ID | Purpose | Network zones | Persistence | Notes |
|---|---|---|---|---|
| AD-DC-01 | AD DS, DNS, lab identities | services, exercise | Snapshot baseline | No trust with real identities |
| WIN-01 | Primary user endpoint | exercise | Reverted after missions | Synthetic users and documents |
| WIN-02 | Secondary endpoint / lateral target | exercise | Reverted after missions | Started only when required |
| ATTACK-01 | Kali operator tooling | operator, exercise | Curated tool snapshot | No unrestricted egress |
| WEB-01 | Vulnerable web workloads | dmz-lab, exercise | Rebuildable | Never exposed to WAN |
| LINUX-01 | Linux target and telemetry validation | exercise | Rebuildable | Minimal services by default |
| ARES-CTRL | API, scheduler, evidence and UI | control, management API | Backed up | Stores references, not plaintext secrets |

## Template rules

- Pin OS/version and document image provenance.
- Apply only scenario-relevant vulnerabilities.
- Maintain `clean`, `instrumented`, and optional scenario snapshots.
- Never snapshot live production credentials or personal data.
- Verify guest agent health, time sync, telemetry, and reset after cloning.
