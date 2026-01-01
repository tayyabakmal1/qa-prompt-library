# QA Testing Best Practices

## 🎯 Overview

This guide compiles best practices for using the QA Prompt Library effectively and for general QA testing excellence.

---

## 📝 Test Case Writing

### Use Clear, Actionable Language
**Good**:
```
Test: User can log in with valid credentials
Steps:
1. Navigate to login page
2. Enter valid email
3. Enter valid password
4. Click login button
Expected: User is redirected to dashboard
```

**Not Ideal**:
```
Test: Login works
Steps: Try logging in
Expected: It works
```

### Follow Given-When-Then Pattern
```
Given: User is on login page
When: User enters valid credentials and clicks login
Then: User is redirected to dashboard with welcome message
```

### Include All Necessary Details
- Preconditions
- Test data
- Expected results
- Priority/Severity
- Tags for categorization

---

## 🤖 Test Automation

### Page Object Model (POM)
**Always use POM for web automation**:

```java
// Good: Page Object
public class LoginPage {
    private WebDriver driver;
    
    @FindBy(id = "username")
    private WebElement usernameField;
    
    public void login(String username, String password) {
        usernameField.sendKeys(username);
        // ...
    }
}

// Not ideal: Direct locators in tests
@Test
public void testLogin() {
    driver.findElement(By.id("username")).sendKeys("user");
    // ...
}
```

### Use Explicit Waits
**Never use Thread.sleep()**:

```java
// Good: Explicit wait
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
wait.until(ExpectedConditions.elementToBeClickable(loginButton));

// Not ideal: Fixed sleep
Thread.sleep(5000);
```

### Make Tests Independent
Each test should:
- Set up its own data
- Clean up after itself
- Not depend on other tests
- Be able to run in any order

### Use Data-Driven Testing
```java
@DataProvider
public Object[][] loginData() {
    return new Object[][] {
        {"valid@email.com", "ValidPass123", true},
        {"invalid@email.com", "wrong", false},
        {"", "", false}
    };
}

@Test(dataProvider = "loginData")
public void testLogin(String email, String password, boolean shouldSucceed) {
    // Test implementation
}
```

---

## 🔍 Exploratory Testing

### Time-Box Your Sessions
- 60-90 minutes maximum
- Take breaks between sessions
- Document findings immediately

### Use Testing Heuristics
- **SFDPOT**: Structure, Function, Data, Platform, Operations, Time
- **FEW HICCUPS**: Familiarity, Explainability, World, History, etc.
- **Goldilocks**: Too much, too little, just right

### Create Charters
```
Mission: Explore payment processing edge cases
Duration: 90 minutes
Areas: Credit card, PayPal, error handling
Risks: Payment failures, data leakage
```

---

## 🐛 Bug Reporting

### Include Reproduction Steps
```
Steps to Reproduce:
1. Log in as admin user
2. Navigate to Settings > Users
3. Click "Delete" on any user
4. Confirm deletion

Expected: User is deleted, success message shows
Actual: Error 500, user not deleted
```

### Provide Environment Details
- OS and version
- Browser and version
- Application version
- Test environment (staging, QA, etc.)

### Add Evidence
- Screenshots
- Videos
- Logs
- Network traces

### Classify Properly
- **Severity**: How bad is the impact?
- **Priority**: How soon should it be fixed?
- **Type**: Bug, enhancement, question

---

## 📊 Test Strategy

### Follow the Test Pyramid
```
        /\
       /E2E\      ← Few (slow, expensive)
      /------\
     /  API  \    ← More (faster, cheaper)
    /--------\
   /   Unit   \   ← Most (fastest, cheapest)
  /------------\
```

### Risk-Based Testing
Focus on:
- High-impact features
- Frequently used functionality
- Recently changed code
- Complex business logic

### Shift Left
- Test early in development
- Involve QA in planning
- Automate from the start
- Continuous testing in CI/CD

---

## 🔄 CI/CD Integration

### Run Tests in Pipeline
```yaml
# Example: GitHub Actions
- name: Run Tests
  run: npm test
  
- name: Upload Results
  uses: actions/upload-artifact@v2
  with:
    name: test-results
    path: test-results/
```

### Fail Fast
- Run smoke tests first
- Run unit tests before integration
- Stop on critical failures

### Parallel Execution
```java
// TestNG parallel execution
<suite name="Suite" parallel="tests" thread-count="4">
    <test name="Test1">
        <classes>
            <class name="TestClass1"/>
        </classes>
    </test>
</suite>
```

---

## 📈 Metrics and Reporting

### Track Key Metrics
- **Test Coverage**: % of code covered
- **Pass Rate**: % of tests passing
- **Defect Density**: Bugs per feature
- **Test Execution Time**: How long tests take
- **Flaky Test Rate**: % of unstable tests

### Create Meaningful Reports
Include:
- Summary of results
- Failed test details
- Trends over time
- Action items

---

## 🎯 Using AI Tools Effectively

### Provide Context
**Good**:
```
Generate Selenium tests for login feature:
- URL: https://app.example.com/login
- Fields: email (id="email"), password (id="pass")
- Button: css=".btn-login"
- Success: Redirects to /dashboard
- Language: Java
- Framework: TestNG
```

**Not Ideal**:
```
Create login tests
```

### Iterate and Refine
1. Generate initial version
2. Review and test
3. Ask for improvements
4. Refine until satisfactory

### Validate AI Output
- Always review generated code
- Test before using in production
- Verify best practices are followed
- Check for security issues

---

## 🔒 Security Testing

### Test Authentication
- Brute force protection
- Session management
- Password policies
- Multi-factor authentication

### Test Authorization
- Role-based access control
- Horizontal privilege escalation
- Vertical privilege escalation
- API endpoint protection

### Test Input Validation
- SQL injection
- XSS attacks
- Command injection
- Path traversal

---

## ♿ Accessibility Testing

### Use Automated Tools
- axe DevTools
- WAVE
- Lighthouse

### Manual Testing
- Keyboard navigation
- Screen reader testing
- Color contrast
- Focus management

### Follow WCAG Guidelines
- Level A (minimum)
- Level AA (recommended)
- Level AAA (enhanced)

---

## 📱 Mobile Testing

### Test on Real Devices
- Don't rely only on emulators
- Test on popular devices
- Test different OS versions

### Consider Mobile-Specific Scenarios
- Network conditions (3G, 4G, WiFi, offline)
- Battery usage
- Interruptions (calls, notifications)
- Gestures (swipe, pinch, rotate)
- Different screen sizes

---

## 🎓 Continuous Learning

### Stay Updated
- Follow testing blogs
- Join testing communities
- Attend conferences
- Take courses

### Practice Regularly
- Contribute to open source
- Try new tools and frameworks
- Experiment with new techniques

### Share Knowledge
- Write blog posts
- Give presentations
- Mentor junior testers
- Contribute to this library!

---

## 🔗 Related Resources

### From This Library
- [Prompt Writing Guide](prompt-writing-guide.md)
- [Workflows](../workflows/)
- [Templates](../templates/)

### External Resources
- [Ministry of Testing](https://www.ministryoftesting.com/)
- [Test Automation University](https://testautomationu.applitools.com/)
- [ISTQB](https://www.istqb.org/)

---

## ✅ Quick Checklist

### Before Writing Tests
- [ ] Understand requirements
- [ ] Identify test scenarios
- [ ] Prepare test data
- [ ] Set up environment

### While Writing Tests
- [ ] Follow naming conventions
- [ ] Use appropriate design patterns
- [ ] Add proper assertions
- [ ] Include error handling
- [ ] Write maintainable code

### After Writing Tests
- [ ] Run tests locally
- [ ] Review code
- [ ] Add to CI/CD
- [ ] Document if needed
- [ ] Update test plan

### Before Release
- [ ] Run full regression
- [ ] Check test coverage
- [ ] Review failed tests
- [ ] Verify critical paths
- [ ] Sign off on quality

---

**Remember**: Quality is everyone's responsibility. These best practices help ensure we deliver high-quality software!
