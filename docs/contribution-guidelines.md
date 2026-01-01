# Contribution Guidelines

## Welcome Contributors! 🎉

Thank you for your interest in contributing to the QA Prompt Library. This document provides guidelines for contributing new prompts and improvements.

## How to Contribute

### 1. Types of Contributions

We welcome:
- **New Prompts**: Add prompts for scenarios not yet covered
- **Prompt Improvements**: Enhance existing prompts with better examples or clarity
- **Bug Fixes**: Correct errors in existing prompts
- **Documentation**: Improve README, examples, or this guide
- **Examples**: Add real-world usage examples

### 2. Contribution Process

1. **Fork the Repository**
2. **Create a Branch**: `git checkout -b feature/your-prompt-name`
3. **Make Changes**: Add or modify prompts following our guidelines
4. **Test Your Prompts**: Verify prompts work with AI tools
5. **Commit Changes**: Use clear, descriptive commit messages
6. **Submit Pull Request**: Describe your changes clearly

### 3. Prompt Writing Guidelines

**IMPORTANT**: All new prompts must follow our standardized template. See:
- [Prompt Template](../templates/prompt-template.md) - Standard prompt structure
- [Role Template](../templates/role-template.md) - For Cursor AI roles
- [Prompt Writing Guide](prompt-writing-guide.md) - Comprehensive guide
- [Tagging System](tagging-system.md) - Tag reference

#### Structure
- Use the standardized prompt template from `/templates/`
- Include complete metadata (difficulty, tags, version, date)
- Number your prompts for easy reference
- Include placeholders in [BRACKETS]
- Provide context and examples
- Add related prompts section

#### Content
- **Be Specific**: Avoid vague instructions
- **Be Practical**: Focus on real-world scenarios
- **Be Complete**: Include all necessary context
- **Be Clear**: Use simple, unambiguous language
- **Include Examples**: At least one filled example
- **Add Tags**: Use appropriate tags from the tagging system

#### Required Sections
Every prompt must include:
- Metadata (difficulty, time, prerequisites, tags, version)
- Clear objective statement
- Structured prompt template
- Customization guide for placeholders
- Example usage
- Expected output description
- Related prompts
- Additional resources

### 4. File Organization

- Place prompts in appropriate category folders
- Use kebab-case for file names: `my-new-prompts.md`
- Include difficulty suffix for variants: `selenium-beginner.md`, `selenium-advanced.md`
- Follow existing file structure
- Update category README.md when adding prompts
- Update PROMPT_INDEX.md with new prompt entries
- Add to main README if creating new categories

### 5. Quality Standards

✅ **Good Prompt Example**:
```
Generate test cases for login functionality:

Feature: User Login
Fields: Username, Password
Requirements: [DESCRIBE_REQUIREMENTS]

Create test cases for:
- Valid credentials
- Invalid username
- Invalid password
- Empty fields
- SQL injection attempts
```

❌ **Poor Prompt Example**:
```
Make some test cases for login
```

### 6. Testing Your Prompts

Before submitting:
1. **Use the template**: Copy from `/templates/prompt-template.md`
2. **Fill all sections**: Complete all required metadata and sections
3. **Test with AI tools**: Test with at least one AI tool (ChatGPT, Claude, Gemini, etc.)
4. **Verify output quality**: Ensure the output is useful and accurate
5. **Check placeholders**: Ensure placeholders are clear and well-explained
6. **Validate tags**: Use tags from the tagging system guide
7. **Review formatting**: Check for typos and markdown formatting
8. **Add to index**: Update PROMPT_INDEX.md with your new prompt

### 7. Documentation

- Add comments explaining complex prompts
- Include "Best Practices" sections
- Provide "Tips for Using These Prompts"
- Add examples of expected output when helpful

### 8. Code of Conduct

- Be respectful and professional
- Provide constructive feedback
- Help others learn and improve
- Give credit where due

## Review Process

1. **Submission**: Submit PR with clear description
2. **Review**: Maintainers review within 1 week
3. **Feedback**: Address any requested changes
4. **Merge**: Approved PRs are merged
5. **Credit**: Contributors are acknowledged

## Questions?

- Open an issue for questions
- Tag issues appropriately
- Be patient and respectful

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Credited in documentation

---

Thank you for helping make QA testing more efficient with AI! 🚀
