---
artifact_id: UNISYS-OPS-SSM-001
layer: Operational
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Subsystem Map

## Purpose

This document provides the authoritative map of all subsystems within the UNISYS system. It defines each subsystem's identity, purpose, dependencies, and interfaces. The Subsystem Map serves as the primary reference for understanding UNISYS system architecture.

---

## 1. Scope

This document covers all registered UNISYS subsystems, their internal structure, and their relationships to each other and to the broader system.

---

## 2. Subsystem Registry

### 2.1 Core Subsystems

| Subsystem ID | Name | Purpose | Status |
|-------------|------|---------|--------|
| SUB-001 | Identity Service | Manages all UNISYS identity assignments and lookups | Defined |
| SUB-002 | Document Control Service | Manages artifact lifecycle and document control | Defined |
| SUB-003 | Governance Engine | Enforces governance policies at runtime | Defined |
| SUB-004 | Audit & Logging Service | Records all system events and audit trails | Defined |
| SUB-005 | Change Control Service | Manages change requests and their lifecycle | Defined |

### 2.2 Node Subsystems

Nodes are registered in the Node Registry (see `docs/node-registry.md`):

| Node ID | Name | Type | Purpose |
|---------|------|------|---------|
| NODE-OPS-001 | Legion5Gen10 | OPS | Operational compute node |
| NODE-VR-002 | LegionPro5Gen10 | VR | Virtual/VR workstation node |
| NODE-ARC-003 | CustomArchival | ARC | Long-term archival node |

### 2.3 Data Layer Subsystems

| Subsystem ID | Name | Purpose | Status |
|-------------|------|---------|--------|
| SUB-010 | Primary Data Store | Main artifact and document storage | Defined |
| SUB-011 | Archive Store | Long-term archive storage | Defined |
| SUB-012 | Configuration Store | System configuration storage | Defined |

---

## 3. Subsystem Dependency Map

```
Identity Service (SUB-001)
    └── No upstream dependencies (root service)

Document Control Service (SUB-002)
    └── Depends on: Identity Service (SUB-001)
    └── Depends on: Primary Data Store (SUB-010)

Governance Engine (SUB-003)
    └── Depends on: Identity Service (SUB-001)
    └── Depends on: Document Control Service (SUB-002)

Audit & Logging Service (SUB-004)
    └── Depends on: Infrastructure (file system / network)

Change Control Service (SUB-005)
    └── Depends on: Identity Service (SUB-001)
    └── Depends on: Document Control Service (SUB-002)
    └── Depends on: Governance Engine (SUB-003)

All Nodes
    └── Depend on: Core Services (SUB-001 through SUB-005)
    └── Depend on: Infrastructure Layer
```

---

## 4. Subsystem Interface Definitions

### 4.1 Identity Service Interfaces

| Interface | Direction | Description |
|-----------|-----------|-------------|
| ID Assignment | Inbound | Accept new entity registration requests |
| ID Lookup | Inbound | Return entity details by ID |
| ID Validation | Inbound | Confirm ID exists and is active |
| Registry Export | Outbound | Provide full registry for other subsystems |

### 4.2 Document Control Service Interfaces

| Interface | Direction | Description |
|-----------|-----------|-------------|
| Artifact CRUD | Inbound | Create, read, update artifact records |
| Lifecycle Transition | Inbound | Move artifact through lifecycle stages |
| PMF Access | Inbound | Read/write Provenance Metadata Files |
| Artifact Query | Inbound | Search and retrieve artifacts |

### 4.3 Governance Engine Interfaces

| Interface | Direction | Description |
|-----------|-----------|-------------|
| Policy Evaluation | Inbound | Evaluate requests against active policies |
| Policy Management | Inbound | Load, update, enable/disable policies |
| Compliance Report | Outbound | Generate compliance status reports |

---

## 5. Subsystem Configuration References

Each subsystem's configuration is defined in the applicable configuration file following the pattern:

```
config_[NODE-TYPE]-[###]_[Description].xml
```

See `docs/standards/configuration-standards.md` for configuration file structure.

---

## 6. Subsystem Addition Process

Adding a new subsystem requires:

1. Subsystem specification document approved
2. Subsystem ID assigned via Identity Service
3. Dependencies documented in this Subsystem Map
4. IQ/OQ completed for new subsystem
5. This document updated via Change Control

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
