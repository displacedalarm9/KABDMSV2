# Coding Standards

## General Principles

1. **Clarity over Cleverness**: Write code that is easy to understand
2. **Consistency**: Follow existing patterns in the codebase
3. **Simplicity**: Keep solutions simple and maintainable
4. **Documentation**: Document complex logic and public APIs

## File Naming

- Use lowercase with hyphens for directories: `my-directory`
- Use descriptive names that indicate purpose
- Configuration files: `config_[TYPE]-[ID]_[Description].xml`

## Code Style

### XML Configuration Files

```xml
<!-- Use 2-space indentation -->
<!-- Include descriptive attributes -->
<configuration>
  <node id="NODE-TYPE-###" name="Descriptive Name">
    <setting key="value" />
  </node>
</configuration>
```

### JSON Files

```json
{
  "property": "value",
  "array": ["item1", "item2"],
  "nested": {
    "key": "value"
  }
}
```

- Use 2-space indentation
- Use camelCase for property names
- Include trailing newline

### Python (if applicable)

- Follow PEP 8 style guide
- Use 4-space indentation
- Maximum line length: 100 characters
- Use type hints for function signatures

### JavaScript/TypeScript (if applicable)

- Use 2-space indentation
- Use semicolons
- Use const/let, never var
- Prefer arrow functions for callbacks

## Comments

- Write comments for "why", not "what"
- Keep comments up to date with code changes
- Use TODO comments sparingly with issue references

```python
# Good: Explains reasoning
# Using batch processing to avoid memory issues with large datasets

# Bad: States the obvious
# Set x to 10
x = 10
```

## Error Handling

- Handle errors gracefully
- Provide meaningful error messages
- Log errors appropriately
- Don't silently ignore errors

## Testing

- Write tests for new functionality
- Keep tests simple and focused
- Test edge cases and error conditions
- Maintain test coverage

## Version Control

- Write clear commit messages
- Keep commits focused on single changes
- Reference issue numbers when applicable
- Don't commit commented-out code

### Commit Message Format

```
Short summary (50 chars or less)

More detailed explanation if needed. Wrap at 72 characters.
Explain what and why, not how.

Fixes #123
```

## Security

- Never commit sensitive data
- Validate all inputs
- Use secure defaults
- Follow principle of least privilege

## Performance

- Optimize when necessary, not prematurely
- Profile before optimizing
- Document performance considerations
- Consider scalability from the start

## Dependencies

- Minimize external dependencies
- Keep dependencies up to date
- Document why dependencies are needed
- Use version pinning for stability

## Code Review

All code changes should:
- Pass automated tests
- Follow these standards
- Be reviewed by another contributor
- Address review feedback

## Questions?

When standards don't cover a situation:
- Look at similar existing code
- Ask via GitHub issues
- Propose a standards update
