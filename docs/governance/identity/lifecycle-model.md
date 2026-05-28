---
artifact_id: UNISYS-LIFECYCLE-MODEL-001
layer: Identity
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Lifecycle Model

## Purpose

This document defines the authoritative lifecycle model for all artifacts and documents within the UNISYS system. It specifies the stages, transitions, and governance requirements that apply from initial creation through retirement.

---

## 1. Scope

This lifecycle model governs:

- Governance documents and policies
- Technical specifications and standards
- Operational artifacts and records
- System components and configurations
- Validation and qualification artifacts

---

## 2. Lifecycle Stages

### Stage 0: Proposed

**Definition:** An artifact has been identified as necessary but has not yet been formally initiated.

**Entry Criteria:** Artifact listed in a manifest or governance backlog.

**Activities:**
- Record in the relevant manifest (e.g., M-00001_)
- Assign artifact ID (reserved status)
- Assign ownership

**Exit Criteria:** Owner assigned and scope defined.

---

### Stage 1: Draft

**Definition:** The artifact is actively being authored.

**Entry Criteria:** Work has begun on the artifact content.

**Activities:**
- Content creation
- Internal review cycles
- Version increments (0.x.x)
- PMF updates for each revision

**Exit Criteria:** Content complete and submitted for formal review.

---

### Stage 2: Under Review

**Definition:** The artifact has been submitted for formal review and approval.

**Entry Criteria:** Author has declared the draft complete.

**Activities:**
- Formal review by designated reviewers
- Issue tracking and resolution
- Review comments documented in PMF

**Exit Criteria:** All review issues resolved; reviewer sign-off obtained.

---

### Stage 3: Approved

**Definition:** The artifact has passed review and received formal approval.

**Entry Criteria:** All reviewers have approved; approving authority sign-off obtained.

**Activities:**
- Version incremented to 1.0.0 (or next major version)
- Approval recorded in PMF
- Artifact published to appropriate location

**Exit Criteria:** Artifact published and operational use authorized.

---

### Stage 4: Active

**Definition:** The artifact is in current operational use.

**Entry Criteria:** Artifact is approved and published.

**Activities:**
- Active reference and application
- Periodic review (per review schedule)
- Minor updates (increment PATCH or MINOR version)

**Exit Criteria:** Artifact superseded, deprecated, or retired.

---

### Stage 5: Under Change

**Definition:** An active artifact is being significantly revised.

**Entry Criteria:** Change request initiated and approved.

**Activities:**
- Draft new version
- Track changes against active version
- Maintain active version during change period

**Exit Criteria:** New version approved; previous version superseded.

---

### Stage 6: Deprecated

**Definition:** The artifact is superseded by a newer version but retained for reference.

**Entry Criteria:** A superseding artifact has been approved.

**Activities:**
- Mark artifact as deprecated in PMF
- Link to superseding artifact
- Restrict new use

**Exit Criteria:** No active dependencies remain; artifact moves to Retired.

---

### Stage 7: Retired

**Definition:** The artifact is formally retired from use.

**Entry Criteria:** No active dependencies; retirement approved.

**Activities:**
- Record retirement in PMF
- Move to archive storage
- Preserve full provenance chain

**Exit Criteria:** None — Retired is a terminal state.

---

## 3. Lifecycle State Diagram

```
[Proposed] → [Draft] → [Under Review] → [Approved] → [Active]
                                                          |
                                               [Under Change] ←→ [Active]
                                                          |
                                                    [Deprecated]
                                                          |
                                                      [Retired]
```

---

## 4. Stage Transition Requirements

| Transition | Approving Authority | Documentation Required |
|------------|---------------------|----------------------|
| Proposed → Draft | Artifact Owner | Manifest entry, ID assignment |
| Draft → Under Review | Artifact Owner | Complete draft, PMF updated |
| Under Review → Approved | Designated Approver | Review sign-off, all issues resolved |
| Approved → Active | System Administrator | Publication confirmation |
| Active → Under Change | Change Control Board | Approved change request |
| Active → Deprecated | Governance Board | Supersession declaration |
| Deprecated → Retired | Governance Board | Dependency analysis, retirement order |

---

## 5. Review Schedule

All active artifacts must be reviewed on the following schedule:

| Artifact Type | Review Frequency |
|---------------|-----------------|
| Constitutional documents | Annual |
| Standards and policies | Annual |
| Procedures | Semi-annual |
| Technical specifications | As-needed / with system changes |
| Operational documents | Quarterly |

---

## 6. Integration with DOCSYS

The UNISYS Lifecycle Model aligns with and extends the DOCSYS lifecycle stages defined in [docs/docsys-lifecycle-stages.md](../../docsys-lifecycle-stages.md). Where the two models overlap, the UNISYS Lifecycle Model takes precedence for governance artifacts.

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
