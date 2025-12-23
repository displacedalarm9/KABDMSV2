# File Organization Standards

## Repository Structure

KABDMSV2 follows a clear organizational structure to maintain order and facilitate navigation.

## Top-Level Structure

```
KABDMSV2/
├── .git/                   # Git repository data
├── .gitignore              # Git ignore rules
├── LICENSE                 # Project license
├── README.md               # Project overview
├── CODE_OF_CONDUCT.md      # Community guidelines
├── CONTRIBUTING.md         # Contribution guidelines
├── SECURITY.md             # Security policy
├── topics.json             # Project metadata
├── docs/                   # Documentation
│   ├── standards/          # Standards documentation
│   └── guides/             # User and developer guides
├── config_*.xml            # Configuration files
├── scripts/                # Utility scripts
├── templates/              # File templates
└── tests/                  # Test files
```

## Directory Purposes

### `/docs/`
Documentation for the project

- `standards/` - Project standards and conventions
- `guides/` - How-to guides and tutorials
- `api/` - API documentation
- `images/` - Documentation images and diagrams

### `/scripts/`
Utility scripts and automation tools

- Organized by purpose (backup, migration, setup, etc.)
- Include README in subdirectories
- Make scripts executable where appropriate

### `/templates/`
Template files for various purposes

- Configuration templates
- Document templates
- Code scaffolding templates

### `/tests/`
Test files and test data

- Mirror source structure
- Include test utilities
- Separate unit, integration, and system tests

### Root Directory

Keep the root directory clean:
- Only essential files at root level
- Configuration files follow naming convention
- Documentation files (README, LICENSE, etc.)

## File Naming Conventions

### General Rules

1. **Use descriptive names**: `user-authentication.md` not `file1.md`
2. **Use lowercase**: `my-file.txt` not `My-File.txt`
3. **Use hyphens for spaces**: `file-name.txt` not `file_name.txt` or `file name.txt`
4. **Be consistent**: Follow existing patterns in the directory

### Specific File Types

#### Markdown Files
```
README.md           # Always capitalized
CONTRIBUTING.md     # Always capitalized
user-guide.md       # Lowercase with hyphens
```

#### Configuration Files
```
config_NODE-TYPE-###_Description.xml
```

See [Configuration Standards](./configuration-standards.md) for details.

#### Script Files
```
backup-data.sh
migrate-configs.py
setup-environment.js
```

#### JSON/Data Files
```
topics.json
metadata.json
config-schema.json
```

## File Organization Best Practices

### 1. Logical Grouping

Group related files together:
```
docs/
  guides/
    getting-started.md
    advanced-usage.md
  standards/
    coding-standards.md
    documentation-standards.md
```

### 2. Depth Limit

- Avoid deeply nested directories (max 4-5 levels)
- If nesting gets deep, reconsider organization
- Use README files to explain structure

### 3. README Files

Every directory should have a README.md:
```markdown
# Directory Name

Brief description of the directory's purpose.

## Contents

- `file1.md` - Description
- `file2.md` - Description

## Usage

How to use or interact with these files.
```

### 4. Avoid Duplication

- Don't duplicate files across directories
- Use symlinks if necessary (document them)
- Reference shared resources via documentation

### 5. Archive Old Files

For outdated files:
- Create `archive/` subdirectory
- Move old files there with date prefix
- Document why files were archived

```
archive/
  2024-01-15_old-config.xml
  2024-03-20_deprecated-script.sh
```

## Special Files

### Configuration Files

- Keep at root level if project-wide
- Group in `/config/` if many configurations
- Follow naming convention
- Document each configuration

### Documentation

- Keep high-level docs at root (README, etc.)
- Detailed docs in `/docs/`
- API docs in `/docs/api/`
- Keep docs close to related code when appropriate

### Scripts and Tools

- Keep utility scripts in `/scripts/`
- Include usage documentation
- Make executable: `chmod +x script.sh`
- Use appropriate shebang: `#!/bin/bash`

### Templates

- Store in `/templates/`
- Provide example usage
- Keep templates minimal but functional
- Document template variables

## Temporary Files

### Development

Create temporary files in `/tmp/`:
```bash
mkdir -p /tmp/kabdms-dev
# Work with temporary files
rm -rf /tmp/kabdms-dev
```

### .gitignore

Include in `.gitignore`:
```
# Temporary files
*.tmp
*.temp
temp/
tmp/

# Build artifacts
build/
dist/
```

## Data Separation

### Important Principle

KABDMSV2 separates:
- **Management code** (this repository)
- **Actual data** (separate private repository)

Never commit actual data files to KABDMSV2:
```
# .gitignore
data/
*.personal
*.private
financial/
logs/personal-*
```

## File Size Considerations

### Small Files
- Most source and config files
- Keep under 1 MB
- Suitable for Git

### Large Files
- Documentation images: < 1 MB preferred
- Consider compression
- Use Git LFS if needed

### Very Large Files
- Don't commit to repository
- Store in appropriate data repository
- Document location in README

## Moving and Renaming Files

When reorganizing:

1. Plan the new structure
2. Update documentation first
3. Move files with git: `git mv old new`
4. Update references and links
5. Test that everything works
6. Commit with descriptive message

## Platform Considerations

### Cross-Platform Compatibility

- Use forward slashes in paths: `/path/to/file`
- Avoid special characters in filenames
- Be case-aware (case-sensitive on Linux/Mac)
- Use UTF-8 encoding

### Line Endings

- Configure Git for line endings:
```
# .gitattributes
* text=auto
*.sh text eol=lf
*.bat text eol=crlf
```

## Maintenance

### Regular Review

- Review organization quarterly
- Remove unused files
- Archive old content
- Update documentation

### Refactoring

When restructuring:
- Document the changes
- Provide migration guide
- Update all references
- Communicate to team

## Related Standards

- [Coding Standards](./coding-standards.md)
- [Documentation Standards](./documentation-standards.md)
- [Configuration Standards](./configuration-standards.md)
