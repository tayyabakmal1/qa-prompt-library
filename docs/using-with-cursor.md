# Using QA Prompt Library with Cursor AI

## 🎯 Overview

Cursor AI is an AI-powered code editor that integrates directly into your development workflow. This guide shows how to use the QA Prompt Library's Cursor AI roles for maximum productivity.

---

## 🚀 Getting Started

### 1. Install Cursor
- Download from [cursor.sh](https://cursor.sh)
- Install and open Cursor
- Sign in to activate AI features

### 2. Open Your Test Project
- Open your test automation project in Cursor
- Cursor works with any programming language

### 3. Use Cursor AI Roles
- Navigate to [cursor-ai directory](../cursor-ai/)
- Choose the role that matches your framework
- Copy the role content

---

## 🤖 How to Use Cursor AI Roles

### Method 1: Chat Panel (Recommended)

1. **Open Chat** (Cmd/Ctrl + L)
2. **Paste the Role**: Copy entire role file content
3. **Add Your Request**: Describe what you need
4. **Get Code**: Cursor generates code in context

**Example**:
```
[Paste Selenium Expert Role content]

Now help me create a Page Object for the login page with:
- Username field: id="username"
- Password field: id="password"
- Login button: css=".btn-login"
- Remember me checkbox: name="remember"

Use Java and include proper waits.
```

### Method 2: Inline Generation (Cmd/Ctrl + K)

1. **Write a comment** describing what you need
2. **Press Cmd/Ctrl + K**
3. **Paste role** in the prompt
4. **Get code** generated inline

**Example**:
```java
// Generate a Selenium Page Object for login page
// [Paste Selenium Role]
```

### Method 3: Composer (Cmd/Ctrl + I)

1. **Open Composer** (Cmd/Ctrl + I)
2. **Reference files** you want to modify
3. **Paste role** and describe changes
4. **Review and apply** changes

---

## 🔧 Available Cursor AI Roles

### Web Automation
- [Selenium Expert](../cursor-ai/selenium-role.md) - Selenium WebDriver
- [Playwright Expert](../cursor-ai/playwright-role.md) - Playwright
- [Cypress Expert](../cursor-ai/cypress-role.md) - Cypress

### Mobile Testing
- [Appium Expert](../cursor-ai/appium-role.md) - Mobile automation
- [Mobile Testing Expert](../cursor-ai/mobile-testing-role.md) - Mobile strategies

### API Testing
- [REST Assured Expert](../cursor-ai/rest-assured-role.md) - Java API testing
- [Karate DSL Expert](../cursor-ai/karate-dsl-role.md) - BDD API testing
- [GraphQL Expert](../cursor-ai/graphql-testing-role.md) - GraphQL testing

### Design Patterns
- [POM Expert](../cursor-ai/pom-role.md) - Page Object Model
- [BDD Expert](../cursor-ai/bdd-role.md) - Behavior-Driven Development
- [Data-Driven Expert](../cursor-ai/data-driven-role.md) - Data-driven testing

### Specialized
- [Security Testing Expert](../cursor-ai/security-testing-role.md) - Security testing
- [Performance Testing Expert](../cursor-ai/performance-testing-role.md) - Performance testing
- [Accessibility Expert](../cursor-ai/accessibility-testing-role.md) - Accessibility testing

---

## 💡 Best Practices

### 1. Keep Roles Active in Chat
Start your Cursor session by pasting the relevant role:
```
[Paste Selenium Expert Role]

I'll be working on Selenium tests today. Help me with:
1. Creating page objects
2. Writing test cases
3. Debugging issues
```

### 2. Use @-mentions for Context
Reference specific files:
```
@LoginPage.java 
Using the Selenium Expert role, refactor this page object to use better locators
```

### 3. Combine Roles
Use multiple roles for complex tasks:
```
[Paste Selenium Expert Role]
[Paste POM Expert Role]

Create a complete test framework structure with Page Objects
```

### 4. Iterate on Generated Code
```
First request: Generate basic page object
Review: Check the code
Second request: Add error handling and logging
Review: Check improvements
Third request: Add custom wait methods
```

---

## 🎨 Common Use Cases

### 1. Creating Page Objects

**Setup**:
```
[Paste Selenium Expert Role]
[Paste POM Expert Role]
```

**Request**:
```
Create a Page Object for the dashboard page with:
- Header navigation
- User profile dropdown
- Search functionality
- Data table with filters

Use Java, include waits, and follow best practices.
```

### 2. Writing Test Cases

**Setup**:
```
[Paste Playwright Expert Role]
```

**Request**:
```
Write Playwright tests in TypeScript for:
- User login (happy path)
- Invalid credentials
- Password reset flow

Include proper assertions and error handling.
```

### 3. Debugging Flaky Tests

**Setup**:
```
[Paste Selenium Expert Role]

@FlakyTest.java
```

**Request**:
```
This test is flaky. Help me:
1. Identify potential issues
2. Add proper waits
3. Implement retry logic
4. Make it more stable
```

### 4. Refactoring Tests

**Setup**:
```
[Paste POM Expert Role]

@OldTests.java
```

**Request**:
```
Refactor these tests to use Page Object Model pattern.
Extract common methods and improve maintainability.
```

---

## 🚀 Advanced Techniques

### Multi-File Generation

**Request**:
```
[Paste Framework Design Expert Role]

Create a complete test framework with:
- Base test class
- Page object base class
- Test data manager
- Configuration handler
- Reporting setup

Generate all necessary files.
```

### Code Review

**Request**:
```
[Paste Selenium Expert Role]

@TestSuite.java
Review this code and suggest improvements for:
- Code quality
- Best practices
- Performance
- Maintainability
```

### Test Data Generation

**Request**:
```
[Paste Data-Driven Expert Role]

Generate test data for user registration tests:
- 10 valid users
- 5 invalid email formats
- 5 weak passwords
- Edge cases

Format as JSON.
```

---

## ⚙️ Cursor Settings for Testing

### Recommended Settings

1. **Enable Copilot++**: Better code suggestions
2. **Set Context Length**: Maximum for better understanding
3. **Auto-Import**: Enable for test frameworks
4. **Format on Save**: Keep code clean

### Custom Rules

Create `.cursorrules` file in project root:
```
When writing test code:
- Use Page Object Model pattern
- Include explicit waits, never Thread.sleep()
- Add meaningful assertions
- Follow naming convention: test_FeatureName_Scenario
- Include comments for complex logic
- Use data-driven approach when applicable
```

---

## 📊 Productivity Tips

### 1. Create Snippets
Save common role combinations as snippets in Cursor.

### 2. Use Keyboard Shortcuts
- `Cmd/Ctrl + L`: Open chat
- `Cmd/Ctrl + K`: Inline generation
- `Cmd/Ctrl + I`: Composer
- `Cmd/Ctrl + Shift + L`: Clear chat

### 3. Reference Documentation
```
@docs selenium
[Paste Selenium Expert Role]

How do I handle file uploads in Selenium?
```

### 4. Batch Operations
```
[Paste Selenium Expert Role]

Generate page objects for all pages in @sitemap.md
```

---

## ⚠️ Common Pitfalls

### ❌ Not Providing Enough Context
```
Create a test
```

### ✅ Providing Full Context
```
[Paste Selenium Expert Role]

Create a Selenium test in Java for login functionality:
- URL: https://example.com/login
- Username field: id="user"
- Password field: id="pass"
- Submit: css=".btn-submit"
- Verify: Dashboard page loads

Use Page Object Model and TestNG.
```

### ❌ Ignoring Role Expertise
Not using the appropriate role for your framework.

### ✅ Using Correct Role
Use Playwright Expert for Playwright, Selenium Expert for Selenium, etc.

---

## 🔗 Quick Role Access

### Bookmark These
- [Selenium Expert](../cursor-ai/selenium-role.md)
- [Playwright Expert](../cursor-ai/playwright-role.md)
- [POM Expert](../cursor-ai/pom-role.md)
- [REST Assured Expert](../cursor-ai/rest-assured-role.md)

### Keep Open in Tabs
Keep your most-used roles open in browser tabs for quick copy-paste.

---

## 📚 Additional Resources

- [Cursor Documentation](https://cursor.sh/docs)
- [Cursor AI Roles Directory](../cursor-ai/)
- [Framework Design Role](../cursor-ai/framework-design-role.md)

---

**Pro Tip**: Start each coding session by pasting the relevant expert role into Cursor chat. This sets the context for the entire session and ensures consistent, high-quality code generation!
