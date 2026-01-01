# Templates Directory

This directory contains standardized templates for creating new prompts and roles in the QA Prompt Library.

## Available Templates

### 1. Prompt Template (`prompt-template.md`)
Use this template when creating new prompt files for any category.

**When to use**:
- Adding new test generation prompts
- Creating automation prompts
- Developing AI-assisted QA prompts
- Any scenario-based prompt creation

**Key features**:
- Metadata section with difficulty, tags, and versioning
- Structured prompt format with placeholders
- Customization guide for users
- Example usage with expected output
- Related prompts and resources

### 2. Role Template (`role-template.md`)
Use this template when creating new Cursor AI roles or framework-specific guides.

**When to use**:
- Adding support for new testing frameworks
- Creating tool-specific expert roles
- Developing specialized testing roles

**Key features**:
- Role overview and competencies
- Responsibilities and best practices
- Code examples and patterns
- Problem-solving approach
- Common use cases and pitfalls

## How to Use These Templates

### Step 1: Copy the Template
```bash
# For a new prompt
cp templates/prompt-template.md [category]/[your-prompt-name].md

# For a new role
cp templates/role-template.md cursor-ai/[framework-name]-role.md
```

### Step 2: Fill in the Placeholders
- Replace all `[BRACKETED_PLACEHOLDERS]` with actual content
- Update metadata (difficulty, tags, date, version)
- Add specific examples relevant to your topic
- Include real code snippets where applicable

### Step 3: Customize Sections
- Remove sections that don't apply
- Add additional sections if needed
- Ensure all links work correctly
- Validate code examples

### Step 4: Review Quality
Use this checklist before submitting:
- [ ] All placeholders replaced with actual content
- [ ] Metadata is complete and accurate
- [ ] At least one example usage provided
- [ ] Code examples are tested and working
- [ ] Related prompts are linked
- [ ] Follows naming conventions (kebab-case)
- [ ] Tags are appropriate and consistent
- [ ] No typos or formatting issues

## Template Customization Guidelines

### Metadata Standards
- **Difficulty**: 
  - `Beginner`: For newcomers to testing or the framework
  - `Intermediate`: For professionals with basic experience
  - `Advanced`: For complex scenarios and edge cases

- **Estimated Time**:
  - `5min`: Quick reference or simple prompts
  - `15min`: Standard comprehensive prompts
  - `30min`: Detailed prompts with multiple scenarios
  - `1hr`: Deep dive or complex multi-step prompts

- **Tags**: Use existing tags when possible
  - Complexity: `#beginner`, `#intermediate`, `#advanced`
  - Domain: `#web`, `#mobile`, `#api`, `#desktop`
  - Framework: `#selenium`, `#playwright`, `#cypress`, etc.
  - Language: `#java`, `#python`, `#javascript`, etc.

### Version Control
- Start with version `1.0` for new prompts
- Increment minor version (1.1, 1.2) for updates
- Increment major version (2.0) for significant changes
- Update `Last Updated` date with each change

## Examples

See the `examples/` directory for real-world implementations of these templates:
- [Sample Automation Prompt](../examples/sample-automation-code.md)
- [Sample Test Case Prompt](../examples/sample-test-cases.md)

## Need Help?

- Review existing prompts for inspiration
- Check [contribution guidelines](../docs/contribution-guidelines.md)
- Read the [prompt writing guide](../docs/prompt-writing-guide.md)
- Open an issue if you have questions

---

**Remember**: Templates are starting points. Customize them to best serve your specific use case while maintaining consistency with the library's standards.
