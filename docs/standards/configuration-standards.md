# Configuration Standards

## Overview

KABDMSV2 uses configuration files to manage system nodes and settings. This document defines the standards for configuration file format and structure.

## File Naming Convention

Configuration files follow this pattern:

```
config_[NODE-TYPE]-[NUMBER]_[Description].xml
```

### Components

- **NODE-TYPE**: Category of the node (e.g., ARC, OPS, VR)
  - `ARC`: Archival nodes
  - `OPS`: Operational nodes
  - `VR`: Virtual/VR-related nodes
  
- **NUMBER**: Three-digit identifier (e.g., 001, 002, 003)

- **Description**: Descriptive name in PascalCase (e.g., CustomArchival, Legion5Gen10)

### Examples

```
config_NODE-ARC-003_CustomArchival.xml
config_NODE-OPS-001_Legion5Gen10.xml
config_NODE-VR-002_LegionPro5Gen10.xml
```

## XML Structure

### Basic Template

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <metadata>
    <nodeId>NODE-TYPE-###</nodeId>
    <name>Descriptive Name</name>
    <description>Brief description of this node</description>
    <created>YYYY-MM-DD</created>
    <updated>YYYY-MM-DD</updated>
  </metadata>
  
  <settings>
    <setting key="property1" value="value1" />
    <setting key="property2" value="value2" />
  </settings>
  
  <paths>
    <path type="data" location="/path/to/data" />
    <path type="backup" location="/path/to/backup" />
  </paths>
</configuration>
```

### XML Formatting Rules

1. **Indentation**: Use 2 spaces per level
2. **Encoding**: Always UTF-8
3. **Attributes**: Quote values with double quotes
4. **Empty Elements**: Use self-closing tags `<element />`
5. **Comments**: Use XML comments for documentation

```xml
<!-- This is a section comment -->
<section>
  <!-- This explains a specific setting -->
  <setting key="example" value="value" />
</section>
```

## Configuration Elements

### Required Elements

Every configuration must include:

```xml
<metadata>
  <nodeId>NODE-TYPE-###</nodeId>
  <name>Display Name</name>
</metadata>
```

### Optional Elements

```xml
<description>Detailed description</description>
<created>YYYY-MM-DD</created>
<updated>YYYY-MM-DD</updated>
<version>1.0.0</version>
<tags>
  <tag>archival</tag>
  <tag>production</tag>
</tags>
```

## Node Types and IDs

### Node Type Prefixes

- **ARC**: Archival and backup systems
- **OPS**: Operational/production systems
- **VR**: Virtual reality or virtual machines
- **DEV**: Development systems
- **TEST**: Testing systems

### ID Assignment

- Start at 001 for each type
- Use sequential numbering
- Pad with zeros (001, 002, not 1, 2)
- Document node registry separately

## Settings Format

### Boolean Values

```xml
<setting key="enabled" value="true" />
<setting key="disabled" value="false" />
```

### Numeric Values

```xml
<setting key="port" value="8080" />
<setting key="timeout" value="30" />
```

### String Values

```xml
<setting key="hostname" value="localhost" />
<setting key="environment" value="production" />
```

### Path Values

```xml
<path type="data" location="/absolute/path/to/data" />
```

- Use absolute paths when possible
- Use forward slashes (/) even on Windows
- Document path requirements

## Validation

### Required Checks

1. Well-formed XML
2. Valid node ID format
3. Unique node IDs within system
4. Required elements present
5. Valid attribute values

### Schema Validation

Consider using XML Schema (XSD) for validation:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <!-- Schema definition -->
</xs:schema>
```

## Documentation in Config Files

### Inline Comments

```xml
<!-- Data storage configuration -->
<paths>
  <!-- Primary data location -->
  <path type="data" location="/data/primary" />
  
  <!-- Backup location (daily snapshots) -->
  <path type="backup" location="/data/backup" />
</paths>
```

### Section Headers

```xml
<!-- ============================================ -->
<!-- System Paths Configuration                   -->
<!-- ============================================ -->
<paths>
  ...
</paths>
```

## Security Considerations

### Sensitive Data

- Never include passwords or API keys
- Use environment variables for secrets
- Document where credentials should be stored
- Use placeholders for sensitive values

```xml
<!-- Use environment variable: DB_PASSWORD -->
<setting key="database_password" value="${DB_PASSWORD}" />
```

### Access Control

- Store configs in secure locations
- Limit read/write permissions
- Version control non-sensitive configs only
- Encrypt sensitive configurations

## Version Control

### What to Commit

✓ Template configurations
✓ Example configurations
✓ Non-sensitive production configs

### What to Exclude

✗ Configurations with credentials
✗ Personal/local configurations
✗ Development-specific configs with sensitive paths

## Testing Configurations

- Validate XML syntax
- Test with actual system
- Document test procedures
- Maintain test configurations

## Migration and Updates

When updating configuration format:

1. Document changes
2. Provide migration script if needed
3. Support old format temporarily
4. Update all templates
5. Notify users of changes

## Related Standards

- [Coding Standards](./coding-standards.md)
- [Documentation Standards](./documentation-standards.md)
- [File Organization](./file-organization.md)
