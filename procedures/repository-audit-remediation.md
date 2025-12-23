---
last_updated: 2025-11-25
version: 1.0.0
file_status: protocol
---

# Repository Audit and Remediation Protocol

## Purpose

This document defines the comprehensive audit and remediation protocol for the kabreneman project ecosystem. Use this protocol for quarterly repository audits, security reviews, and remediation planning.

## References

[See: README.md for repository structure]
[See: https://github.com/displacedalarm9/kabreneman.us/blob/main/docs/filename.md for naming conventions]
[See: https://github.com/displacedalarm9/kabreneman.us/tree/main/procedures for related procedures]

> **Note:** This repository (KABDMSV2) is in transition. The current README describes it as the "management system," but the planned state per this audit is for KABDMSV2 to become the data storage repository (data.kabreneman.us), while kabreneman.us becomes the file management system.

## Trigger Conditions

Execute this protocol when:

- [ ] Quarterly audit schedule (Q1, Q2, Q3, Q4).
- [ ] New repository added to ecosystem.
- [ ] Security incident or vulnerability discovered.
- [ ] Major structural changes proposed.
- [ ] Repository purpose or scope changes.

---

## Repository Ecosystem Overview

### Planned State

| Repository | Purpose | Visibility | Status |
|------------|---------|------------|--------|
| **kabreneman.us** | File management system (software) | Public | Active |
| **data.kabreneman.us** | Data storage (actual files) | Private | Planned (currently KABDMSV2) |
| **dev.kabreneman.us** | Development playground | Public/Private | Needs decision |

### Current State

| Repository | Current Name | Current Purpose | Transition Needed |
|------------|--------------|-----------------|-------------------|
| kabreneman.us | kabreneman.us | Active with scripts, docs, procedures | Clarify as software repo |
| KABDMSV2 | KABDMSV2 | Management system (per README) | Rename to data.kabreneman.us, set private |
| dev.kabreneman.us | dev.kabreneman.us | Empty since Dec 2020 | Archive or repurpose |

### Repository Relationships

```
kabreneman.us (Software)
    ├── Scripts and utilities
    ├── Documentation and procedures
    └── Integration with data repository
            │
            ▼
data.kabreneman.us (Data) ← Currently KABDMSV2
    ├── Configuration files
    ├── Reports and logs
    └── Confidential data (private)
            │
            ▼
dev.kabreneman.us (Development)
    ├── Experimental features
    ├── Testing environments
    └── Sandbox workflows
```

---

## Security Audit Checklist

### Repository Security Features

| Feature | kabreneman.us | KABDMSV2 | dev.kabreneman.us |
|---------|---------------|----------|-------------------|
| Dependabot | ❌ Not enabled | ❌ Not enabled | ❌ Not enabled |
| Secret Scanning | ❌ Not enabled | ❌ Not enabled | ❌ Not enabled |
| CodeQL/Code Scanning | ❌ Not enabled | ❌ Not applicable | ❌ Not enabled |
| Commit Signing | ⚠️ Partial | ❌ Not enforced | ❌ Not enforced |
| Branch Protection | ⚠️ Partial | ✅ All branches | ❌ None |

### Security Action Items

- [ ] Enable Dependabot security updates on all repositories.
- [ ] Enable Secret Scanning with push protection.
- [ ] Enable CodeQL for kabreneman.us (Python code).
- [ ] Standardize commit signing requirements.
- [ ] Review and enforce branch protection rules.

---

## Repository Health Scores

| Repository | Score | Status | Notes |
|------------|-------|--------|-------|
| dev.kabreneman.us | 🔴 Poor | Empty since creation (Dec 2020) | Needs repurposing or archival |
| kabreneman.us | 🟡 Fair | Active | Needs documentation improvements |
| KABDMSV2 | 🟢 Good | Active | Well-organized, active development |

---

## Task Breakdown by Priority

### 🔴 IMMEDIATE PRIORITY (Within 1 Week)

#### KABDMSV2 (Data Repository) Tasks

**1. Resolve Merge Conflict Chain**

- [ ] Merge PR #8 to complete revert of premature WIP merge.
- [ ] Verify `copilot/separate-data-files-management` branch is clean.
- [ ] Document integration requirements between data and software repos.

**2. Review Ready PRs**

| PR | Title | Status | Action |
|----|-------|--------|--------|
| #5 | Add file management guidelines | Ready for review | Review and merge |
| #6 | Add system-info-formatted.md | Draft | Review scope |

#### kabreneman.us (Software Repository) Tasks

**3. Review Pending PRs**

| PR | Title | Age | Action |
|----|-------|-----|--------|
| #40 | Organize uploaded off-repository files | Recent | Review and decide |
| #38 | Add project status, reviews, and tooling documentation | Draft | Review scope |

**4. Critical Issues**

- [ ] Issue #37: Upload pending files via local clone (P1, owner-request).
- [ ] Issue #39: Upload and review off-repository files (owner-request).

---

### 🟡 HIGH PRIORITY (Within 1 Month)

#### Repository Naming and Repurposing

**5. KABDMSV2 Rename Planning**

- [ ] Plan migration to "data.kabreneman.us" naming.
- [ ] Determine approach: rename or create new repository.
- [ ] Update all cross-references in documentation.
- [ ] Set repository visibility to Private.

**6. dev.kabreneman.us Repurposing**

Decision matrix:

| Option | When to Choose | Action |
|--------|----------------|--------|
| Archive | No planned development use | Archive the repository |
| Delete | Never needed again | Delete (after backup) |
| Repurpose | Active development planned | Initialize structure |

- [ ] Make decision on dev.kabreneman.us future.
- [ ] Execute chosen option.
- [ ] Update documentation references.

#### kabreneman.us Documentation Issues

**Security Issues:**

| Issue | Title | Priority |
|-------|-------|----------|
| #31 | Enforce security boundaries (gitignore + pre-commit hooks) | High |
| #34 | Strengthen PR checklist (sensitive data verification) | High |

**Documentation Issues:**

| Issue | Title | Priority |
|-------|-------|----------|
| #25 | Enforce repository-wide file naming conventions | Medium |
| #26 | Ensure frontmatter headers in all Markdown docs/templates | Medium |
| #28 | Validate and scaffold report folder structure in data repo | Medium |
| #29 | Create XSD and validate node XML configs | Medium |
| #32 | Pin dependencies in requirements and verify scripts | Medium |
| #33 | Document WorkCap Analyzer data expectations and archive behavior | Medium |
| #35 | Add Markdown link validation for cross-references | Medium |
| #36 | Align topics.json metadata and document integration | Medium |

**Feature Issues:**

| Issue | Title | Priority |
|-------|-------|----------|
| #27 | Automate daily template copy with date prefix | Medium |
| #30 | Implement phase tracking dashboard/status files | Medium |

**Process Issues:**

| Issue | Title | Priority |
|-------|-------|----------|
| #5 | [META] Review and refactor architecture after KABDMSV2 merge | High |
| #14 | Add EditorConfig and Python linting configuration | Medium |
| #15 | Add GitHub Actions for automated checks | Medium |
| #21 | Document backup and restore procedures | Medium |
| #22 | Set up automated work documentation enforcement | Medium |
| #23 | Upload offline files for versioning control | Medium |
| #24 | Test issue: naming conventions enforcement | Low |

---

### 🟢 MEDIUM PRIORITY (Within 2 Months)

**7. Branch Cleanup (kabreneman.us)**

Stale branches to evaluate and clean:

- [ ] `copilot/create-project-repositories`
- [ ] `copilot/make-data-private`
- [ ] `copilot/secure-sensitive-data-merge`
- [ ] `copilot/upload-review-off-repository-files` (after PR #40 decision)
- [ ] `copilot/create-draft-and-issue` (after PR #38 decision)

**8. Security Infrastructure (All Repos)**

- [ ] Enable Dependabot security updates.
- [ ] Enable Secret Scanning with push protection.
- [ ] Enable CodeQL for kabreneman.us (Python).
- [ ] Standardize branch protection rules across repositories.

---

### 🔵 LOW PRIORITY (Within 3 Months)

**9. Documentation and Standards**

- [ ] Create cross-repository documentation explaining the ecosystem.
- [ ] Document data/software separation boundaries.
- [ ] Establish contribution guidelines for each repo type.
- [ ] Create repository relationship diagram.

**10. Audit Schedule**

- [ ] Schedule quarterly repository audits.
- [ ] Create audit checklist template.
- [ ] Document audit findings format.

---

## Success Criteria

| Priority | Timeline | Criteria |
|----------|----------|----------|
| Immediate | 1 week | All immediate priority items resolved |
| High | 1 month | All high priority items resolved |
| Security | 2 weeks | Security features enabled on all repos |
| Naming | 1 month | Repository naming/purpose clarity established |
| Documentation | 2 months | Cross-repository integration properly documented |

---

## Audit Completion Checklist

- [ ] All immediate priority items addressed.
- [ ] Security features reviewed and enabled.
- [ ] Repository health scores updated.
- [ ] Open PRs triaged and actioned.
- [ ] Stale branches identified and cleaned.
- [ ] Documentation updated with findings.
- [ ] Next audit scheduled.
- [ ] This document updated with `last_updated` date.

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2025-11-25 | Initial protocol creation |

---

## Contact

For questions about this protocol, create an issue in the KABDMSV2 repository or, once established, in the kabreneman.us repository.
