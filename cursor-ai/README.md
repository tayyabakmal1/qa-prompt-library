# Cursor AI Automation Testing Roles

This folder contains specialized role files for Cursor AI to assist with various test automation frameworks, patterns, and approaches.

## Available Roles

### Testing Frameworks

1. **[selenium-role.md](selenium-role.md)** - Selenium WebDriver Expert
   - Selenium 4.x features and best practices
   - Cross-browser testing strategies
   - Element locator strategies and synchronization
   - Page Object Model implementation with Selenium
   - Framework design and CI/CD integration

2. **[playwright-role.md](playwright-role.md)** - Playwright Automation Expert
   - Modern web testing with auto-waiting
   - Network interception and API mocking
   - Visual regression testing
   - Multi-browser and mobile emulation
   - Trace viewer and debugging capabilities

3. **[cypress-role.md](cypress-role.md)** - Cypress Testing Expert
   - JavaScript-based E2E testing
   - Time-travel debugging
   - Network stubbing and request interception
   - Component testing
   - Custom commands and app actions pattern

### Design Patterns & Approaches

4. **[pom-role.md](pom-role.md)** - Page Object Model Expert
   - POM design principles and best practices
   - Component-based page objects
   - Fluent interface design
   - Multi-language POM examples (Java, Python, TypeScript)
   - Base classes and inheritance strategies

5. **[bdd-role.md](bdd-role.md)** - Behavior-Driven Development Expert
   - Gherkin syntax and feature file writing
   - Cucumber, SpecFlow, Behave, Pytest-BDD
   - Step definition implementation
   - Hooks and test data management
   - Living documentation practices

6. **[data-driven-role.md](data-driven-role.md)** - Data-Driven Testing Expert
   - Test data separation and management
   - Multiple data sources (Excel, CSV, JSON, Database)
   - Parameterization techniques
   - Test data builders and factories
   - Data-driven framework design

7. **[framework-design-role.md](framework-design-role.md)** - Framework Architecture Expert
   - Comprehensive framework design
   - Configuration management
   - Reporting and logging strategies
   - CI/CD integration
   - Docker and parallel execution

### Mobile Testing

8. **[appium-role.md](appium-role.md)** - Appium Mobile Automation Expert
   - Appium 2.x architecture and setup
   - iOS (XCUITest) and Android (UiAutomator2) automation
   - Mobile gestures and touch actions
   - Cross-platform mobile testing
   - Cloud device farm integration

9. **[mobile-testing-role.md](mobile-testing-role.md)** - Mobile Testing Strategy Expert
   - Mobile-specific test scenarios (lifecycle, permissions, gestures)
   - Network connectivity testing
   - Device coverage strategies
   - Performance and battery testing
   - Platform-specific considerations

10. **[mobile-performance-role.md](mobile-performance-role.md)** - Mobile Performance Testing Expert
   - App launch time measurement (cold/warm/hot start)
   - Memory leak detection
   - Battery consumption analysis
   - Frame rate and UI smoothness testing
   - Performance optimization strategies

## How to Use These Roles

### In Cursor AI

1. **Reference a specific role** in your prompt:
   ```
   @selenium-role.md help me create a robust page object for a login page
   ```

2. **Combine multiple roles** for complex scenarios:
   ```
   Using @pom-role.md and @data-driven-role.md, create a login test with multiple user credentials from Excel
   ```

3. **Ask for framework setup**:
   ```
   @framework-design-role.md help me set up a complete test automation framework structure
   ```

### Role Selection Guide

Choose the appropriate role based on your needs:

- **Starting a new project?** → Use `framework-design-role.md`
- **Working with Selenium?** → Use `selenium-role.md`
- **Using Playwright?** → Use `playwright-role.md`
- **Using Cypress?** → Use `cypress-role.md`
- **Testing mobile apps?** → Use `appium-role.md` or `mobile-testing-role.md`
- **Mobile performance testing?** → Use `mobile-performance-role.md`
- **Implementing page objects?** → Use `pom-role.md`
- **Writing BDD scenarios?** → Use `bdd-role.md`
- **Need data-driven tests?** → Use `data-driven-role.md`

## Role Capabilities

Each role provides:

✅ **Expert guidance** on best practices
✅ **Code examples** in multiple languages
✅ **Framework patterns** and architectures
✅ **Problem-solving approaches** for common challenges
✅ **Design principles** and recommendations
✅ **Integration strategies** with CI/CD tools

## Example Use Cases

### Example 1: Create a Selenium Page Object
```
@selenium-role.md and @pom-role.md

Create a page object for a registration form with the following fields:
- First Name
- Last Name
- Email
- Password
- Confirm Password
- Submit button

Include proper waits and validation methods.
```

### Example 2: Set Up BDD Tests
```
@bdd-role.md

Create a Cucumber feature file and step definitions for user login with:
- Valid credentials
- Invalid credentials
- Locked account
- Empty fields
```

### Example 3: Data-Driven API Tests
```
@data-driven-role.md

Create a data-driven test framework for API testing that reads test data from JSON files and validates responses.
```

### Example 4: Complete Framework Setup
```
@framework-design-role.md

Set up a complete test automation framework with:
- Selenium WebDriver
- TestNG
- Page Object Model
- Extent Reports
- Maven
- CI/CD with GitHub Actions
```

## Best Practices

When using these roles:

1. **Be specific** about your requirements
2. **Mention your tech stack** (Java, Python, TypeScript, etc.)
3. **Specify the testing tool** (Selenium, Playwright, Cypress)
4. **Include context** about your project structure
5. **Ask for explanations** when you need to understand the reasoning

## Contributing

These roles are part of the QA Prompt Library. To suggest improvements or add new roles:

1. Follow the existing role structure
2. Include comprehensive code examples
3. Cover multiple programming languages where applicable
4. Provide best practices and anti-patterns
5. Include real-world use cases

## Related Resources

- [Test Script Generation Prompts](../automation-qa/test-script-generation/)
- [Framework Design Prompts](../automation-qa/framework-design/)
- [API Automation Prompts](../automation-qa/api-automation/)
- [CI/CD Prompts](../automation-qa/ci-cd/)

---

**Note**: These roles are designed to work with Cursor AI's context-aware features. Reference them using the `@` symbol followed by the filename to activate the specific expertise you need.
