---
artifact_id: UNISYS-GOV-CC-001
layer: Governance
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Change Control

## Purpose

This document defines the change control process for the UNISYS system. All changes to governed artifacts, system configurations, operational procedures, and validated components must follow this process to maintain system integrity, traceability, and compliance.

---

## 1. Scope

This process applies to changes affecting:

- Governance documents and policies
- System configuration files
- Validated system components (see Validation Layer)
- Operational procedures and standards
- Node configurations and registrations

---

## 2. Change Classification

### Class 1 — Minor Change

Low-risk changes with no impact on system behavior, validation status, or governed specifications.

**Examples:**
- Typographical corrections
- Formatting updates
- Non-substantive clarifications
- Contact information updates

**Process:** Owner review and approval only. PMF updated.

### Class 2 — Moderate Change

Changes that affect documented content, procedures, or configurations without impacting validated system behavior.

**Examples:**
- Procedural updates
- Standard revisions
- Configuration adjustments within pre-approved parameters

**Process:** Owner review, peer review, and Change Control Board (CCB) notification.

### Class 3 — Major Change

Changes that impact validated components, critical governance documents, or system architecture.

**Examples:**
- Changes to validated subsystems
- Constitutional amendments
- Architectural modifications
- New component introduction

**Process:** Full CCB review and approval required.

---

## 3. Change Request Process

### Step 1: Initiate Change Request

The requester submits a Change Request (CR) including:

- Description of proposed change
- Affected artifacts/systems (with IDs)
- Justification and business need
- Change classification (Class 1, 2, or 3)
- Impact assessment
- Rollback plan

### Step 2: Impact Assessment

For Class 2 and 3 changes:
- Identify all affected downstream dependencies
- Assess validation impact
- Assess risk level
- Identify required reviewers

### Step 3: Review and Approval

| Class | Reviewers | Approver |
|-------|-----------|---------|
| 1 | Artifact Owner | Artifact Owner |
| 2 | Owner + Peer reviewer | CCB Notification |
| 3 | CCB full review | CCB Chair |

### Step 4: Implementation

- Implement approved change
- Update artifact version per semantic versioning
- Update PMF with change record
- Notify affected stakeholders

### Step 5: Verification

- Verify change implemented correctly
- Update all cross-references
- Close Change Request with verification record

---

## 4. Emergency Changes

Emergency changes that must bypass standard review may be implemented under the following conditions:

1. System safety or security is immediately threatened
2. Emergency is documented with justification
3. Change is reviewed post-implementation within 5 business days
4. Emergency CR is filed retroactively

---

## 5. Change Records

All change requests must be retained in the change log with:

- CR number
- Date initiated
- Requester
- Description
- Classification
- Approval status
- Implementation date
- Verifier

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
