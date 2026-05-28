---
artifact_id: UNISYS-GOV-CAPA-001
layer: Governance
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS CAPA (Corrective and Preventive Action)

## Purpose

This document defines the Corrective and Preventive Action (CAPA) process for the UNISYS system. CAPA ensures that root causes of deficiencies, non-conformances, and systemic issues are identified, addressed, and prevented from recurring.

---

## 1. Scope

The CAPA process applies to:

- Recurring deviations and non-conformances
- Audit findings requiring systemic correction
- Customer or stakeholder complaints indicating systemic issues
- Failed validation tests
- Process failures with recurrence risk
- Proactively identified risk areas (Preventive Actions)

---

## 2. CAPA Types

### 2.1 Corrective Action (CA)

Addresses an existing non-conformance or deficiency to prevent recurrence.

**Trigger sources:**
- Deviation management records
- Audit findings
- Incident reports
- Failed validation events

### 2.2 Preventive Action (PA)

Addresses a potential non-conformance before it occurs.

**Trigger sources:**
- Risk assessments
- Trend analysis
- Process reviews
- Proactive improvement initiatives

---

## 3. CAPA Process Steps

### Step 1: Initiation

Create a CAPA record with:

- CAPA number (unique)
- CAPA type (CA or PA)
- Date initiated
- Initiator
- Problem statement or risk description
- Related records (DR numbers, audit findings, etc.)

### Step 2: Root Cause Analysis (RCA)

For Corrective Actions, perform a formal root cause analysis:

**Required RCA Methods (choose at least one):**

| Method | When to Use |
|--------|-------------|
| 5-Why Analysis | Simple to moderate issues |
| Fishbone (Ishikawa) Diagram | Complex, multi-factor issues |
| Fault Tree Analysis | System/safety failures |
| Process Map Analysis | Process-related failures |

Document:
- Root cause(s) identified
- Contributing factors
- RCA method used
- Evidence supporting the root cause conclusion

### Step 3: Action Plan

Develop an action plan addressing the root cause:

- Corrective/preventive actions to be taken
- Owner for each action
- Target completion date for each action
- Success criteria / verification method

### Step 4: Implementation

- Execute each action per the plan
- Document implementation evidence
- Update affected artifacts, procedures, or configurations via Change Control

### Step 5: Effectiveness Verification

After a defined monitoring period:

- Confirm the root cause is resolved
- Confirm no recurrence has occurred
- Verify success criteria are met

### Step 6: Close-out

- Document verification results
- Record CAPA closure date
- Close CAPA record
- Retain in CAPA log

---

## 4. CAPA Record Contents

| Field | Required | Description |
|-------|----------|-------------|
| CAPA Number | Yes | Unique identifier (`CAPA-YYYY-###`) |
| Type | Yes | CA or PA |
| Date Initiated | Yes | ISO 8601 date |
| Initiator | Yes | Actor/agent |
| Problem Statement | Yes | Clear description |
| Root Cause | Yes (CA) | RCA findings |
| Action Plan | Yes | List of actions with owners and dates |
| Implementation Evidence | Yes | Evidence of completion |
| Verification Results | Yes | Effectiveness check results |
| Date Closed | Yes | ISO 8601 date |
| Related DR | No | Deviation record reference |

---

## 5. CAPA Timelines

| Priority | RCA Due | Actions Due | Verification Period |
|----------|---------|-------------|-------------------|
| Critical | 5 business days | 15 business days | 30 days |
| Major | 15 business days | 30 business days | 60 days |
| Minor | 30 business days | 60 business days | 90 days |

---

## 6. CAPA Trend Reporting

CAPA records are reviewed quarterly to identify trends, recurring issues, and opportunities for systemic improvement. Trend reports are presented to the Governance Board.

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
