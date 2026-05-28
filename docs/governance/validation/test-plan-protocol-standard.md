---
artifact_id: UNISYS-VAL-TPPS-001
layer: Validation
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Test Plan & Test Protocol Standard

## Purpose

This document defines the standard for creating, executing, and managing test plans and test protocols within the UNISYS system. Test plans define the overall testing strategy; test protocols are the step-by-step execution documents.

---

## 1. Scope

This standard applies to:

- All IQ, OQ, and PQ test activities
- Functional and non-functional testing
- Regression testing after changes
- Integration and interface testing

---

## 2. Test Plan vs. Test Protocol

| Document | Purpose | When Created |
|----------|---------|--------------|
| **Test Plan** | High-level testing strategy, scope, resources, schedule | Before testing begins |
| **Test Protocol** | Step-by-step instructions for a specific test | Before test execution |
| **Test Report** | Results of test execution | After test execution |

---

## 3. Test Plan Structure

### 3.1 Required Sections

1. **Purpose and Scope** — What is being tested and why
2. **References** — Related specifications, protocols, and standards
3. **Test Objectives** — What the testing aims to demonstrate
4. **Test Types** — IQ, OQ, PQ, functional, regression, etc.
5. **Test Environment** — Hardware, software, and configuration requirements
6. **Test Data Requirements** — Data needed for testing
7. **Roles and Responsibilities** — Who does what
8. **Schedule** — Timeline for test activities
9. **Entry and Exit Criteria** — Conditions to start and conclude testing
10. **Risk Assessment** — Known testing risks and mitigations

### 3.2 Entry Criteria

Testing may not begin until:

- [ ] Test Plan approved
- [ ] All test protocols written and approved
- [ ] Test environment verified
- [ ] Required data available
- [ ] Qualified personnel assigned

### 3.3 Exit Criteria

Testing is complete when:

- [ ] All test cases executed
- [ ] All critical/major failures resolved or formally accepted
- [ ] Test report approved

---

## 4. Test Protocol Structure

### 4.1 Protocol Header

| Field | Value |
|-------|-------|
| Protocol ID | `TP-[TYPE]-[ARTIFACT-ID]-[###]` |
| Protocol Title | [Descriptive title] |
| Version | [X.Y.Z] |
| Related Test Plan | [Test Plan ID] |
| Qualification Type | IQ / OQ / PQ |
| Author | [Name] |
| Reviewer | [Name] |
| Approver | [Name] |

### 4.2 Test Case Structure

Each test case in the protocol shall contain:

| Field | Description |
|-------|-------------|
| Test Case ID | `TC-[###]` unique within protocol |
| Objective | What this test case verifies |
| Requirement Reference | Traced requirement ID(s) |
| Preconditions | System state required before test |
| Test Steps | Numbered, explicit instructions |
| Expected Results | Specific, observable expected outcome |
| Actual Results | Recorded during execution (blank before execution) |
| Pass/Fail | Determined after execution |
| Executed By | Tester signature and date |
| Reviewed By | Reviewer signature and date |

### 4.3 Test Step Format

```
Step [N]: [Precise action description]
Expected: [What should be observed after this step]
Actual: _______________________________________________
```

---

## 5. Test Execution Rules

1. Test protocols must be executed as written; no ad-hoc deviations
2. Deviations from the protocol must be documented on the protocol itself with justification
3. Tester must initial and date each step as completed
4. Failures must be documented with a Failure Report (FR) immediately
5. Retesting after failure correction requires a new protocol execution or documented retest justification

---

## 6. Test Protocol Numbering

```
TP-[QUALIFICATION TYPE]-[ARTIFACT-ID]-[###]
```

Examples:
- `TP-IQ-UNISYS-SYS-001-001` — IQ protocol for UNISYS system, protocol #001
- `TP-OQ-UNISYS-NODE-001-001` — OQ protocol for a node

---

## 7. Test Data Management

- Test data must be documented before test execution
- Production data shall not be used for testing unless explicitly approved
- Test data must be appropriate for the test objective (boundary cases, normal cases, error cases)
- Test data records are retained with the test protocol execution

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
