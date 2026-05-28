---
artifact_id: UNISYS-VAL-VRT-001
layer: Validation
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Validation Report Template

## Purpose

This template defines the required structure and content for Validation Reports within the UNISYS system. Validation Reports document the outcome of qualification activities (IQ, OQ, PQ) and provide the formal record of validated status.

---

## Instructions for Use

1. Copy this template for each validation report
2. Complete all required fields
3. Replace placeholder text in brackets `[...]` with actual content
4. Remove these instructions from the final report
5. Assign a report ID following the naming convention below

**Report ID Format:** `VR-[QUAL-TYPE]-[ARTIFACT-ID]-[YYYY-MM-DD]`

**Example:** `VR-OQ-UNISYS-SYS-001-2026-05-28`

---

## Validation Report

---

### 1. Report Identification

| Field | Value |
|-------|-------|
| **Report ID** | [VR-TYPE-ARTIFACT-ID-YYYY-MM-DD] |
| **Report Title** | [Qualification type] Validation Report — [System/Component Name] |
| **Qualification Type** | [IQ / OQ / PQ] |
| **System/Component** | [Name and Artifact ID] |
| **Version Qualified** | [Version number of qualified item] |
| **Qualification Period** | [Start date] to [End date] |
| **Report Date** | [Date of report issuance] |
| **Report Version** | [1.0] |

---

### 2. Scope and Objective

#### 2.1 Scope

[Describe what was qualified — the system, component, or process covered by this report.]

#### 2.2 Objective

[State the objective of this qualification activity. What did it aim to demonstrate?]

---

### 3. References

| Document | ID | Version |
|----------|----|---------|
| Qualification Protocol | [Protocol ID] | [Version] |
| Requirements Specification | [Spec ID] | [Version] |
| Test Plan | [Test Plan ID] | [Version] |
| IQ Report (if this is OQ/PQ) | [IQ Report ID] | [Version] |
| OQ Report (if this is PQ) | [OQ Report ID] | [Version] |

---

### 4. System Description

[Provide a brief description of the qualified system or component, including its purpose, key components, and operational context.]

---

### 5. Qualification Summary

#### 5.1 Results by Section

| Protocol Section | Tests Executed | Passed | Failed | Deviations | Result |
|-----------------|----------------|--------|--------|------------|--------|
| [Section 1 name] | | | | | Pass/Fail |
| [Section 2 name] | | | | | Pass/Fail |
| **Total** | | | | | |

#### 5.2 Failures and Deviations

| ID | Section | Description | Impact | Disposition | Resolved |
|----|---------|-------------|--------|-------------|---------|
| | | | | | |

*If none, state: "No failures or deviations were recorded."*

---

### 6. Traceability

[Reference the applicable Traceability Matrix document(s) demonstrating requirement coverage.]

| Traceability Matrix | ID | Version | Coverage |
|--------------------|----|---------|---------|
| Requirements Traceability Matrix | [ID] | [Version] | [% requirements covered] |

---

### 7. Observations and Recommendations

[List any observations noted during qualification that do not constitute failures but may warrant attention or improvement. Also include any recommendations for the operational phase.]

- [Observation/Recommendation 1]
- [Observation/Recommendation 2]

*If none, state: "No observations or recommendations."*

---

### 8. Conclusion

#### 8.1 Qualification Status

☐ **PASSED** — The [system/component] has successfully completed [IQ/OQ/PQ] and is qualified for [intended use].

☐ **CONDITIONAL PASS** — The [system/component] has completed [IQ/OQ/PQ] with the following conditions: [describe conditions].

☐ **FAILED** — The [system/component] has not completed [IQ/OQ/PQ]. See failures section for details.

#### 8.2 Qualification Statement

[Provide a formal statement summarizing the qualification outcome. Example: "Based on the results documented in this report, the UNISYS [Component] version [X.Y.Z] has demonstrated that it meets all specified requirements as defined in the approved qualification protocol. The system is qualified for operational use as described in the scope of this report."]

---

### 9. Approvals

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Report Author | [Name] | | |
| Technical Reviewer | [Name] | | |
| Qualification Owner | [Name] | | |
| Approving Authority | [Name] | | |

---

### 10. Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1 | [Date] | Initial draft | [Author] |
| 1.0 | [Date] | Approved | [Author] |

---

*End of Validation Report Template*
