# Node Registry

**Purpose:** Central registry of all assigned node identifiers in the KABDMSV2 ecosystem.  
**Created:** 2026-04-03  
**Last Updated:** 2026-04-03  
**Version:** 1.0.0

---

## Overview

This registry tracks all node IDs assigned within the KABDMSV2 system. Each node has a unique identifier following the `NODE-TYPE-###` format. Consult this registry before assigning new node IDs to avoid conflicts.

See [Configuration Standards](./standards/configuration-standards.md) for the naming convention details.

---

## Assigned Node IDs

| Node ID        | Type | Number | Name                   | Config File                                  | Status  | Description                                      |
|----------------|------|--------|------------------------|----------------------------------------------|---------|--------------------------------------------------|
| NODE-OPS-001   | OPS  | 001    | Legion 5 Gen 10 AMD    | `config_NODE-OPS-001_Legion5Gen10.xml`       | Active  | Primary workstation — Lenovo Legion 5 Gen 10 AMD |
| NODE-VR-002    | VR   | 002    | Legion Pro 5 Gen 10 AMD| `config_NODE-VR-002_LegionPro5Gen10.xml`     | Active  | Gaming and VR node — Lenovo Legion Pro 5 Gen 10 AMD |
| NODE-ARC-003   | ARC  | 003    | Custom Archival Node   | `config_NODE-ARC-003_CustomArchival.xml`     | Active  | Archival storage node — custom-built NAS         |

---

## Node Type Prefixes

| Prefix | Category              | Next Available ID |
|--------|-----------------------|-------------------|
| ARC    | Archival/backup       | 004               |
| OPS    | Operational           | 002               |
| VR     | Virtual reality / VMs | 003               |
| DEV    | Development           | 001               |
| TEST   | Testing               | 001               |

---

## ID Assignment Rules

1. Each type starts at `001` and increments sequentially.
2. IDs are **never reused**, even if a node is decommissioned.
3. Decommissioned nodes remain in this registry with status `Retired`.
4. The config file name must match the assigned node ID exactly.
5. The `<NodeId>` element inside the config `<Metadata>` must match the registry entry.

---

## Adding a New Node

1. Determine the appropriate type prefix (`ARC`, `OPS`, `VR`, `DEV`, or `TEST`).
2. Use the next available ID from the table above.
3. Create the config file: `config_NODE-TYPE-###_Description.xml`.
4. Add the `<Metadata>` section with the new `<NodeId>`, `<Name>`, `<Version>`, `<Created>`, and `<Updated>`.
5. Update this registry with the new entry and increment "Next Available ID".
6. Commit both the new config file and the updated registry in the same commit.

---

## Revision History

| Version | Date       | Changes                                    | Author          |
|---------|------------|--------------------------------------------|-----------------|
| 1.0.0   | 2026-04-03 | Initial node registry creation             | KABDMSV2 Project |
