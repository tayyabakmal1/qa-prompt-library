# Using QA Prompt Library with ChatGPT

## 🎯 Overview

This guide shows you how to effectively use the QA Prompt Library with ChatGPT for testing activities.

---

## 🚀 Getting Started

### 1. Access ChatGPT
- Go to [chat.openai.com](https://chat.openai.com)
- Sign in or create an account
- Choose GPT-4 for best results (if available)

### 2. Browse the Prompt Library
- Navigate to the [QA Prompt Library](https://github.com/your-repo/qa-prompt-library)
- Find the prompt you need using [PROMPT_INDEX.md](../PROMPT_INDEX.md)
- Open the relevant prompt file

### 3. Copy and Customize
- Copy the prompt template
- Replace `[PLACEHOLDERS]` with your specific details
- Paste into ChatGPT

---

## 💡 Best Practices

### Use Clear Context
**Good**:
```
I need to create test cases for a user registration feature.

Feature: User Registration
Fields: Email, Password, Confirm Password, Terms Checkbox
Requirements: Email must be valid, password min 8 chars, terms must be accepted

Generate comprehensive test cases covering happy path, validation, and edge cases.
```

**Not Ideal**:
```
Create test cases for registration
```

### Iterate and Refine
1. Start with the prompt template
2. Review ChatGPT's output
3. Ask follow-up questions to refine
4. Request specific formats or additions

**Example Follow-ups**:
- "Can you add more edge cases?"
- "Format this as a table with Test ID, Description, Steps, Expected Result"
- "Add priority levels to each test case"

### Use Conversation History
ChatGPT remembers context within a conversation:
```
You: Generate test cases for login feature
ChatGPT: [Provides test cases]
You: Now generate automation code for these test cases using Selenium
ChatGPT: [Generates code based on previous test cases]
```

---

## 🔧 Common Use Cases

### 1. Test Case Generation

**Prompt from Library**:
Use [Functional Test Cases](../manual-qa/test-case-creation/functional-prompts.md)

**In ChatGPT**:
```
Generate comprehensive functional test cases for:

Feature: Shopping Cart
User Story: As a user, I want to add items to cart so I can purchase them
Acceptance Criteria:
- Users can add items to cart
- Cart shows correct item count
- Cart total updates correctly
- Users can remove items

Include:
- Happy path scenarios
- Edge cases
- Input validation
- Expected outputs

Format: Table with Test ID, Title, Steps, Expected Result, Priority
```

### 2. Test Automation Code

**Prompt from Library**:
Use [Selenium Quick Reference](../automation-qa/web-automation/selenium-quick-reference.md)

**In ChatGPT**:
```
Generate Selenium WebDriver code in Java to:

Action: Login to application
Locators:
- Username: id="username"
- Password: id="password"  
- Login button: css=".btn-login"

Include:
- Page Object Model pattern
- Explicit waits
- Proper assertions
- Exception handling
```

### 3. Bug Report Writing

**Prompt from Library**:
Use [Bug Reporting](../manual-qa/bug-reporting/)

**In ChatGPT**:
```
Create a detailed bug report for:

Issue: Login button doesn't work on mobile
Steps to reproduce:
1. Open app on iPhone 13
2. Enter valid credentials
3. Tap login button
4. Nothing happens

Expected: User should be logged in
Actual: Button doesn't respond

Include: Environment details, severity, suggested priority
```

### 4. API Test Creation

**Prompt from Library**:
Use [API Testing - Beginner](../automation-qa/api-automation/api-testing-beginner.md)

**In ChatGPT**:
```
Help me create Postman tests for:

Endpoint: POST /api/users
Purpose: Create new user
Request Body:
{
  "name": "John Doe",
  "email": "john@example.com"
}

I need:
- Test scripts to validate status code
- Response body validation
- Response time check
- Explain each test clearly
```

---

## 🎨 Advanced Techniques

### Multi-Turn Conversations

**Turn 1**: Generate test cases
```
Generate test cases for password reset feature
```

**Turn 2**: Convert to automation
```
Convert these test cases to Playwright automation code in TypeScript
```

**Turn 3**: Add assertions
```
Add more detailed assertions to verify email is sent
```

### Combining Multiple Prompts

**Step 1**: Use exploratory testing prompt
```
Create an exploratory testing charter for checkout flow
```

**Step 2**: Use test case prompt
```
Based on this charter, generate detailed test cases
```

**Step 3**: Use automation prompt
```
Now create Cypress tests for the critical path scenarios
```

### Custom Instructions

Set up custom instructions in ChatGPT settings:
```
I'm a QA engineer working on web applications. When I ask for test cases:
- Use Given-When-Then format
- Include priority levels
- Consider edge cases
- Format as tables

When I ask for automation code:
- Use Page Object Model
- Include proper waits
- Add comments
- Follow best practices
```

---

## 📊 Prompt Templates for ChatGPT

### Quick Test Case Generation
```
Generate [NUMBER] test cases for [FEATURE] covering [SCENARIOS]
Format as: [FORMAT]
Priority: [PRIORITY_LEVELS]
```

### Quick Automation Code
```
Generate [FRAMEWORK] code in [LANGUAGE] to:
- [ACTION_1]
- [ACTION_2]
Include: [REQUIREMENTS]
```

### Quick Bug Report
```
Create bug report for:
Issue: [DESCRIPTION]
Steps: [STEPS]
Expected: [EXPECTED]
Actual: [ACTUAL]
Environment: [ENV_DETAILS]
```

---

## ⚠️ Common Pitfalls

### ❌ Too Vague
```
Create some tests
```

### ✅ Specific and Clear
```
Create 10 functional test cases for user login covering valid credentials, invalid credentials, empty fields, SQL injection, and session management
```

### ❌ No Context
```
Write Selenium code
```

### ✅ Full Context
```
Write Selenium WebDriver code in Java using Page Object Model to test login functionality with explicit waits and proper assertions
```

---

## 💡 Pro Tips

1. **Start Broad, Then Narrow**: Begin with general prompts, then ask for specifics
2. **Use Examples**: Provide examples of what you want
3. **Specify Format**: Tell ChatGPT exactly how to format output
4. **Iterate**: Don't expect perfection first try - refine the output
5. **Save Good Prompts**: Keep a personal collection of prompts that work well
6. **Use Code Blocks**: Ask ChatGPT to use code blocks for better formatting

---

## 🔗 Recommended Prompts for ChatGPT

### For Beginners
- [API Testing - Beginner](../automation-qa/api-automation/api-testing-beginner.md)
- [Functional Test Cases](../manual-qa/test-case-creation/functional-prompts.md)
- [Bug Reporting](../manual-qa/bug-reporting/)

### For Automation
- [Selenium Quick Reference](../automation-qa/web-automation/selenium-quick-reference.md)
- [Playwright Automation](../automation-qa/playwright-automation/)
- [API Testing](../automation-qa/api-automation/postman-prompts.md)

### For Advanced Users
- [E2E Testing](../automation-qa/e2e-testing/e2e-testing-prompts.md)
- [API Testing - Advanced](../automation-qa/api-automation/api-testing-advanced.md)
- [Visual Testing](../automation-qa/visual-testing/visual-testing-prompts.md)

---

## 📚 Additional Resources

- [ChatGPT Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Prompt Writing Guide](prompt-writing-guide.md)
- [Examples Directory](../examples/)

---

**Remember**: ChatGPT is a tool to enhance your testing, not replace your expertise. Always review and validate AI-generated content!
