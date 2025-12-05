# Sample Bug Reports

## Bug Report #1: Login Button Not Responding

**Title**: Login button does not respond on mobile Safari

**Environment**:
- Browser: Safari 15.0
- Device: iPhone 12 Pro
- OS: iOS 15.2
- App Version: 2.3.1

**Description**:
When attempting to log in on mobile Safari, the login button does not respond to tap events. The button appears to be clickable (shows hover state) but does not submit the form or trigger any action.

**Steps to Reproduce**:
1. Open Safari on iPhone 12 Pro
2. Navigate to https://example.com/login
3. Enter valid username: "testuser@example.com"
4. Enter valid password: "Test@123"
5. Tap the "Login" button

**Expected Result**:
- Login form submits
- User is authenticated
- User is redirected to dashboard

**Actual Result**:
- Login button does not respond
- No form submission occurs
- User remains on login page

**Severity**: High
**Priority**: P1
**Frequency**: Always (100% reproduction rate)
**Workaround**: Using Chrome on mobile works correctly

**Attachments**:
- Screenshot: login-button-issue.png
- Video: login-tap-not-working.mp4
- Console logs: safari-console.txt

**Additional Information**:
- Issue does not occur on desktop Safari
- Issue does not occur on Chrome mobile
- JavaScript console shows no errors
- Button has proper touch-action CSS property

---

## Bug Report #2: Data Loss on Network Interruption

**Title**: Shopping cart data lost when network connection is interrupted

**Environment**:
- Platform: Web Application
- Browser: Chrome 108.0
- OS: Windows 11
- Network: WiFi

**Description**:
When a user adds items to their shopping cart and the network connection is interrupted, all cart data is lost upon reconnection. This results in a poor user experience and potential lost sales.

**Steps to Reproduce**:
1. Log in to the application
2. Add 3 products to shopping cart
3. Verify cart shows 3 items
4. Disconnect network (disable WiFi)
5. Wait 30 seconds
6. Reconnect network (enable WiFi)
7. Refresh the page

**Expected Result**:
- Cart data persists
- All 3 items remain in cart after reconnection
- User can proceed with checkout

**Actual Result**:
- Cart is empty
- All items are lost
- User must re-add items

**Severity**: Critical
**Priority**: P0
**Frequency**: Always
**Workaround**: None available

**Impact**:
- Affects all users
- Results in abandoned carts
- Negative user experience
- Potential revenue loss

**Suggested Fix**:
Implement local storage or session storage to persist cart data during network interruptions.

---

## Bug Report #3: Performance Degradation with Large Datasets

**Title**: Dashboard page load time exceeds 30 seconds with 10,000+ records

**Environment**:
- Application: Admin Dashboard
- Browser: Firefox 109.0
- OS: macOS Ventura 13.1
- Database: PostgreSQL 14.5

**Description**:
The admin dashboard page experiences severe performance degradation when loading datasets with more than 10,000 records. Page load time exceeds 30 seconds, making the application unusable.

**Steps to Reproduce**:
1. Log in as admin user
2. Navigate to Dashboard > Analytics
3. Select date range: Last 90 days (results in 15,000 records)
4. Click "Load Data" button
5. Observe page load time

**Expected Result**:
- Page loads within 3 seconds (per SLA)
- Data displays in paginated format
- UI remains responsive

**Actual Result**:
- Page takes 32 seconds to load
- Browser becomes unresponsive during load
- Console shows warning: "Long running script"

**Severity**: Major
**Priority**: P1
**Frequency**: Always with large datasets

**Performance Metrics**:
- Records: 15,000
- Load Time: 32 seconds
- Memory Usage: 1.2 GB
- CPU Usage: 95%

**Suggested Optimization**:
- Implement server-side pagination
- Add data virtualization
- Optimize database queries
- Implement caching

---

## Bug Report #4: XSS Vulnerability in Comment Section

**Title**: Cross-Site Scripting (XSS) vulnerability in user comments

**Environment**:
- Application: Blog Platform
- Version: 3.2.0
- Affected Component: Comment Section

**Description**:
The comment section does not properly sanitize user input, allowing malicious JavaScript code to be executed. This is a critical security vulnerability that could compromise user data.

**Steps to Reproduce**:
1. Navigate to any blog post
2. Enter the following in comment field:
   ```html
   <script>alert('XSS')</script>
   ```
3. Submit comment
4. Refresh the page

**Expected Result**:
- Script tags are escaped or removed
- Comment displays as plain text
- No JavaScript execution

**Actual Result**:
- Script executes
- Alert box displays
- Potential for malicious code execution

**Severity**: Critical
**Priority**: P0
**Security Impact**: High
**CVSS Score**: 7.5

**Vulnerability Type**: Cross-Site Scripting (XSS)
**Attack Vector**: User Input
**Affected Users**: All users viewing comments

**Recommended Fix**:
- Implement input sanitization
- Use Content Security Policy (CSP)
- Escape HTML entities
- Validate and sanitize all user input

**Compliance Impact**:
- OWASP Top 10 violation
- Potential GDPR compliance issue

---

## Bug Report Template

```markdown
**Title**: [CONCISE_DESCRIPTIVE_TITLE]

**Environment**:
- Application Version: [VERSION]
- Browser/Device: [DETAILS]
- OS: [OS_VERSION]
- Additional Context: [ANY_RELEVANT_INFO]

**Description**:
[CLEAR_DESCRIPTION_OF_THE_ISSUE]

**Steps to Reproduce**:
1. [STEP_1]
2. [STEP_2]
3. [STEP_3]

**Expected Result**:
[WHAT_SHOULD_HAPPEN]

**Actual Result**:
[WHAT_ACTUALLY_HAPPENS]

**Severity**: [CRITICAL/MAJOR/MINOR/TRIVIAL]
**Priority**: [P0/P1/P2/P3/P4]
**Frequency**: [ALWAYS/SOMETIMES/RARE]
**Workaround**: [IF_AVAILABLE]

**Attachments**:
- [SCREENSHOTS]
- [VIDEOS]
- [LOGS]

**Additional Information**:
[ANY_OTHER_RELEVANT_DETAILS]
```

## Bug Severity Guidelines

- **Critical**: System crash, data loss, security vulnerability
- **Major**: Major functionality broken, no workaround
- **Minor**: Minor functionality issue, workaround available
- **Trivial**: Cosmetic issue, minimal impact

## Bug Priority Guidelines

- **P0**: Fix immediately, blocks release
- **P1**: Fix in current sprint
- **P2**: Fix in next sprint
- **P3**: Fix when time permits
- **P4**: Nice to have, low priority
