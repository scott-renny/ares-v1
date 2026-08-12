# Network and Security Design

## Proposed zones

| Zone | Typical members | Default policy |
|---|---|---|
| Management | Proxmox, admin endpoint | Allow only named admin sources |
| Control | ARES-CTRL | Reach Proxmox API and approved guest agents only |
| Operator | ATTACK-01 | Reach exercise targets during an active mission |
| Exercise | Windows/Linux targets | No home-LAN access; internal flows are scenario-specific |
| DMZ-Lab | WEB-01 | No inbound WAN exposure; limited exercise access |
| Telemetry | Collectors/sensors | Receive logs; restrict administrative access |

## Egress

Internet access is denied by default. Temporary egress uses an allowlist, is time-bounded, logged, and removed during cleanup. Package and image acquisition should occur through controlled staging rather than from compromised targets.

## Emergency stop

The emergency stop cancels orchestration jobs, disables exercise-facing virtual interfaces or applies a deny-all ruleset, revokes temporary cloud access, records the reason, and preserves evidence before shutdown where safe. It must remain reachable through the management plane.

## Secrets

Use least-privilege service identities and a secret store. Repository examples contain placeholders only. Rotate lab credentials after scenarios that exercise credential access.

## AWS boundary

Use a dedicated lab account or isolated sandbox, budget alarms, short-lived roles, region/service allowlists, synthetic identities, and mandatory teardown. No trust path to personal or production cloud resources is permitted.
