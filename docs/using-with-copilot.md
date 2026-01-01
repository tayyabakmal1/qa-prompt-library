# Using QA Prompt Library with GitHub Copilot

## 🎯 Overview

GitHub Copilot is an AI pair programmer that suggests code as you type. This guide shows how to use the QA Prompt Library with Copilot for test automation.

---

## 🚀 Getting Started

### 1. Install GitHub Copilot
- Install [GitHub Copilot extension](https://github.com/features/copilot) for your IDE
- Supported IDEs: VS Code, JetBrains, Neovim, Visual Studio
- Sign in with GitHub account

### 2. Enable Copilot
- Ensure Copilot is active (check status bar)
- Configure settings if needed

### 3. Use Cursor AI Roles as Context
- Open relevant role from [cursor-ai directory](../cursor-ai/)
- Keep role file open in your IDE
- Copilot uses open files as context

---

## 💡 How to Use with Copilot

### Method 1: Comment-Driven Development

Write detailed comments, and Copilot suggests code:

```java
// Create a Selenium Page Object for login page
// Fields: username (id="user"), password (id="pass"), submit button (css=".btn-login")
// Include explicit waits and proper encapsulation
// Follow Page Object Model best practices

public class LoginPage {
    // Copilot will suggest the implementation
}
```

### Method 2: Use Roles as Context Files

1. Open [Selenium Expert Role](../cursor-ai/selenium-role.md) in your IDE
2. Open your test file
3. Write comments describing what you need
4. Copilot suggests code based on role context

**Example**:
```python
# File 1 (open): selenium-role.md
# File 2 (working): test_login.py

# Create a robust login test with explicit waits
# Use Page Object Model pattern
def test_login():
    # Copilot suggests implementation following the role's patterns
```

### Method 3: Copilot Chat

Use Copilot Chat (if available):

```
@workspace Using the Selenium Expert role patterns, create a Page Object for the checkout page
```

---

## 🔧 Best Practices

### 1. Keep Relevant Roles Open
Open 2-3 related files:
- Your test file
- Relevant Cursor AI role
- Example test (if available)

### 2. Write Descriptive Comments
```java
// Good: Detailed comment
// Create a Selenium test for user registration
// Steps: navigate to /register, fill form, submit, verify success message
// Use Page Object Model, include waits, add assertions

// Not ideal: Vague comment
// Create registration test
```

### 3. Use Consistent Naming
Copilot learns from your codebase:
```java
// If you name page objects like: LoginPage, DashboardPage
// Copilot will suggest: RegistrationPage, CheckoutPage
```

### 4. Leverage Copilot Labs
Use Copilot Labs features:
- **Explain**: Understand generated code
- **Translate**: Convert between languages
- **Test**: Generate test cases

---

## 🎨 Common Use Cases

### 1. Generate Page Objects

**Setup**:
- Open [Selenium Expert Role](../cursor-ai/selenium-role.md)
- Open [POM Expert Role](../cursor-ai/pom-role.md)

**In Your Code**:
```java
// Create Page Object for product listing page
// Elements: search box (id="search"), filter dropdown (name="filter"), 
// product cards (css=".product-card"), add to cart buttons
// Include methods: searchProduct(), applyFilter(), addToCart()
// Use explicit waits and return appropriate page objects

public class ProductListingPage extends BasePage {
    // Copilot suggests complete implementation
}
```

### 2. Generate Test Methods

**Setup**:
- Open relevant framework role

**In Your Code**:
```python
# Test: User can add product to cart
# Given: User is on product page
# When: User clicks add to cart
# Then: Cart count increases and success message shows
# Use Page Objects and proper assertions

def test_add_to_cart(self):
    # Copilot suggests test implementation
```

### 3. Generate Test Data

**In Your Code**:
```javascript
// Generate test data for user registration
// Include: valid users, invalid emails, weak passwords, edge cases
// Format as array of objects with: email, password, firstName, lastName, expected result

const testData = [
    // Copilot suggests test data
];
```

### 4. Generate API Tests

**Setup**:
- Open [REST Assured Expert Role](../cursor-ai/rest-assured-role.md)

**In Your Code**:
```java
// Test: GET /api/users/{id} returns user details
// Given: User exists with id=1
// When: GET request to /api/users/1
// Then: Status 200, response contains user data
// Validate: id, name, email fields

@Test
public void testGetUserById() {
    // Copilot suggests REST Assured code
}
```

---

## 🚀 Advanced Techniques

### Multi-File Context

Open multiple related files for better suggestions:
```
Open Files:
1. selenium-role.md (context)
2. BasePage.java (base class)
3. LoginPage.java (example)
4. NewPage.java (working file)

Copilot uses all files to suggest consistent code
```

### Inline Chat for Refactoring

Select code and use inline chat:
```
Select: Old test code
Chat: "Refactor this to use Page Object Model pattern from selenium-role.md"
```

### Generate Complete Test Suites

```java
// Generate complete test suite for user management
// Tests: create user, update user, delete user, list users
// Use TestNG, data providers, and assertions
// Follow patterns from rest-assured-role.md

@Test
public class UserManagementTests {
    // Copilot suggests all test methods
}
```

---

## ⚙️ Copilot Settings

### Recommended Settings (VS Code)

```json
{
  "github.copilot.enable": {
    "*": true,
    "yaml": true,
    "markdown": true
  },
  "github.copilot.advanced": {
    "length": 500,
    "temperature": 0.2
  }
}
```

### Enable for Test Files

Ensure Copilot is enabled for your test file extensions:
- `.java`, `.py`, `.js`, `.ts`, `.rb`, `.cs`

---

## 💡 Pro Tips

1. **Start with Comments**: Write what you want, let Copilot suggest how
2. **Accept and Refine**: Accept suggestion, then refine with more comments
3. **Use Tab**: Tab accepts suggestion, Escape dismisses
4. **Multiple Suggestions**: Alt+] or Alt+[ to cycle through suggestions
5. **Keep Roles Open**: Always have relevant expert role open
6. **Consistent Patterns**: Copilot learns from your existing code

---

## 🔗 Recommended Roles for Copilot

### For Web Automation
- [Selenium Expert](../cursor-ai/selenium-role.md)
- [Playwright Expert](../cursor-ai/playwright-role.md)
- [Cypress Expert](../cursor-ai/cypress-role.md)
- [POM Expert](../cursor-ai/pom-role.md)

### For API Testing
- [REST Assured Expert](../cursor-ai/rest-assured-role.md)
- [Karate DSL Expert](../cursor-ai/karate-dsl-role.md)

### For Mobile
- [Appium Expert](../cursor-ai/appium-role.md)
- [Mobile Testing Expert](../cursor-ai/mobile-testing-role.md)

---

## ⚠️ Limitations

### What Copilot Does Well
✅ Code completion and suggestions
✅ Generating boilerplate code
✅ Following patterns from open files
✅ Completing test methods

### What Copilot Struggles With
❌ Understanding complex business logic
❌ Knowing your specific test data
❌ Understanding your application's unique flows
❌ Making architectural decisions

**Solution**: Combine Copilot with other AI tools:
- Use ChatGPT for planning and strategy
- Use Cursor AI for complex refactoring
- Use Copilot for code completion

---

## 📚 Additional Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Copilot Best Practices](https://github.blog/2023-06-20-how-to-write-better-prompts-for-github-copilot/)
- [Cursor AI Roles](../cursor-ai/)

---

**Remember**: Copilot is a co-pilot, not an autopilot. Always review and test generated code!
