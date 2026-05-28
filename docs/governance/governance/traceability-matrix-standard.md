---
artifact_id: UNISYS-GOV-TMS-001
layer: Governance
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Traceability Matrix Standard

## Purpose

This document defines the standard for creating, maintaining, and using traceability matrices within the UNISYS system. Traceability matrices ensure that requirements, design elements, test cases, and validation evidence are explicitly linked, providing full bidirectional traceability.

---

## 1. Scope

Traceability matrices are required for:

- Requirements to design traceability
- Requirements to test case traceability
- Test cases to validation evidence traceability
- Governance policies to implementation traceability

---

## 2. Traceability Matrix Types

### 2.1 Requirements Traceability Matrix (RTM)

Links each requirement to its source, design element, and test coverage.

**Columns:**
| Column | Description |
|--------|-------------|
| Req ID | Unique requirement identifier |
| Requirement Text | Statement of requirement |
| Source | Origin (e.g., policy, standard, stakeholder) |
| Design Reference | Implementing design element |
| Test Case ID(s) | Associated test case(s) |
| Validation Evidence | Reference to validation record |
| Status | Open / In Progress / Verified |

### 2.2 Test Traceability Matrix (TTM)

Links each test case to the requirement(s) it validates and the test evidence.

**Columns:**
| Column | Description |
|--------|-------------|
| Test Case ID | Unique test case identifier |
| Test Description | Summary of test |
| Requirement ID(s) | Traced requirements |
| Test Protocol Reference | Protocol document reference |
| Execution Date | Date test was executed |
| Result | Pass / Fail / Pending |
| Evidence Reference | Reference to test evidence record |

### 2.3 Governance Traceability Matrix (GTM)

Links governance policies and standards to their implementing artifacts and controls.

**Columns:**
| Column | Description |
|--------|-------------|
| Policy/Standard ID | Source policy or standard ID |
| Policy Statement | Governing statement |
| Implementing Artifact | Artifact implementing the control |
| Control Description | How the requirement is addressed |
| Verification Method | How compliance is verified |
| Status | Compliant / Gap / In Progress |

---

## 3. Traceability Matrix Format

Traceability matrices shall be maintained in Markdown table format within dedicated traceability documents, or in a structured data file (CSV or JSON) linked from the relevant specification.

### 3.1 Naming Convention

```
TM_[TYPE]_[ARTIFACT-ID]_[YYYY-MM-DD].md
```

Examples:
- `TM_RTM_UNISYS-SYS-001_2026-05-28.md`
- `TM_TTM_UNISYS-VAL-001_2026-05-28.md`

---

## 4. Traceability Coverage Requirements

### 4.1 Minimum Coverage

- All functional requirements must have at least one associated test case
- All safety-critical requirements must have at least two independent test cases
- All governance requirements must have at least one implementing control

### 4.2 Gap Identification

Gaps in traceability coverage must be:

1. Documented in the traceability matrix (Status = Gap)
2. Reported to the CCB or Governance Board
3. Tracked until resolved

---

## 5. Maintenance Requirements

Traceability matrices must be updated:

- When new requirements are added
- When requirements are modified or removed
- When new test cases are created
- When test results are recorded
- When governed artifacts are changed via Change Control

Version and update history of traceability matrices shall be tracked in their PMF.

---

## 6. Review and Approval

Traceability matrices are subject to review:

- As part of the validation review process
- During audits
- At each major version increment of the traced artifact

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
