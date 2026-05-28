---
artifact_id: UNISYS-OPS-LMS-001
layer: Operational
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Logging & Monitoring Standard

## Purpose

This document defines the logging and monitoring standards for the UNISYS system. It specifies what must be logged, how logs are structured, how monitoring is performed, and how monitoring data is retained and used.

---

## 1. Scope

This standard applies to:

- All UNISYS core services and subsystems
- All registered nodes
- All governance and operational events
- System-level infrastructure monitoring

---

## 2. Logging Requirements

### 2.1 Events That Must Be Logged

| Category | Events |
|----------|--------|
| System lifecycle | Boot start/completion, shutdown, state transitions |
| Security | Authentication attempts (success and failure), authorization decisions, privilege changes |
| Governance | Artifact lifecycle transitions, change request actions, policy evaluations |
| Data operations | Artifact create/update/delete/archive actions |
| Errors | All errors per classification in Error Handling & Recovery Model |
| Configuration | Configuration load, change, validation events |
| Audit | Audit initiation, finding records, closure events |

### 2.2 Mandatory Log Fields

Every log entry must include:

| Field | Format | Description |
|-------|--------|-------------|
| `timestamp` | ISO 8601 with timezone | When the event occurred |
| `level` | `FATAL\|ERROR\|WARN\|INFO\|DEBUG` | Severity level |
| `event_type` | String | Category of event |
| `event_id` | `EVT-[TYPE]-[###]` | Unique event identifier |
| `component` | String | Component generating the log |
| `artifact_id` | UNISYS ID (if applicable) | Affected artifact |
| `actor` | String | Who or what triggered the event |
| `message` | String | Human-readable description |
| `outcome` | `SUCCESS\|FAILURE\|WARNING` | Result of the action |

### 2.3 Log Levels

| Level | Use Case |
|-------|----------|
| `FATAL` | Non-recoverable system errors |
| `ERROR` | Recoverable errors requiring attention |
| `WARN` | Potential issues; no immediate failure |
| `INFO` | Normal operational events |
| `DEBUG` | Detailed diagnostic information (not for production default) |

**Production default log level:** `INFO` (capture INFO and above)

---

## 3. Log Format

### 3.1 Structured Log Format (JSON)

```json
{
  "timestamp": "2026-05-28T12:00:00.000Z",
  "level": "INFO",
  "event_type": "ARTIFACT_LIFECYCLE",
  "event_id": "EVT-LIFECYCLE-001",
  "component": "DocumentControlService",
  "artifact_id": "UNISYS-DOC-001",
  "actor": "system-admin",
  "message": "Artifact status changed from Draft to Approved",
  "outcome": "SUCCESS",
  "details": {
    "previous_status": "Draft",
    "new_status": "Approved",
    "approved_by": "governance-board"
  }
}
```

---

## 4. Log Retention

| Log Category | Minimum Retention |
|-------------|-------------------|
| Security events | 3 years |
| Governance events | System lifetime |
| System lifecycle events | 2 years |
| Error events | 2 years |
| Operational events | 1 year |
| Debug logs | 30 days |

Logs approaching retention expiry are archived per the Document Control & Records Management standard before deletion.

---

## 5. Monitoring Requirements

### 5.1 Key Metrics to Monitor

| Metric | Threshold Warning | Threshold Critical | Measurement Interval |
|--------|-------------------|--------------------|--------------------|
| System state | Any non-OPERATIONAL state | FAILED state | Continuous |
| Core service health | Any service WARNING | Any service DOWN | 30 seconds |
| Storage utilization | 80% | 90% | 5 minutes |
| Error rate | >5 errors/min | >20 errors/min | 1 minute |
| Authentication failures | >5/min | >20/min | 1 minute |
| Node availability | Any node WARNING | Any node DOWN | 60 seconds |

### 5.2 Monitoring Alerts

Alerts must be generated for:

- Any metric crossing a WARNING or CRITICAL threshold
- Any service or node health status changing to WARNING, CRITICAL, or DOWN
- Any FATAL or ERROR level log event
- System state transitions to DEGRADED or FAILED
- Any security event of concern (auth failures, access denials)

### 5.3 Alert Routing

| Severity | Notification Method | Response Time |
|----------|--------------------|--------------:|
| Critical/Fatal | Immediate administrator alert | < 15 minutes |
| Major/Error | Administrator notification | < 1 hour |
| Minor/Warning | Operational dashboard / daily report | Next business day |

---

## 6. Log Integrity

To ensure log integrity:

- Logs are written to append-only storage
- Log tampering alerts are triggered by unexpected log deletions or modifications
- Log backups are maintained on a separate system
- Log integrity hashes are generated at defined intervals

---

## 7. Log Review

| Review Type | Frequency | Reviewer |
|-------------|-----------|---------|
| Security event review | Daily | Security/Governance staff |
| Error trend review | Weekly | System Administrator |
| Full operational log review | Monthly | System Administrator |
| Audit log review | As scheduled per audit plan | Auditors |

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
