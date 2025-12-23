# DOCSYS Document Lifecycle Stages

**Purpose:** Document lifecycle framework for KABDMSV2  
**Created:** 2025-12-23  
**Last Updated:** 2025-12-23  
**Author:** KABDMSV2 Project

---

This document outlines the complete lifecycle stages used within DOCSYS, based on established patterns in archival and creative workflows. These stages describe how an artifact moves from initial capture to archival obsoletion, ensuring consistent provenance, auditability, and restoration readiness.

## Lifecycle Overview

The DOCSYS lifecycle consists of 11 distinct stages that govern how artifacts are managed throughout their existence in the system.

---

## 1. Capture

**Definition:** The moment an artifact is first recorded or digitized.

**Activities:**
- Scanning physical documents
- Photographing artifacts
- Exporting digital files
- Downloading content
- Transcribing analog media

**Output:** Each capture event generates a unique **TSN (Trace Serial Number)** representing the artifact's origin.

**Key Considerations:**
- Capture quality and fidelity
- Original format preservation
- Timestamp documentation
- Source attribution

---

## 2. Intake

**Definition:** The classification stage where the captured artifact is assigned its identity within DOCSYS.

**Activities:**
- Assign document number
- Apply type prefix (e.g., SCN, STR, DOC, FRG)
- Set title and description
- Establish initial metadata
- Create Provenance Metadata File (PMF)

**Output:** The artifact receives a formal identity within DOCSYS.

**Document Type Prefixes:**
- **SCN** - Scene documents
- **STR** - Structure/architectural documents
- **DOC** - General documentation
- **FRG** - Fragment/partial documents
- Additional prefixes as defined by project needs

---

## 3. Versioning

**Definition:** The evolutionary stage where artifacts that change over time receive version identifiers.

**Activities:**
- Assign version numbers (v1, v2, v3, etc.)
- Generate new TSN for each version
- Document changes in PMF
- Maintain version history
- Link versions in provenance chain

**Output:** A versioned artifact with documented evolution history.

**Versioning Rules:**
- Each version is a separate artifact with its own TSN
- All versions remain in the system
- Newer versions may supersede older ones
- Version history is immutable

---

## 4. Controlled Print (When Applicable)

**Definition:** A physical printout containing human-added marks such as annotations, highlights, signatures, or corrections.

**Activities:**
- Generate physical print
- Capture human annotations
- Digitize marked print
- Transcribe all marks and notations
- Document mark metadata (author, date, purpose)

**Output:** Controlled prints are treated as new artifacts with their own TSNs and PMFs.

**Key Requirements:**
- All marks must be captured
- Marks must be transcribed to text when possible
- Mark metadata (who, when, why) must be recorded
- Original and marked versions linked via PMF

---

## 5. Analysis

**Definition:** Interpretive or contextual documents that provide commentary, summaries, metadata, or insights related to an artifact.

**Activities:**
- Create analytical commentary
- Generate summaries
- Develop interpretive frameworks
- Document contextual information
- Establish analytical relationships

**Output:** Analysis documents are separate artifacts with their own document numbers and PMFs.

**Analysis Types:**
- Critical analysis
- Summary documents
- Metadata documentation
- Interpretive frameworks
- Contextual studies

---

## 6. Procedure / Workflow

**Definition:** Documents that define repeatable steps, rules, naming conventions, or operational logic.

**Activities:**
- Document operational procedures
- Define naming conventions
- Establish processing rules
- Create workflow definitions
- Version as procedures evolve

**Output:** Procedure documents that guide consistent artifact handling.

**Characteristics:**
- Versioned as they evolve
- Reference other procedures when applicable
- Provide step-by-step guidance
- Define standards and conventions

---

## 7. Relation Mapping

**Definition:** The establishment and documentation of typed relationships between artifacts.

**Relationship Types:**
- **Derived From** - Artifact created from another
- **Included In** - Artifact is part of a larger work
- **Uses Procedure** - Artifact follows a defined procedure
- **Has Analysis** - Artifact has analytical commentary
- **Superseded By** - Artifact replaced by newer version
- **References** - Artifact cites another
- **Depends On** - Artifact requires another

**Activities:**
- Declare relationships in PMF
- Generate reciprocal links automatically
- Maintain relationship integrity
- Document relationship metadata

**Output:** A web of interconnected artifacts with typed relationships.

**Key Rules:**
- Relationships are bidirectional where appropriate
- Relationship changes are logged
- Circular dependencies are flagged
- Broken links trigger alerts

---

## 8. Active Use

**Definition:** The stage where an artifact is currently being edited, referenced, or included in active workflows.

**Characteristics:**
- Mutable (can be edited)
- Accessible for current work
- Included in active builds/workflows
- Referenced by active manuscripts
- Part of current creative output

**Activities:**
- Ongoing editing and refinement
- Active referencing
- Workflow integration
- Manuscript inclusion

**Status:** Current and operational

---

## 9. Supersession

**Definition:** When a newer version replaces an older one, marking the previous version as superseded.

**Activities:**
- Establish supersession relationship
- Document supersession reason
- Maintain provenance chain
- Mark older version as superseded
- Redirect references where appropriate

**Output:** Superseded artifacts remain in the provenance chain but are no longer considered current.

**Key Principles:**
- Superseded artifacts are not deleted
- Full history is preserved
- Supersession is reversible (with justification)
- Multiple versions can coexist

---

## 10. Archive

**Definition:** The stage for artifacts no longer in active use but preserved for provenance, reference, or restoration.

**Characteristics:**
- Read-only access
- Excluded from active workflows
- Preserved for historical reference
- Available for restoration
- Maintains full metadata

**Activities:**
- Transfer to archive storage
- Update status in PMF
- Remove from active indexes
- Maintain accessibility for reference
- Preserve all relationships

**Access:** Reference and restoration only

---

## 11. Obsoletion

**Definition:** A formal archival action that moves artifacts to permanent archival status after comprehensive dependency analysis.

**Process:**

### 11.1 Obsoletion Request
- Formal request initiated by authorized personnel
- Includes justification and impact assessment
- Specifies target artifact(s)

### 11.2 Dependency Analysis
DOCSYS performs comprehensive dependency analysis:
- Identify all artifacts that reference the target
- Check for active use in workflows
- Verify no active dependencies exist
- Analyze relationship chains

### 11.3 Decision Points

**If Dependencies Exist:**
- Request is **HALTED**
- Dependencies are reported
- Requester must resolve dependencies first
- Request can be resubmitted after resolution

**If Request is Invalid:**
- Request is **ABORTED**
- Reasons documented
- No changes made to artifact status

**If No Dependencies and Valid:**
- Request is **APPROVED**
- Obsoletion proceeds

### 11.4 Obsoletion Actions
- Move artifact to Archive tier
- Update status to "Obsolete"
- Log action in PMF with timestamp and reason
- Maintain full provenance chain
- Preserve all metadata and relationships
- Generate obsoletion report

**Output:** Obsolete artifacts remain accessible for historical reference but are formally retired from all active use.

**Key Safeguards:**
- Cannot obsolete artifacts with active dependencies
- Obsoletion is logged and auditable
- Full restoration is possible
- Provenance chain remains intact

---

## Lifecycle State Diagram

```
[Capture] → [Intake] → [Versioning] ⟷ [Active Use]
                            ↓              ↓
                     [Controlled Print] [Analysis]
                            ↓              ↓
                       [Relation Mapping]  
                            ↓
                       [Supersession]
                            ↓
                        [Archive]
                            ↓
                      [Obsoletion]
```

Note: Procedures and workflows can be created at any stage and influence multiple lifecycle phases.

---

## Provenance Metadata File (PMF)

Each artifact maintains a PMF that records:
- All lifecycle stage transitions
- Version history
- Relationship declarations
- Timestamp for each action
- Actor/agent responsible for each action
- Justification for significant actions
- Current lifecycle stage

---

## Best Practices

### For Capture
- Document capture method and tools
- Record original format and quality
- Note any degradation or quality issues
- Generate TSN immediately

### For Intake
- Use consistent naming conventions
- Apply appropriate type prefixes
- Complete all required metadata
- Link to source materials

### For Versioning
- Document reason for new version
- Maintain clear version numbering
- Link versions in provenance chain
- Never delete older versions

### For Active Use
- Track all references and dependencies
- Document ongoing changes
- Maintain clear status indicators
- Update PMF regularly

### For Archive/Obsoletion
- Complete dependency analysis
- Document archival reasoning
- Preserve full context
- Ensure restoration capability

---

## Integration with KABDMSV2

The DOCSYS lifecycle stages integrate with KABDMSV2 standards:

- **File Naming:** See [Configuration Standards](standards/configuration-standards.md)
- **Version Control:** See [Coding Standards](standards/coding-standards.md)
- **Documentation:** See [Documentation Standards](standards/documentation-standards.md)
- **File Organization:** See [File Organization Standards](standards/file-organization.md)

---

## Audit and Compliance

All lifecycle transitions must be:
- Logged with timestamp
- Attributed to an actor/agent
- Documented with justification
- Preserved in PMF
- Auditable through history

---

## Glossary

- **TSN (Trace Serial Number):** Unique identifier assigned at capture
- **PMF (Provenance Metadata File):** Complete history and metadata record for an artifact
- **Artifact:** Any document, file, or creative work managed by DOCSYS
- **Supersession:** The act of replacing an artifact with a newer version
- **Obsoletion:** Formal retirement of an artifact from active use

---

## Revision History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0.0 | 2025-12-23 | Initial documentation of DOCSYS lifecycle stages | KABDMSV2 Project |

---

This lifecycle provides a consistent, auditable framework for managing all artifacts within DOCSYS, ensuring clarity, traceability, and long-term preservation.
