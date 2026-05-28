---
artifact_id: UNISYS-VAL-RSS-001
layer: Validation
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Requirements Specification Standard

## Purpose

This document defines the standard for creating, structuring, and managing requirements specifications within the UNISYS system. Requirements are the foundation of all validation activities; this standard ensures they are clear, testable, and traceable.

---

## 1. Scope

This standard applies to:

- System-level requirements
- Subsystem and component requirements
- Functional and non-functional requirements
- Interface requirements
- Performance requirements

---

## 2. Requirements Quality Criteria

All requirements must be:

| Criterion | Description |
|-----------|-------------|
| **Unique** | Each requirement has a unique ID |
| **Atomic** | Each requirement states one thing |
| **Clear** | Unambiguous language; no "and/or" constructs that imply multiple requirements |
| **Testable** | Can be verified through test, inspection, or analysis |
| **Traceable** | Can be linked to its source |
| **Necessary** | Removal would create a gap |
| **Feasible** | Achievable within known constraints |

---

## 3. Requirement Types

### 3.1 Functional Requirements

Define what the system must do.

**Template:** `The system shall [action] [object] [condition/constraint].`

**Example:** `The system shall assign a unique ID to every artifact at the time of creation.`

### 3.2 Non-Functional Requirements

Define system quality attributes.

**Template:** `The system shall [quality attribute] to [measurable standard] under [conditions].`

**Example:** `The system shall retrieve any artifact record within 5 seconds under normal operating load.`

### 3.3 Interface Requirements

Define how the system interacts with other systems.

**Template:** `The system shall [interface type] with [external system] via [protocol/standard].`

### 3.4 Constraint Requirements

Define limitations on the system design or implementation.

**Template:** `The system shall [comply with / operate within] [constraint description].`

---

## 4. Requirement ID Structure

```
[SYSTEM]-[TYPE]-REQ-[###]
```

| Component | Description | Example |
|-----------|-------------|---------|
| SYSTEM | System or subsystem prefix | `UNISYS` |
| TYPE | Requirement type (F=Functional, NF=Non-Functional, I=Interface, C=Constraint) | `F` |
| REQ | Fixed label | `REQ` |
| ### | Sequential number, zero-padded | `001` |

**Examples:**
- `UNISYS-F-REQ-001` — Functional requirement #001
- `UNISYS-NF-REQ-001` — Non-functional requirement #001
- `UNISYS-I-REQ-001` — Interface requirement #001

---

## 5. Requirements Specification Document Structure

### 5.1 Required Sections

1. **Purpose and Scope** — What system or component is specified
2. **References** — Standards, inputs, and parent specifications
3. **Assumptions and Constraints** — Operating assumptions
4. **Functional Requirements** — All F-type requirements
5. **Non-Functional Requirements** — All NF-type requirements
6. **Interface Requirements** — All I-type requirements
7. **Constraint Requirements** — All C-type requirements
8. **Traceability Summary** — Link to Requirements Traceability Matrix

### 5.2 Per-Requirement Entry

| Field | Required | Description |
|-------|----------|-------------|
| Requirement ID | Yes | Unique ID per naming convention |
| Statement | Yes | The requirement text |
| Rationale | Yes | Why this requirement exists |
| Source | Yes | Where this requirement originates |
| Priority | Yes | Critical / High / Medium / Low |
| Verification Method | Yes | Test / Inspection / Analysis / Demonstration |
| Test Case ID | No | Assigned after test planning |
| Status | Yes | Draft / Approved / Implemented / Verified |

---

## 6. Verification Methods

| Method | When to Use |
|--------|-------------|
| **Test** | Execute a procedure and compare results to expected outcome |
| **Inspection** | Examine documentation, configuration, or physical item |
| **Analysis** | Use models, calculations, or simulations |
| **Demonstration** | Operate the system and observe behavior |

---

## 7. Requirements Baseline

Once approved, a Requirements Specification becomes the requirements baseline. Changes to the baseline must follow the Change Control process.

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
