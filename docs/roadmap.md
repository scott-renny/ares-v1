# Roadmap

## Ares v1 — prove the platform

- [ ] Audit, back up, and health-check existing hardware
- [ ] Install and harden Proxmox VE
- [ ] Create isolated bridges/VLANs and validate deny-by-default rules
- [ ] Build minimal guest templates and snapshots
- [ ] Implement ARES-CTRL mission state machine and dry-run mode
- [ ] Deliver first benign telemetry validation scenario
- [ ] Add emergency stop and tested recovery runbook
- [ ] Add prioritized adversary-simulation scenarios
- [ ] Add dashboard, detection scoring, history, and report export
- [ ] Add bounded AWS lab integration
- [ ] Publish performance, capacity, and safety findings

### Optional v1 capacity changes

- [ ] Upgrade to 32 GB only when scenario concurrency is RAM-bound
- [ ] Add the 1 TB SATA SSD only when storage latency/endurance measurements justify it

## Ares v2 — purpose-built migration

- [ ] Derive requirements from v1 workload and reliability data
- [ ] Select server chassis and updated compute platform
- [ ] Design storage, networking, cooling, power, backup, and recovery
- [ ] Revalidate isolation and safety controls on the new platform
- [ ] Migrate controller data, templates, scenarios, and reports
- [ ] Retire or reassign v1 hardware through a documented process

v2 is not a prerequisite for v1 and is not represented as an in-progress hardware rebuild.
