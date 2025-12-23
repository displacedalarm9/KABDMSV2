# Documentation Standards

## Purpose

Good documentation is essential for project success. These standards ensure documentation is clear, consistent, and helpful.

## Types of Documentation

### 1. README Files

Every directory should have a README.md explaining its purpose.

**Structure:**
```markdown
# Directory/Project Name

Brief description (1-2 sentences)

## Purpose/Overview

Detailed explanation

## Contents/Structure

What's in this directory

## Usage

How to use or interact with contents
```

### 2. Code Documentation

#### Inline Comments
- Explain complex logic
- Document assumptions
- Note limitations or gotchas
- Keep comments updated with code

#### Function/Method Documentation
```python
def process_data(input_file: str, options: dict) -> dict:
    """
    Process data from the input file with specified options.
    
    Args:
        input_file: Path to the input file
        options: Dictionary of processing options
        
    Returns:
        Dictionary containing processed results
        
    Raises:
        FileNotFoundError: If input file doesn't exist
        ValueError: If options are invalid
    """
```

### 3. API Documentation

- Document all public APIs
- Include parameter descriptions
- Provide usage examples
- Document return values and errors

### 4. User Guides

- Step-by-step instructions
- Clear prerequisites
- Expected outcomes
- Troubleshooting section

## Markdown Style

### Headers

```markdown
# H1 - Main Title (one per document)
## H2 - Major Sections
### H3 - Subsections
#### H4 - Detailed Points
```

### Code Blocks

Always specify language for syntax highlighting:

````markdown
```python
def example():
    pass
```
````

### Links

- Use descriptive link text
- Prefer relative links for internal docs
- Check links aren't broken

```markdown
[Good: Descriptive text](./path/to/doc.md)
[Bad: Click here](./path/to/doc.md)
```

### Lists

- Use `-` for unordered lists
- Use `1.` for ordered lists
- Indent nested items with 2 spaces

### Tables

```markdown
| Column 1 | Column 2 |
|----------|----------|
| Data     | Data     |
```

## File Structure

### README.md Structure

1. Title
2. Brief description
3. Overview/Purpose
4. Installation/Setup
5. Usage/Examples
6. Documentation links
7. Contributing
8. License

### Technical Documentation Structure

1. Title and description
2. Prerequisites
3. Concepts/Background
4. Detailed content
5. Examples
6. Troubleshooting
7. Related documentation

## Writing Style

### Voice and Tone

- Use clear, concise language
- Write in present tense
- Use active voice
- Be direct and specific

```markdown
✓ "Click the Submit button"
✗ "The Submit button should be clicked"

✓ "The system processes requests"
✗ "Requests are processed by the system"
```

### Terminology

- Use consistent terminology
- Define acronyms on first use
- Avoid jargon when possible
- Maintain a glossary if needed

### Formatting

- One sentence per line (in source)
- Use bold for UI elements: **Submit**
- Use italics for emphasis: *important*
- Use code formatting for: `code`, `commands`, `filenames`

## Examples

Always include examples:
- Show realistic use cases
- Include expected output
- Cover common scenarios
- Note any prerequisites

## Maintenance

- Review documentation quarterly
- Update docs with code changes
- Remove outdated information
- Fix broken links

## Screenshots and Diagrams

When helpful:
- Include alt text for accessibility
- Keep images up to date
- Use appropriate file formats (PNG for screenshots, SVG for diagrams)
- Store in `docs/images/` directory

## Version-Specific Documentation

- Indicate version requirements
- Note deprecated features
- Provide migration guides
- Archive old documentation

## Accessibility

- Use descriptive link text
- Provide alt text for images
- Use semantic heading structure
- Ensure good contrast in diagrams

## Review Process

Documentation changes should:
- Be reviewed like code
- Be tested (follow instructions)
- Check for spelling/grammar
- Verify links work
- Ensure consistency

## Tools and Resources

- Markdown linters for consistency
- Spell checkers
- Link checkers
- Preview tools

## Questions?

- Unclear documentation is a bug - report it
- Suggest improvements via pull requests
- Ask questions in issues
