---
artifact_id: S-00008_
class: S-Class
layer: Extensions
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS File Behavior Standard

## Purpose

This document defines the standard for how files are handled, named, stored, versioned, and managed within the UNISYS system. Consistent file behavior ensures predictability, traceability, and integrity across all file operations.

---

## 1. Scope

This standard applies to:

- All files created or managed within the UNISYS system
- Configuration files
- Governance documents and artifacts
- Data files and records
- Logs and operational outputs

---

## 2. File Naming Conventions

### 2.1 General Naming Rules

1. Use lowercase letters and hyphens for general document files (`kebab-case`)
2. Use PascalCase for XML element names within configuration files
3. No spaces in file names
4. No special characters except hyphens (`-`) and underscores (`_`)
5. File names must be descriptive and self-explanatory

### 2.2 File Naming Patterns by Type

| File Type | Pattern | Example |
|-----------|---------|---------|
| Governance documents | `[subject-description].md` | `change-control.md` |
| Configuration files | `config_NODE-[TYPE]-[###]_[Description].xml` | `config_NODE-OPS-001_Legion5Gen10.xml` |
| PMF files | `PMF_[ARTIFACT-ID]_[YYYY-MM-DD].yaml` | `PMF_UNISYS-DOC-001_2026-05-28.yaml` |
| Validation records | `VR-[TYPE]-[ARTIFACT-ID]-[YYYY-MM-DD].md` | `VR-OQ-UNISYS-SYS-001-2026-05-28.md` |
| Traceability matrices | `TM_[TYPE]_[ARTIFACT-ID]_[YYYY-MM-DD].md` | `TM_RTM_UNISYS-SYS-001_2026-05-28.md` |
| Manifest documents | `MANIFEST-[ID].md` | `MANIFEST-M-00001.md` |
| Log files | `[component]-[YYYY-MM-DD].log` | `governance-engine-2026-05-28.log` |

---

## 3. File Format Standards

### 3.1 Document Files

| Format | Use Case | Extension |
|--------|----------|-----------|
| Markdown | All governance documents, READMEs, specifications | `.md` |
| XML | Node and system configuration files | `.xml` |
| YAML | Metadata files, PMFs, structured configuration | `.yaml` |
| JSON | Topic registries, API data, structured data | `.json` |
| Plain text | Logs, simple data exports | `.txt` / `.log` |

### 3.2 Markdown Documents

All Markdown governance documents must:
- Include YAML frontmatter as the first block (per Metadata Standard)
- Use `#` for the title (H1), `##` for major sections (H2)
- Include a Revision History table at the end
- Not exceed 500 lines (split into multiple files if necessary)

### 3.3 XML Configuration Files

All XML configuration files must:
- Begin with `<?xml version="1.0" encoding="UTF-8"?>`
- Use `<Configuration>` (capital C) as the root element
- Include a `<Metadata>` section with required fields
- Use PascalCase for all element names

---

## 4. File Storage and Organization

### 4.1 Directory Structure

```
[repository root]
├── docs/                     # Documentation
│   ├── governance/           # UNISYS governance artifacts
│   │   ├── identity/         # Identity layer documents
│   │   ├── governance/       # Governance layer documents
│   │   ├── validation/       # Validation layer documents
│   │   ├── operational/      # Operational layer documents
│   │   └── extensions/       # Extension documents
│   └── standards/            # General standards
├── config_*.xml              # Node configuration files
├── procedures/               # Operational procedures
└── data/                     # Data files
```

### 4.2 File Placement Rules

1. Configuration files belong in the root directory (per existing convention)
2. Governance documents belong in `docs/governance/[layer]/`
3. General standards belong in `docs/standards/`
4. Procedures belong in `procedures/`
5. Log files belong in designated log storage (not committed to repository)

---

## 5. File Versioning

### 5.1 Version Tracking

All governed files must track version history:

- Configuration files: `<Version>` element in XML Metadata
- Markdown documents: `version:` in YAML frontmatter and Revision History table
- YAML files: `version:` field

### 5.2 Version Numbering

All files follow semantic versioning: `MAJOR.MINOR.PATCH`

| Increment | When |
|-----------|------|
| MAJOR | Fundamental restructuring or breaking change |
| MINOR | Significant addition of content |
| PATCH | Minor corrections, typos, formatting |

---

## 6. File Integrity

### 6.1 Checksums

For critical files (configuration, validation records, PMFs):
- Checksums should be generated and recorded at time of creation
- Checksums verified at time of use
- Checksum algorithm: SHA-256

### 6.2 File Protection

- Approved/Active governed files are treated as read-only
- Changes require a Change Request
- Version history preserved via version control system (Git)

---

## 7. File Deletion and Archival

Files are never permanently deleted from governed storage. Instead:

1. **Superseded files:** Retained with status `Deprecated`
2. **Retired files:** Moved to archive with status `Retired`
3. **Erroneous files:** Marked as `Voided` with explanation; never removed

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
