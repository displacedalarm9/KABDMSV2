# File Management Guidelines

This document defines the standards for file management within the KABDMSV2 repository. These guidelines ensure consistency in naming, identifying, categorizing, and cycling files.

---

## Terms

| Term | Definition |
|------|------------|
| KABDMSV2 | K. A. Breneman's Document Management System, Version 2 |

---

## Table of Contents

1. [File Naming Conventions](#file-naming-conventions)
2. [File Identification](#file-identification)
3. [File Categorization](#file-categorization)
4. [File Cycling and Versioning](#file-cycling-and-versioning)
5. [Enforcement](#enforcement)

---

## File Naming Conventions

### General Rules

| Rule | Description | Example |
|------|-------------|---------|
| Case | Use lowercase for all file names | `system-info.md` |
| Word Separation | Use hyphens (`-`) for multi-word names | `system-info-formatted.md` |
| No Spaces | Never use spaces in file names | ❌ `system info.md` → ✅ `system-info.md` |
| No Special Characters | Avoid special characters except hyphens | ❌ `file@name.txt` → ✅ `file-name.txt` |
| Descriptive Names | Use clear, descriptive names | ❌ `data1.txt` → ✅ `system-report.txt` |
| Maximum Length | Keep names under 50 characters | `quarterly-performance-report-2025.md` |

### Extension Standards

| File Type | Extension | Purpose |
|-----------|-----------|---------|
| Markdown | `.md` | Documentation, formatted content |
| Plain Text | `.txt` | Raw data, logs, unformatted content |
| JSON | `.json` | Configuration, metadata, structured data |
| YAML | `.yaml` | Configuration files |

### Naming Patterns by Category

#### Documentation Files
```
<topic>[-<subtopic>][-<qualifier>].md
```
Examples:
- `readme.md`
- `system-info.md`
- `system-info-formatted.md`
- `file-management.md`

#### Data Files
```
<source>[-<type>][-<date>].<ext>
```
Examples:
- `system-export.txt`
- `system-export-2025-08-22.txt`
- `topics.json`

#### Configuration Files
```
<scope>[-config].<ext>
```
Examples:
- `project-config.json`
- `settings.yaml`

---

## File Identification

### File Headers

All markdown files should include a header section:

```markdown
# [Title]

**Purpose:** [Brief description]  
**Created:** [YYYY-MM-DD]  
**Last Updated:** [YYYY-MM-DD]  
**Author:** [Author name or system]
```

### JSON Files Metadata

JSON files should include a metadata section:

```json
{
  "_metadata": {
    "description": "Brief description of file purpose",
    "created": "YYYY-MM-DD",
    "version": "X.Y.Z"
  },
  "data": {}
}
```

### File Purpose Indicators

| Prefix/Suffix | Indicates |
|---------------|-----------|
| `*-raw.*` | Unprocessed, original data |
| `*-formatted.*` | Processed, human-readable format |
| `*-export.*` | Data exported from external system |
| `*-archive.*` | Historical/archived content |
| `*-template.*` | Template for creating new files |

---

## File Categorization

### Directory Structure

```
KABDMSV2/
├── README.md              # Project overview
├── file-management.md     # This document
├── docs/                  # Documentation files
│   └── *.md
├── data/                  # Data files
│   ├── raw/              # Unprocessed data
│   ├── processed/        # Formatted/processed data
│   └── confidential/     # Confidential data files
├── config/               # Configuration files
│   └── *.json, *.yaml
└── archive/              # Archived files
    └── YYYY/             # By year
```

### Category Definitions

| Category | Description | Location |
|----------|-------------|----------|
| Documentation | Human-readable documents, guides, references. | Root or `docs/` |
| Data | Raw and processed data files. | `data/` |
| Confidential | Sensitive or private data files. | `data/confidential/` |
| Configuration | Settings and metadata. | Root or `config/` |
| Archive | Historical or deprecated files. | `archive/` |

### Current File Mapping

| File | Category | Status |
|------|----------|--------|
| `README.md` | Documentation | Active |
| `file-management.md` | Documentation | Active |
| `topics.json` | Configuration | Active |
| `sysinfo.txt` | Data (Raw) | Active |
| `data/confidential/system-info-formatted.md` | Confidential | Active |

---

## File Cycling and Versioning

### Version Numbering

Use semantic versioning for tracked documents:

```
MAJOR.MINOR.PATCH.BUILD

MAJOR - Significant changes to structure or purpose.
MINOR - Content additions or updates.
PATCH - Minor corrections, typos.
BUILD - Iterations of reports, controlled copies of data files.
```

### Retention Policies

| File Type | Retention Period | Action After Period |
|-----------|-----------------|---------------------|
| Documentation | Indefinite | Update or archive. |
| Raw Data | 1 year | Archive or delete. |
| Processed Data | 1 year | Archive or delete. |
| Configuration | Indefinite | Version control. |
| Archives | 3 years | Review and purge. |
| Pay statements, financial statements | 7 years | Review, summarize, purge. |
| Journal entries, source documents, bookkeeping cycle | 5 years | Condense into one file per kind, paginate and format such file to retain post references. |
| Log files from programs | 1 year | Summarize and ensure recommendations are executed or at least considered and that none are missed. |

### Cycling Workflow

1. **Create**: New files follow naming conventions.
2. **Update**: Increment version, update timestamps.
3. **Archive**: Move to `archive/YYYY/` with date suffix.
4. **Purge**: Delete after retention period review.

### Archive Naming

When archiving files, append the archive date:

```
<original-name>-archived-YYYY-MM-DD.<ext>
```

Example:
- `sysinfo.txt` → `archive/2025/sysinfo-archived-2025-11-25.txt`

---

## Enforcement

### Pre-Commit Checks

Files should be validated against these rules before committing:

1. ✅ File name follows naming conventions.
2. ✅ Appropriate file extension used.
3. ✅ Required metadata/headers present.
4. ✅ File placed in correct category/location.

### Review Checklist

When reviewing changes, verify:

- [ ] File names are lowercase with hyphens.
- [ ] No spaces or special characters in names.
- [ ] File extension matches content type.
- [ ] Documentation files have proper headers.
- [ ] Data files are appropriately categorized.
- [ ] Archived files follow archive naming pattern.

### Non-Compliance Resolution

1. Identify non-compliant files.
2. Create compliant copy with proper naming.
3. Update references to use new file name.
4. Remove or archive non-compliant original.

---

## Quick Reference

### Do's ✅

- Use lowercase names.
- Separate words with hyphens.
- Use descriptive, meaningful names.
- Include file headers in documentation.
- Follow the versioning scheme.
- Archive before deletion.

### Don'ts ❌

- Use spaces in file names.
- Use camelCase or PascalCase.
- Use special characters (except hyphens).
- Create ambiguous or generic names.
- Delete files without archiving.
- Skip metadata in configuration files.

---

**Document Version:** 1.0.0  
**Created:** 2025-11-25  
**Last Updated:** 2025-11-25
