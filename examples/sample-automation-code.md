# Sample Automation Code

## Selenium Java Example - Login Test

```java
package com.qa.tests;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.Assert;
import org.testng.annotations.*;
import java.time.Duration;

public class LoginTest {
    
    private WebDriver driver;
    private WebDriverWait wait;
    
    @BeforeMethod
    public void setUp() {
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        driver = new ChromeDriver();
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        wait = new WebDriverWait(driver, Duration.ofSeconds(20));
    }
    
    @Test(description = "Verify successful login with valid credentials")
    public void testValidLogin() {
        // Navigate to login page
        driver.get("https://example.com/login");
        
        // Enter credentials
        WebElement usernameField = driver.findElement(By.id("username"));
        usernameField.sendKeys("testuser@example.com");
        
        WebElement passwordField = driver.findElement(By.id("password"));
        passwordField.sendKeys("Test@123");
        
        // Click login button
        WebElement loginButton = driver.findElement(By.xpath("//button[@type='submit']"));
        loginButton.click();
        
        // Wait for dashboard to load
        WebElement dashboard = wait.until(
            ExpectedConditions.visibilityOfElementLocated(By.id("dashboard"))
        );
        
        // Verify successful login
        Assert.assertTrue(dashboard.isDisplayed(), "Dashboard should be visible");
        String welcomeMessage = driver.findElement(By.className("welcome-message")).getText();
        Assert.assertTrue(welcomeMessage.contains("Welcome"), "Welcome message should display");
    }
    
    @Test(description = "Verify error message with invalid credentials")
    public void testInvalidLogin() {
        driver.get("https://example.com/login");
        
        driver.findElement(By.id("username")).sendKeys("invalid@example.com");
        driver.findElement(By.id("password")).sendKeys("wrongpassword");
        driver.findElement(By.xpath("//button[@type='submit']")).click();
        
        WebElement errorMessage = wait.until(
            ExpectedConditions.visibilityOfElementLocated(By.className("error-message"))
        );
        
        Assert.assertEquals(errorMessage.getText(), "Invalid credentials", 
            "Error message should display for invalid login");
    }
    
    @AfterMethod
    public void tearDown() {
        if (driver != null) {
            driver.quit();
        }
    }
}
```

## Playwright TypeScript Example - E-commerce Test

```typescript
import { test, expect } from '@playwright/test';

test.describe('Shopping Cart Tests', () => {
  
  test.beforeEach(async ({ page }) => {
    await page.goto('https://example-shop.com');
    // Login
    await page.click('text=Login');
    await page.fill('#email', 'testuser@example.com');
    await page.fill('#password', 'Test@123');
    await page.click('button:has-text("Sign In")');
    await expect(page.locator('.user-menu')).toBeVisible();
  });

  test('Add product to cart', async ({ page }) => {
    // Search for product
    await page.fill('[placeholder="Search products"]', 'laptop');
    await page.press('[placeholder="Search products"]', 'Enter');
    
    // Select first product
    await page.click('.product-card >> nth=0');
    
    // Add to cart
    await page.click('button:has-text("Add to Cart")');
    
    // Verify success message
    await expect(page.locator('.success-message')).toHaveText('Product added to cart');
    
    // Verify cart count
    const cartCount = await page.locator('.cart-count').textContent();
    expect(cartCount).toBe('1');
  });

  test('Update cart quantity', async ({ page }) => {
    // Navigate to cart
    await page.click('.cart-icon');
    
    // Update quantity
    await page.fill('.quantity-input >> nth=0', '3');
    await page.click('button:has-text("Update")');
    
    // Verify quantity updated
    const quantity = await page.locator('.quantity-input >> nth=0').inputValue();
    expect(quantity).toBe('3');
    
    // Verify total price updated
    const total = await page.locator('.cart-total').textContent();
    expect(total).toContain('$');
  });

  test('Remove item from cart', async ({ page }) => {
    await page.click('.cart-icon');
    
    // Get initial count
    const initialCount = await page.locator('.cart-item').count();
    
    // Remove first item
    await page.click('.remove-item >> nth=0');
    await page.click('button:has-text("Confirm")');
    
    // Verify item removed
    await page.waitForTimeout(500);
    const newCount = await page.locator('.cart-item').count();
    expect(newCount).toBe(initialCount - 1);
  });
});
```

## Cypress JavaScript Example - API Testing

```javascript
describe('User API Tests', () => {
  
  const baseUrl = 'https://api.example.com';
  let authToken;
  
  before(() => {
    // Get authentication token
    cy.request('POST', `${baseUrl}/auth/login`, {
      email: 'testuser@example.com',
      password: 'Test@123'
    }).then((response) => {
      authToken = response.body.token;
    });
  });

  it('GET - Retrieve user list', () => {
    cy.request({
      method: 'GET',
      url: `${baseUrl}/users`,
      headers: {
        'Authorization': `Bearer ${authToken}`
      }
    }).then((response) => {
      expect(response.status).to.eq(200);
      expect(response.body).to.have.property('users');
      expect(response.body.users).to.be.an('array');
      expect(response.body.users.length).to.be.greaterThan(0);
    });
  });

  it('POST - Create new user', () => {
    const newUser = {
      name: 'Jane Doe',
      email: 'jane.doe@example.com',
      role: 'user'
    };

    cy.request({
      method: 'POST',
      url: `${baseUrl}/users`,
      headers: {
        'Authorization': `Bearer ${authToken}`,
        'Content-Type': 'application/json'
      },
      body: newUser
    }).then((response) => {
      expect(response.status).to.eq(201);
      expect(response.body).to.have.property('id');
      expect(response.body.name).to.eq(newUser.name);
      expect(response.body.email).to.eq(newUser.email);
    });
  });

  it('PUT - Update user', () => {
    const userId = 123;
    const updatedData = {
      name: 'Jane Smith',
      role: 'admin'
    };

    cy.request({
      method: 'PUT',
      url: `${baseUrl}/users/${userId}`,
      headers: {
        'Authorization': `Bearer ${authToken}`,
        'Content-Type': 'application/json'
      },
      body: updatedData
    }).then((response) => {
      expect(response.status).to.eq(200);
      expect(response.body.name).to.eq(updatedData.name);
      expect(response.body.role).to.eq(updatedData.role);
    });
  });

  it('DELETE - Remove user', () => {
    const userId = 123;

    cy.request({
      method: 'DELETE',
      url: `${baseUrl}/users/${userId}`,
      headers: {
        'Authorization': `Bearer ${authToken}`
      }
    }).then((response) => {
      expect(response.status).to.eq(204);
    });
  });
});
```

## Python Pytest Example - API Testing

```python
import pytest
import requests

BASE_URL = "https://api.example.com"

@pytest.fixture(scope="module")
def auth_token():
    """Get authentication token"""
    response = requests.post(
        f"{BASE_URL}/auth/login",
        json={
            "email": "testuser@example.com",
            "password": "Test@123"
        }
    )
    assert response.status_code == 200
    return response.json()["token"]

@pytest.fixture
def headers(auth_token):
    """Create headers with auth token"""
    return {
        "Authorization": f"Bearer {auth_token}",
        "Content-Type": "application/json"
    }

class TestUserAPI:
    
    def test_get_users(self, headers):
        """Test retrieving user list"""
        response = requests.get(f"{BASE_URL}/users", headers=headers)
        
        assert response.status_code == 200
        data = response.json()
        assert "users" in data
        assert isinstance(data["users"], list)
        assert len(data["users"]) > 0
    
    def test_create_user(self, headers):
        """Test creating a new user"""
        new_user = {
            "name": "John Doe",
            "email": "john.doe@example.com",
            "role": "user"
        }
        
        response = requests.post(
            f"{BASE_URL}/users",
            json=new_user,
            headers=headers
        )
        
        assert response.status_code == 201
        data = response.json()
        assert "id" in data
        assert data["name"] == new_user["name"]
        assert data["email"] == new_user["email"]
    
    def test_update_user(self, headers):
        """Test updating user information"""
        user_id = 123
        updated_data = {
            "name": "John Smith",
            "role": "admin"
        }
        
        response = requests.put(
            f"{BASE_URL}/users/{user_id}",
            json=updated_data,
            headers=headers
        )
        
        assert response.status_code == 200
        data = response.json()
        assert data["name"] == updated_data["name"]
        assert data["role"] == updated_data["role"]
    
    def test_delete_user(self, headers):
        """Test deleting a user"""
        user_id = 123
        
        response = requests.delete(
            f"{BASE_URL}/users/{user_id}",
            headers=headers
        )
        
        assert response.status_code == 204
```

## REST Assured Java Example

```java
import io.restassured.RestAssured;
import io.restassured.response.Response;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

public class APITest {
    
    private String authToken;
    
    @BeforeClass
    public void setup() {
        RestAssured.baseURI = "https://api.example.com";
        
        // Get auth token
        Response response = given()
            .contentType("application/json")
            .body("{ \"email\": \"testuser@example.com\", \"password\": \"Test@123\" }")
        .when()
            .post("/auth/login")
        .then()
            .statusCode(200)
            .extract().response();
        
        authToken = response.jsonPath().getString("token");
    }
    
    @Test
    public void testGetUsers() {
        given()
            .header("Authorization", "Bearer " + authToken)
        .when()
            .get("/users")
        .then()
            .statusCode(200)
            .body("users", hasSize(greaterThan(0)))
            .body("users[0].name", notNullValue());
    }
    
    @Test
    public void testCreateUser() {
        String requestBody = "{ \"name\": \"Jane Doe\", \"email\": \"jane@example.com\", \"role\": \"user\" }";
        
        given()
            .header("Authorization", "Bearer " + authToken)
            .contentType("application/json")
            .body(requestBody)
        .when()
            .post("/users")
        .then()
            .statusCode(201)
            .body("id", notNullValue())
            .body("name", equalTo("Jane Doe"))
            .body("email", equalTo("jane@example.com"));
    }
}
```

## Tips for Writing Automation Code

1. **Use Page Object Model**: Separate page logic from tests
2. **Add Waits**: Use explicit waits for dynamic elements
3. **Error Handling**: Add try-catch blocks
4. **Logging**: Include logging for debugging
5. **Data-Driven**: Externalize test data
6. **Assertions**: Use meaningful assertion messages
7. **Clean Code**: Follow coding standards
8. **Reusability**: Create utility methods
