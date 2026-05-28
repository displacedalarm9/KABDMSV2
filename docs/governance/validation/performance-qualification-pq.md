---
artifact_id: UNISYS-VAL-PQ-001
layer: Validation
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Performance Qualification (PQ)

## Purpose

This document defines the Performance Qualification (PQ) process for UNISYS system components. PQ demonstrates that the system consistently performs within defined specifications under real-world operational conditions over a defined period.

---

## 1. Scope

PQ applies after successful OQ and covers:

- Consistent performance under actual operational conditions
- Performance across the full range of operational scenarios
- Sustained operation over the PQ monitoring period
- Performance under concurrent load and real operational data

---

## 2. PQ Objectives

The PQ process confirms:

1. The system consistently meets performance specifications during actual use
2. The system performs reliably over the defined PQ monitoring period
3. No systematic failures or performance degradation occur
4. The system is suitable for its intended operational purpose

---

## 3. PQ Prerequisites

Before commencing PQ:

- [ ] OQ successfully completed and approved
- [ ] Approved PQ Protocol in place
- [ ] Operational environment fully configured
- [ ] Real or representative operational data available
- [ ] PQ monitoring period and criteria defined
- [ ] Qualified personnel assigned for monitoring

---

## 4. PQ Protocol Structure

### Section 1: PQ Monitoring Plan

| Parameter | Description |
|-----------|-------------|
| PQ Period | [Duration of PQ monitoring, e.g., 30 days] |
| Sampling Frequency | [How often measurements are taken] |
| Performance Metrics | [List of metrics to be monitored] |
| Acceptance Limits | [Pass/fail criteria for each metric] |

### Section 2: Performance Metrics

Define and track the following for the PQ period:

| Metric | Specification Limit | Measurement Method | Measurement Frequency |
|--------|--------------------|--------------------|----------------------|
| [Metric 1] | [Limit] | [How measured] | [Frequency] |
| [Metric 2] | [Limit] | [How measured] | [Frequency] |

### Section 3: Operational Scenario Coverage

Verify performance across all defined operational scenarios:

| Scenario | Description | Frequency During PQ | Performance Result | Pass/Fail |
|----------|-------------|--------------------|--------------------|-----------|
| [Scenario 1] | [Description] | [How often executed] | [Result summary] | |
| [Scenario 2] | [Description] | [How often executed] | [Result summary] | |

### Section 4: Anomaly Log

Record any anomalies, incidents, or performance deviations during the PQ period:

| Date | Anomaly Description | Impact | Disposition | Resolved Date |
|------|---------------------|--------|-------------|---------------|
| | | | | |

### Section 5: PQ Period Summary

| Metric | Total Measurements | Within Spec | Out of Spec | % Compliance |
|--------|-------------------|-------------|-------------|--------------|
| [Metric 1] | | | | |

---

## 5. PQ Acceptance Criteria

PQ is considered passing when:

- All required monitoring periods are completed
- All performance metrics meet acceptance limits throughout the PQ period
- All anomalies are documented and resolved
- Statistical analysis (if required) confirms consistent performance
- Qualified reviewer has approved the completed PQ

---

## 6. PQ Reporting

Upon PQ completion, a PQ Report shall be generated containing:

- PQ Protocol reference and monitoring period
- Summary of metrics with trend data
- Anomaly log with dispositions
- Statistical analysis results (if applicable)
- Reviewer and approver sign-offs
- Conclusion statement (PQ Passed / PQ Failed / Conditional Pass)

---

## 7. Ongoing Monitoring

After successful PQ, the following ongoing monitoring shall be maintained:

- Periodic performance checks at defined frequency
- Trend analysis to identify early degradation
- Re-PQ triggered by significant process or environmental changes

---

## 8. Re-qualification Triggers

A new PQ is required when:

- Significant operational environment changes
- Process changes that may affect consistency
- Performance trend indicates degradation
- Periodic re-validation schedule requires PQ renewal

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
