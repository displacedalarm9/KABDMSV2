---
artifact_id: UNISYS-GOV-DCRM-001
layer: Governance
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Document Control & Records Management

## Purpose

This document establishes the controls and practices for creating, reviewing, approving, distributing, and retiring documents and records within the UNISYS system. Effective document control ensures that only approved, current documents are in use and that records are retained and accessible as required.

---

## 1. Scope

This standard applies to:

- All governance documents
- Technical specifications and standards
- Operational procedures
- Validation records and qualification reports
- Configuration records
- Audit and inspection records

---

## 2. Document Control Principles

1. **Authorization** — Only approved documents are used operationally
2. **Currency** — Documents are kept up to date and outdated versions are removed from active use
3. **Accessibility** — Current approved documents are accessible to those who need them
4. **Traceability** — All document changes are tracked with version history
5. **Legibility** — Documents are clear, readable, and complete

---

## 3. Document Lifecycle

### 3.1 Creation

1. Author creates document using approved template
2. Apply required metadata (see [Metadata Standard](../identity/metadata-standard.md))
3. Assign document ID following naming convention
4. Set initial status to `Draft`
5. Create PMF

### 3.2 Review

1. Author submits for review
2. Designated reviewers provide comments
3. Author resolves comments
4. Review cycle repeats until all reviewers approve
5. Review records retained

### 3.3 Approval

1. Approving authority reviews final draft
2. Formal approval recorded in PMF
3. Version incremented to release version (x.0.0)
4. Status set to `Approved`

### 3.4 Distribution

1. Approved document published to designated location
2. Stakeholders notified of new/revised document
3. Previous version superseded (Status = `Deprecated`)
4. Previous version moved to archive with clearly marked superseded status

### 3.5 Review and Update

1. Documents reviewed on schedule (see [Lifecycle Model](../identity/lifecycle-model.md))
2. Required updates initiated via Change Control
3. Document moves to `Under Change` status during revision

### 3.6 Retirement

1. Document no longer required initiates retirement via Change Control
2. Dependency analysis performed
3. Document status set to `Retired`
4. Document archived per retention schedule

---

## 4. Document Numbering

All documents shall follow the numbering convention:

```
[LAYER-PREFIX]-[TYPE]-[###]
```

| Layer | Prefix |
|-------|--------|
| Identity | `UNISYS-ID` |
| Governance | `UNISYS-GOV` |
| Validation | `UNISYS-VAL` |
| Operational | `UNISYS-OPS` |
| Extensions | `UNISYS-EXT` |

---

## 5. Records Management

### 5.1 Definition of Records

Records are completed documents that provide evidence of activities performed. Unlike working documents, records are not revised — they are fixed evidence of what occurred.

### 5.2 Record Creation Requirements

- Records must be created at the time of the activity
- Records must be legible and permanent
- Records must be attributable (who created them, when)
- Corrections must be made with a single strikethrough and initialed

### 5.3 Retention Schedule

| Record Type | Minimum Retention Period |
|-------------|--------------------------|
| Governance decisions | Indefinite |
| Validation records | System lifetime + 5 years |
| Audit records | 10 years |
| Change records | System lifetime |
| CAPA records | System lifetime + 3 years |
| Training records | Employment + 5 years |

### 5.4 Archive and Retrieval

- All records stored in designated archive location
- Records retrievable within 5 business days
- Archive access controls applied per classification
- Physical backups maintained for critical records

---

## 6. Controlled Copy vs. Reference Copy

| Copy Type | Description | Control Level |
|-----------|-------------|---------------|
| Controlled | Official current version, tracked | Full control |
| Reference | For informational use, may not be current | User awareness required |
| Obsolete | Superseded version, retained for history | Clearly marked, restricted use |

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
