# Hardware Strategy

## Ares v1 starting point

| Component | Existing hardware | v1 decision |
|---|---|---|
| Motherboard | ASUS M5A97 LE R2.0 | Reuse; verify firmware and virtualization settings |
| CPU | AMD FX-8320 | Reuse; validate AMD-V support and thermal stability |
| Memory | 16 GB DDR3 | Reuse initially; enforce scenario resource budgets |
| Storage | 1 TB HDD | Reuse initially after SMART/health check and backup |
| GPU | Radeon HD 6450 | Use for installation/recovery; headless in normal operation |
| Network | Gigabit Ethernet | Reuse; VLANs require compatible switching, otherwise use host-only bridges |
| PSU | Cooler Master GX2 750W | Reuse only after inspection; monitor stability |

## Previously selected optional v1 upgrades

- TEAMGROUP Elite 32 GB (4×8 GB) DDR3-1600 CL11
- Timetec 1 TB SATA III 2.5-inch SSD

These remain capacity upgrades, not prerequisites. Purchase or install them only if measurements show that memory pressure or HDD latency prevents the target missions.

## Pre-install gates

- Back up all required data before replacing Windows.
- Check disk SMART data and run an extended test.
- Update firmware only through the vendor-supported process and stable power.
- Enable AMD-V/SVM; enable IOMMU only when a planned feature needs it.
- Clean dust, inspect fans/capacitors/cabling, and perform a memory test.
- Record idle/load temperature, power, and noise baselines.

## v2 boundary

Ares v2 is a distinct purpose-built server-chassis migration. Chassis, platform, storage topology, cooling, NICs, and redundancy will be selected from v1 utilization and reliability data—not assumed in v1 documentation.
