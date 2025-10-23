# Contributing to Markdown in Action

Thank you for your interest in contributing to this project! This guide will help you understand how to contribute effectively.

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Documentation Standards](#documentation-standards)
- [Submission Guidelines](#submission-guidelines)
- [Development Setup](#development-setup)

## Code of Conduct

This project follows a standard code of conduct. Please be respectful and inclusive in all interactions.

## How to Contribute

### Reporting Issues
- Use the [issue templates](.github/ISSUE_TEMPLATE/) provided
- Search existing issues before creating new ones
- Provide clear, detailed descriptions
- Include examples when applicable

### Suggesting Enhancements
- Check if the enhancement has already been suggested
- Provide clear use cases and examples
- Explain why this would be valuable to the community

### Contributing Documentation
- Follow the [documentation standards](#documentation-standards)
- Ensure examples are practical and tested
- Update related files when necessary
- Check links and cross-references

## Documentation Standards

### File Organization
- Use descriptive, lowercase filenames with hyphens: `api-reference.md`
- Organize files logically in appropriate directories
- Update navigation and index files when adding new content

### Writing Style
- **Clear and concise**: Write for your audience
- **Practical examples**: Include real-world use cases
- **Consistent formatting**: Follow established patterns
- **Cross-references**: Link to related documentation

### Markdown Guidelines
```markdown
# Use consistent header hierarchy
## Second level headers for main sections  
### Third level for subsections

**Bold** for emphasis on important terms
*Italic* for subtle emphasis
`Code` for technical terms and commands

- Use consistent list formatting
- Keep lines under 100 characters when possible
- Add blank lines between sections
```

### Example Structure
```markdown
# Document Title

Brief description of the document's purpose.

## Table of Contents
- [Section 1](#section-1)
- [Section 2](#section-2)

## Section 1

Content with practical examples:

### Example
```language
// Code example
```

**Explanation**: What this example demonstrates.

## Related Documents
- [Previous: Setup](setup.md)
- [Next: Configuration](configuration.md)
```

## Submission Guidelines

### Pull Request Process
1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/add-new-examples`
3. **Make** your changes following the documentation standards
4. **Test** all links and examples
5. **Commit** with clear messages: `Add examples for table formatting`
6. **Submit** a pull request with description

### Pull Request Template
When submitting a PR, include:
- **Description**: What changes you made and why
- **Type of Change**: Documentation update, new examples, etc.
- **Testing**: How you verified the changes work
- **Related Issues**: Reference any related issues

### Review Process
- All submissions require review by maintainers
- Reviews focus on accuracy, clarity, and consistency
- Feedback will be provided for improvements
- Once approved, changes will be merged

## Development Setup

### Local Environment
```bash
# Clone the repository
git clone https://github.com/trungnd6/md-in-action.git
cd md-in-action

# Create a new branch for your changes
git checkout -b feature/your-feature-name

# Make your changes and test locally
# Verify all links work correctly
```

### Testing Documentation
```bash
# Install markdown link checker (optional)
npm install -g markdown-link-check

# Check for broken links
find . -name "*.md" -exec markdown-link-check {} \;

# Preview locally (if using a static site generator)
# For GitHub Pages testing:
bundle exec jekyll serve  # or your preferred method
```

### File Validation
Before submitting:
- [ ] All internal links work correctly
- [ ] External links are valid and appropriate
- [ ] Examples are tested and accurate
- [ ] Formatting is consistent with existing files
- [ ] New files are referenced in navigation/index files

## Examples of Good Contributions

### Adding New Platform Examples
If you want to add examples for a new platform (e.g., Confluence, Jira, etc.):

1. Add a new subsection under "Platform-Specific Features"
2. Include practical examples showing the syntax differences
3. Explain the platform-specific use cases
4. Test the examples on the actual platform

### Improving Existing Examples
- Add more realistic use cases
- Clarify confusing explanations
- Fix outdated information
- Add missing cross-references

### Organizing Content
- Improve file structure and navigation
- Add missing index files
- Create better cross-linking between related topics
- Enhance table of contents

## Questions?

If you have questions about contributing:
- Check existing [issues](https://github.com/trungnd6/md-in-action/issues)
- Create a new issue with the "question" label
- Reference this contributing guide in discussions

---

**Thank you for helping make this Markdown guide better for everyone!** 🚀

## Related Documents
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Main README](README.md)
- [Documentation Structure](docs/README.md)