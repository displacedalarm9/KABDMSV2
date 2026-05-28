---
artifact_id: UNISYS-GOV-DEV-001
layer: Governance
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Deviation Management

## Purpose

This document defines the process for identifying, documenting, evaluating, and resolving deviations from established UNISYS standards, specifications, and procedures. Deviation management ensures that non-conformances are formally handled rather than overlooked.

---

## 1. Scope

This process applies to any deviation from:

- Approved specifications and standards
- Validated procedures and protocols
- Configuration requirements
- Document control requirements
- Governance policies

---

## 2. Deviation Types

### 2.1 Planned Deviation

A deliberate, pre-approved departure from a standard or specification for a defined scope and duration.

**Characteristics:**
- Requested before the deviation occurs
- Limited scope and time period
- Requires formal approval before implementation

### 2.2 Unplanned Deviation

An unintentional departure from a standard or specification discovered after the fact.

**Characteristics:**
- Identified after the fact
- Requires immediate documentation
- Root cause analysis required
- May trigger CAPA

---

## 3. Deviation Process

### Step 1: Identification and Documentation

Upon identifying a deviation:

1. Stop affected activity if safety/integrity is at risk
2. Create Deviation Record (DR) immediately, including:
   - Affected artifact/system ID
   - Description of the deviation
   - Date/time of discovery
   - Discovered by (actor/agent)
   - Scope of impact

### Step 2: Impact Assessment

Assess the impact of the deviation:

- Safety implications
- Quality implications
- Validation status impact
- Affected downstream artifacts or processes

### Step 3: Classification

| Level | Description | Response Time |
|-------|-------------|---------------|
| Critical | Safety or system integrity risk | Immediate |
| Major | Significant impact on quality or compliance | 24 hours |
| Minor | Limited impact, no safety risk | 5 business days |

### Step 4: Approval

**Planned deviations:** Require approval before implementation.
**Unplanned deviations:** Require approval for continuation or disposition.

Approval authority by level:

| Level | Approving Authority |
|-------|---------------------|
| Critical | Governance Board |
| Major | CCB Chair |
| Minor | Artifact Owner |

### Step 5: Resolution and Disposition

Deviations are resolved by one of:

- **Correction:** Return to compliant state
- **Specification update:** Update the standard to reflect actual practice (via Change Control)
- **Waiver:** Formal acceptance of deviation with documented justification

### Step 6: Close-out

- Document resolution in DR
- Update PMF for affected artifacts
- Trigger CAPA if recurrence prevention is required
- Report to governance as appropriate

---

## 4. Deviation Record Contents

| Field | Required | Description |
|-------|----------|-------------|
| DR Number | Yes | Unique identifier |
| Date Opened | Yes | ISO 8601 date |
| Affected Artifact ID | Yes | UNISYS artifact ID |
| Deviation Description | Yes | Clear description |
| Type | Yes | Planned / Unplanned |
| Level | Yes | Critical / Major / Minor |
| Impact Assessment | Yes | Documented impact |
| Disposition | Yes | Correction / Update / Waiver |
| Date Closed | Yes | ISO 8601 date |
| Related CAPA | No | CAPA reference if applicable |

---

## 5. Relationship to CAPA

Deviations that reveal systemic issues or recurrence patterns shall trigger the CAPA process. See [CAPA](capa.md) for the corrective and preventive action process.

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
