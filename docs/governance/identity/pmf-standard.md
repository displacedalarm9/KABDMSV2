---
artifact_id: S-00002_
class: S-Class
layer: Identity
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS PMF (Provenance Metadata File) Standard

## Purpose

This document defines the structure, content, and maintenance requirements for Provenance Metadata Files (PMFs) within the UNISYS system. A PMF is the authoritative record of an artifact's complete history, origin, relationships, and lifecycle transitions.

---

## 1. Scope

This standard applies to all artifacts managed by DOCSYS and all governance documents produced under the UNISYS framework.

---

## 2. What is a PMF?

A Provenance Metadata File (PMF) is a structured record that accompanies every artifact in the UNISYS system. It captures:

- The artifact's origin and creation context
- All lifecycle stage transitions with timestamps and actors
- Version history and change log
- Relationship declarations (references, dependencies, supersessions)
- Audit trail of all significant actions taken on the artifact

---

## 3. PMF Structure

### 3.1 Header Section (Required)

```yaml
pmf_version: 1.0.0
artifact_id: [UNISYS-TYPE-###]
artifact_title: [Human-readable title]
artifact_type: [Document type]
created: YYYY-MM-DD
created_by: [Actor/Agent]
current_status: [Status]
current_version: [X.Y.Z]
```

### 3.2 Provenance Chain (Required)

Records each significant event in the artifact's history:

```yaml
provenance:
  - event: Created
    timestamp: YYYY-MM-DDTHH:MM:SSZ
    actor: [Actor name or system ID]
    version: 0.1.0
    notes: Initial creation
  - event: Reviewed
    timestamp: YYYY-MM-DDTHH:MM:SSZ
    actor: [Reviewer name]
    version: 0.1.0
    notes: First review completed
  - event: Approved
    timestamp: YYYY-MM-DDTHH:MM:SSZ
    actor: [Approver name]
    version: 1.0.0
    notes: Approved for operational use
```

### 3.3 Relationship Declarations (Required where applicable)

```yaml
relationships:
  derived_from:
    - artifact_id: [SOURCE-ID]
      description: [Nature of derivation]
  references:
    - artifact_id: [REF-ID]
      description: [Nature of reference]
  depends_on:
    - artifact_id: [DEP-ID]
      description: [Nature of dependency]
  supersedes:
    - artifact_id: [OLD-ID]
      description: [Reason for supersession]
  superseded_by:
    - artifact_id: [NEW-ID]
      description: [Reason for supersession]
```

### 3.4 Version History (Required)

```yaml
version_history:
  - version: 0.1.0
    date: YYYY-MM-DD
    author: [Author]
    changes: Initial draft
  - version: 1.0.0
    date: YYYY-MM-DD
    author: [Author]
    changes: [Summary of changes]
```

---

## 4. PMF Maintenance Requirements

### 4.1 Update Triggers

A PMF must be updated whenever:

- The artifact's lifecycle status changes
- A new version is created
- A relationship is added or removed
- Ownership or responsibility changes
- The artifact is reviewed, approved, or rejected
- The artifact is archived or made obsolete

### 4.2 Immutability

- Existing PMF entries shall not be deleted or modified
- New entries are always appended to the provenance chain
- Corrections must be recorded as new entries noting the correction

### 4.3 Retention

PMFs are retained for the lifetime of the UNISYS system plus a minimum archival retention period as defined by the applicable Records Management policy.

---

## 5. PMF File Naming Convention

PMF files shall follow this naming pattern:

```
PMF_[ARTIFACT-ID]_[YYYY-MM-DD].yaml
```

Example: `PMF_UNISYS-DOC-001_2026-05-28.yaml`

---

## 6. PMF Validation

All PMFs must be validated for:

1. Required fields present and non-empty
2. Chronologically ordered provenance chain
3. Valid artifact ID cross-reference
4. Consistent version numbering
5. No orphaned relationship references

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
