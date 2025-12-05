# Sample Test Cases

## Example 1: Login Functionality Test Cases

### TC001: Valid Login
- **Test ID**: TC001
- **Title**: Verify user can login with valid credentials
- **Preconditions**: User account exists
- **Priority**: High
- **Steps**:
  1. Navigate to login page
  2. Enter valid username: "testuser@example.com"
  3. Enter valid password: "Test@123"
  4. Click "Login" button
- **Expected Result**: User is redirected to dashboard, welcome message displays
- **Actual Result**: As expected
- **Status**: Pass

### TC002: Invalid Username
- **Test ID**: TC002
- **Title**: Verify error message for invalid username
- **Preconditions**: None
- **Priority**: High
- **Steps**:
  1. Navigate to login page
  2. Enter invalid username: "invalid@example.com"
  3. Enter valid password: "Test@123"
  4. Click "Login" button
- **Expected Result**: Error message "Invalid credentials" displays
- **Actual Result**: As expected
- **Status**: Pass

### TC003: Empty Password Field
- **Test ID**: TC003
- **Title**: Verify validation for empty password
- **Preconditions**: None
- **Priority**: Medium
- **Steps**:
  1. Navigate to login page
  2. Enter valid username: "testuser@example.com"
  3. Leave password field empty
  4. Click "Login" button
- **Expected Result**: Validation error "Password is required" displays
- **Actual Result**: As expected
- **Status**: Pass

## Example 2: E-commerce Shopping Cart Test Cases

### TC101: Add Product to Cart
- **Test ID**: TC101
- **Title**: Verify user can add product to shopping cart
- **Preconditions**: User is logged in, product is in stock
- **Priority**: Critical
- **Steps**:
  1. Navigate to product page
  2. Select size: "Medium"
  3. Select color: "Blue"
  4. Click "Add to Cart" button
- **Expected Result**: 
  - Success message "Product added to cart" displays
  - Cart icon shows count "1"
  - Product appears in cart with correct details
- **Actual Result**: As expected
- **Status**: Pass

### TC102: Update Cart Quantity
- **Test ID**: TC102
- **Title**: Verify user can update product quantity in cart
- **Preconditions**: Cart has at least one product
- **Priority**: High
- **Steps**:
  1. Navigate to shopping cart
  2. Change quantity from "1" to "3"
  3. Click "Update" button
- **Expected Result**:
  - Quantity updates to "3"
  - Subtotal recalculates correctly
  - Total price updates
- **Actual Result**: As expected
- **Status**: Pass

## Example 3: API Test Cases

### TC201: GET User by ID
- **Test ID**: TC201
- **Title**: Verify GET /users/{id} returns user details
- **Endpoint**: GET /api/v1/users/123
- **Priority**: High
- **Request Headers**:
  - Authorization: Bearer {token}
  - Content-Type: application/json
- **Expected Response**:
  - Status Code: 200
  - Response Body:
    ```json
    {
      "id": 123,
      "name": "John Doe",
      "email": "john@example.com",
      "status": "active"
    }
    ```
- **Actual Result**: As expected
- **Status**: Pass

### TC202: POST Create New User
- **Test ID**: TC202
- **Title**: Verify POST /users creates new user
- **Endpoint**: POST /api/v1/users
- **Priority**: Critical
- **Request Body**:
  ```json
  {
    "name": "Jane Smith",
    "email": "jane@example.com",
    "password": "SecurePass123!"
  }
  ```
- **Expected Response**:
  - Status Code: 201
  - Response Body contains user ID
  - User is created in database
- **Actual Result**: As expected
- **Status**: Pass

## Example 4: Mobile App Test Cases

### TC301: App Installation
- **Test ID**: TC301
- **Title**: Verify app installs successfully
- **Device**: iPhone 12, iOS 15.0
- **Priority**: Critical
- **Steps**:
  1. Download app from App Store
  2. Tap "Install"
  3. Wait for installation to complete
- **Expected Result**:
  - App installs without errors
  - App icon appears on home screen
  - First launch shows onboarding screens
- **Actual Result**: As expected
- **Status**: Pass

### TC302: Offline Mode
- **Test ID**: TC302
- **Title**: Verify app works in offline mode
- **Device**: Samsung Galaxy S21, Android 12
- **Priority**: High
- **Preconditions**: User has previously synced data
- **Steps**:
  1. Enable airplane mode
  2. Open app
  3. Navigate to previously viewed content
- **Expected Result**:
  - Cached content displays
  - "Offline mode" indicator shows
  - User can view saved data
- **Actual Result**: As expected
- **Status**: Pass

## Test Case Template

```
### TC[ID]: [TEST_CASE_TITLE]
- **Test ID**: TC[ID]
- **Title**: [DESCRIPTIVE_TITLE]
- **Preconditions**: [REQUIRED_STATE]
- **Priority**: [CRITICAL/HIGH/MEDIUM/LOW]
- **Steps**:
  1. [STEP_1]
  2. [STEP_2]
  3. [STEP_3]
- **Expected Result**: [WHAT_SHOULD_HAPPEN]
- **Actual Result**: [WHAT_ACTUALLY_HAPPENED]
- **Status**: [PASS/FAIL/BLOCKED]
- **Notes**: [ADDITIONAL_INFORMATION]
```

## Tips for Writing Good Test Cases

1. **Clear Title**: Describe what is being tested
2. **Specific Steps**: Make steps actionable and unambiguous
3. **Measurable Results**: Define clear pass/fail criteria
4. **Proper Priority**: Assign appropriate priority
5. **Traceability**: Link to requirements
6. **Reusability**: Write for reuse across releases
7. **Independence**: Each test case should be independent
