---
artifact_id: UNISYS-VAL-IQ-001
layer: Validation
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Installation Qualification (IQ)

## Purpose

This document defines the Installation Qualification (IQ) process for UNISYS system components. IQ verifies that the system and its components have been delivered, installed, and configured correctly in accordance with approved specifications.

---

## 1. Scope

IQ applies to:

- UNISYS system installation
- Node installation and initial configuration
- Software component installation
- Infrastructure and environment setup
- Any re-installation or major configuration change

---

## 2. IQ Objectives

The IQ process confirms:

1. The system components have been received as specified
2. Installation environment meets required specifications
3. Components are installed according to vendor and project requirements
4. Configuration settings are correct and documented
5. Required documentation (manuals, licenses, certificates) is present and accessible

---

## 3. IQ Prerequisites

Before commencing IQ:

- [ ] Approved IQ Protocol in place (see [Test Plan & Protocol Standard](test-plan-protocol-standard.md))
- [ ] System specifications and design documents available
- [ ] Qualified personnel assigned
- [ ] Installation environment ready and documented
- [ ] Required tools and equipment calibrated (if applicable)

---

## 4. IQ Protocol Structure

### Section 1: System/Component Identification

| Field | Requirement | Actual | Pass/Fail |
|-------|-------------|--------|-----------|
| System Name | UNISYS [Component] | | |
| Version | [Specification version] | | |
| Serial/Asset Number | [As specified] | | |
| Installation Location | [Designated location] | | |
| Installation Date | [Scheduled date] | | |

### Section 2: Environmental Verification

| Parameter | Specification | Measured/Observed | Pass/Fail |
|-----------|---------------|-------------------|-----------|
| Operating System | [Required OS and version] | | |
| Hardware specifications | [Minimum requirements] | | |
| Network configuration | [Required settings] | | |
| Storage capacity | [Minimum required] | | |
| Required dependencies | [List of dependencies] | | |

### Section 3: Installation Verification

| Check Item | Expected Result | Actual Result | Pass/Fail |
|------------|-----------------|---------------|-----------|
| Installation files integrity | Checksums verified | | |
| Directory structure | Per specification | | |
| File permissions | Per specification | | |
| Configuration files present | All required files present | | |
| Services/processes running | Per expected state | | |

### Section 4: Configuration Verification

| Parameter | Required Value | Actual Value | Pass/Fail |
|-----------|----------------|--------------|-----------|
| [Config parameter 1] | [Required] | | |
| [Config parameter 2] | [Required] | | |
| [Node ID assignment] | [Per Node Registry] | | |

### Section 5: Documentation Verification

| Document | Reference | Present | Pass/Fail |
|----------|-----------|---------|-----------|
| Installation guide | [Reference] | | |
| Configuration specifications | [Reference] | | |
| License/certificates | [Reference] | | |

---

## 5. IQ Acceptance Criteria

IQ is considered passing when:

- All required checks are completed
- No critical or major failures are unresolved
- Minor failures have documented disposition (deviation record or accepted with justification)
- Qualified reviewer has reviewed and approved the completed IQ

---

## 6. IQ Reporting

Upon IQ completion, an IQ Report shall be generated containing:

- IQ Protocol reference
- Summary of results (Pass/Fail per section)
- List of any deviations or failures with disposition
- Reviewer and approver sign-offs
- Conclusion statement (IQ Passed / IQ Failed / Conditional Pass)

---

## 7. Re-qualification Triggers

A new IQ is required when:

- System is reinstalled or migrated to a new environment
- Major version upgrade of a governed component
- Significant configuration changes outside pre-approved parameters

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
