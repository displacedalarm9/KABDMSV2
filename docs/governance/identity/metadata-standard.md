---
artifact_id: S-00001_
class: S-Class
layer: Identity
manifest: M-00001_
status: Outstanding
created: 2026-05-28
last_updated: 2026-05-28
version: 0.1.0
---

# UNISYS Metadata Standard

## Purpose

This document defines the required and optional metadata fields for all artifacts, documents, and records managed within the UNISYS system. Consistent metadata enables discovery, traceability, governance, and lifecycle management.

---

## 1. Scope

This standard applies to:

- All documents created within UNISYS governance layers
- All artifacts tracked by DOCSYS
- All configuration files within the KABDMSV2 ecosystem
- All manifest, policy, and procedure documents

---

## 2. Metadata Categories

### 2.1 Core Identity Metadata (Required)

| Field | Description | Format | Example |
|-------|-------------|--------|---------|
| `artifact_id` | Unique identifier | `[PREFIX]-[TYPE]-[###]` | `UNISYS-DOC-001` |
| `title` | Human-readable title | Free text | `UNISYS Metadata Standard` |
| `version` | Semantic version | `MAJOR.MINOR.PATCH` | `1.0.0` |
| `status` | Current lifecycle state | Enum | `Active` |
| `created` | Creation date | ISO 8601 | `2026-05-28` |
| `last_updated` | Last modification date | ISO 8601 | `2026-05-28` |

### 2.2 Classification Metadata (Required)

| Field | Description | Format | Example |
|-------|-------------|--------|---------|
| `layer` | Governance layer | Enum | `Identity` |
| `manifest` | Originating manifest ID | `M-#####_` | `M-00001_` |
| `document_type` | Type of document | Enum | `Standard` |
| `classification` | Access classification | Enum | `Internal` |

### 2.3 Provenance Metadata (Required)

| Field | Description | Format | Example |
|-------|-------------|--------|---------|
| `owner` | Responsible entity | String | `UNISYS Governance` |
| `author` | Original author | String | `System Administrator` |
| `approver` | Approving authority | String | `Governance Board` |
| `approved_date` | Date of approval | ISO 8601 | `2026-05-28` |

### 2.4 Relational Metadata (Optional)

| Field | Description | Format | Example |
|-------|-------------|--------|---------|
| `parent_id` | Parent artifact ID | `[PREFIX]-[TYPE]-[###]` | `SYS-001` |
| `depends_on` | List of dependencies | Array of IDs | `["UNISYS-ID-CONST-001"]` |
| `supersedes` | Superseded artifact ID | ID string | `UNISYS-META-STD-000` |
| `related_to` | Related artifact IDs | Array of IDs | `["S-00002_"]` |

---

## 3. Metadata Format

### 3.1 YAML Frontmatter (Markdown files)

All Markdown documents shall include YAML frontmatter as the first block:

```yaml
---
artifact_id: UNISYS-[TYPE]-[###]
layer: [Layer Name]
manifest: M-00001_
status: [Status]
created: YYYY-MM-DD
last_updated: YYYY-MM-DD
version: X.Y.Z
---
```

### 3.2 XML Metadata (Configuration files)

XML configuration files shall include a `<Metadata>` section:

```xml
<Metadata>
  <ArtifactId>UNISYS-TYPE-###</ArtifactId>
  <Title>Document Title</Title>
  <Version>1.0.0</Version>
  <Status>Active</Status>
  <Created>YYYY-MM-DD</Created>
  <LastUpdated>YYYY-MM-DD</LastUpdated>
</Metadata>
```

---

## 4. Enumerated Values

### 4.1 Status Values

| Value | Description |
|-------|-------------|
| `Outstanding` | Required but not yet created |
| `Draft` | In development |
| `Review` | Under review |
| `Approved` | Formally approved |
| `Active` | In operational use |
| `Deprecated` | Superseded by newer version |
| `Retired` | No longer in use |

### 4.2 Document Type Values

| Value | Description |
|-------|-------------|
| `Constitution` | Foundational governance document |
| `Standard` | Normative specification |
| `Policy` | Governing policy |
| `Procedure` | Step-by-step operational process |
| `Template` | Reusable document structure |
| `Manifest` | Tracking/inventory document |
| `Report` | Outcome or assessment document |
| `Specification` | Technical specification |

### 4.3 Classification Values

| Value | Description |
|-------|-------------|
| `Public` | Unrestricted access |
| `Internal` | Internal use only |
| `Restricted` | Limited distribution |
| `Confidential` | Controlled access |

---

## 5. Validation Rules

1. All required fields must be present and non-empty
2. `version` must follow semantic versioning (`MAJOR.MINOR.PATCH`)
3. Date fields must use ISO 8601 format (`YYYY-MM-DD`)
4. `artifact_id` must be unique across the UNISYS namespace
5. `status` must be one of the defined enumerated values
6. `last_updated` must be equal to or later than `created`

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 0.1.0 | 2026-05-28 | Initial draft | UNISYS Governance |
