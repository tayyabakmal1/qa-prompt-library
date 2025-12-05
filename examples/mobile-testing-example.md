# Mobile Testing Example: E-Commerce App

This example demonstrates how to use the mobile testing prompts and roles for testing an e-commerce mobile application.

## App Overview
- **App Name**: ShopEasy Mobile
- **Platforms**: iOS 15+ and Android 11+
- **Type**: Native app (Swift for iOS, Kotlin for Android)
- **Key Features**: Product browsing, search, cart, checkout, user accounts, push notifications

---

## Example 1: Using Mobile Test Scenarios Prompt

### Prompt Used:
```
Generate comprehensive test scenarios for mobile app lifecycle management for ShopEasy e-commerce app including:
- App installation and first launch
- App updates and data migration
- Background/foreground transitions during checkout
- App termination and cart recovery
- Low memory scenarios
- System interruptions (calls, SMS) during payment

Output in Gherkin format for iOS and Android.
```

### Generated Output:

```gherkin
Feature: App Lifecycle - Shopping Cart Persistence

  Scenario: Cart items persist when app is backgrounded during checkout
    Given the user has added 3 items to the shopping cart
    And the user is on the checkout page
    When the user receives a phone call
    And the user answers the call for 2 minutes
    And the user returns to the app
    Then the checkout page should still be displayed
    And all 3 items should remain in the cart
    And the shipping address form should retain entered data

  Scenario: Cart recovery after app termination
    Given the user has added 5 items to the cart
    And the user has entered shipping information
    When the app is terminated by the system due to low memory
    And the user relaunches the app
    Then the app should display a "Resume Checkout" prompt
    When the user taps "Resume Checkout"
    Then all 5 items should be in the cart
    And the shipping information should be pre-filled

  Scenario: First-time app launch experience
    Given the user has just installed the app
    When the user launches the app for the first time
    Then the onboarding carousel should be displayed
    And the app should request notification permission
    When the user completes onboarding
    Then the home screen with featured products should be displayed
    And the user should be prompted to create an account or browse as guest
```

---

## Example 2: Using Appium Role for Automation

### Prompt Used:
```
@appium-role.md

Create a Page Object Model for ShopEasy mobile app with the following screens:
- Home Screen (search bar, category tabs, product grid, cart icon with badge)
- Product Detail Screen (product image, title, price, size selector, add to cart button)
- Shopping Cart Screen (cart items list, quantity controls, remove button, checkout button, total price)

Use Python with Appium for Android. Include a base page with common swipe and wait methods.
```

### Generated Code:

```python
# base_page.py
from appium.webdriver.common.appiumby import AppiumBy
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

class BasePage:
    def __init__(self, driver):
        self.driver = driver
        self.wait = WebDriverWait(driver, 10)
    
    def find_element(self, locator):
        return self.wait.until(EC.presence_of_element_located(locator))
    
    def click(self, locator):
        element = self.wait.until(EC.element_to_be_clickable(locator))
        element.click()
    
    def send_keys(self, locator, text):
        element = self.find_element(locator)
        element.clear()
        element.send_keys(text)
    
    def get_text(self, locator):
        return self.find_element(locator).text
    
    def swipe_up(self):
        size = self.driver.get_window_size()
        start_x = size['width'] // 2
        start_y = size['height'] * 0.8
        end_y = size['height'] * 0.2
        
        self.driver.swipe(start_x, start_y, start_x, end_y, 1000)
    
    def scroll_to_element(self, accessibility_id, max_scrolls=10):
        for _ in range(max_scrolls):
            try:
                element = self.driver.find_element(AppiumBy.ACCESSIBILITY_ID, accessibility_id)
                if element.is_displayed():
                    return element
            except:
                pass
            self.swipe_up()
        raise Exception(f"Element {accessibility_id} not found after {max_scrolls} scrolls")


# home_page.py
from appium.webdriver.common.appiumby import AppiumBy
from base_page import BasePage

class HomePage(BasePage):
    # Locators
    SEARCH_BAR = (AppiumBy.ACCESSIBILITY_ID, "search_bar")
    CATEGORY_TAB = (AppiumBy.ID, "com.shopeasy:id/category_tab_{}")
    PRODUCT_GRID = (AppiumBy.ID, "com.shopeasy:id/product_grid")
    CART_ICON = (AppiumBy.ACCESSIBILITY_ID, "cart_icon")
    CART_BADGE = (AppiumBy.ID, "com.shopeasy:id/cart_badge")
    
    def search_product(self, product_name):
        self.click(self.SEARCH_BAR)
        self.send_keys(self.SEARCH_BAR, product_name)
        self.driver.press_keycode(66)  # Enter key
        return self
    
    def select_category(self, category_name):
        locator = (self.CATEGORY_TAB[0], self.CATEGORY_TAB[1].format(category_name))
        self.click(locator)
        return self
    
    def select_product(self, product_index):
        products = self.driver.find_elements(AppiumBy.ID, "com.shopeasy:id/product_item")
        products[product_index].click()
        from product_detail_page import ProductDetailPage
        return ProductDetailPage(self.driver)
    
    def get_cart_badge_count(self):
        return int(self.get_text(self.CART_BADGE))
    
    def open_cart(self):
        self.click(self.CART_ICON)
        from shopping_cart_page import ShoppingCartPage
        return ShoppingCartPage(self.driver)


# product_detail_page.py
from appium.webdriver.common.appiumby import AppiumBy
from base_page import BasePage

class ProductDetailPage(BasePage):
    # Locators
    PRODUCT_IMAGE = (AppiumBy.ID, "com.shopeasy:id/product_image")
    PRODUCT_TITLE = (AppiumBy.ID, "com.shopeasy:id/product_title")
    PRODUCT_PRICE = (AppiumBy.ID, "com.shopeasy:id/product_price")
    SIZE_SELECTOR = (AppiumBy.ID, "com.shopeasy:id/size_selector")
    ADD_TO_CART_BTN = (AppiumBy.ACCESSIBILITY_ID, "add_to_cart_button")
    SUCCESS_MESSAGE = (AppiumBy.ID, "com.shopeasy:id/success_message")
    
    def get_product_title(self):
        return self.get_text(self.PRODUCT_TITLE)
    
    def get_product_price(self):
        return self.get_text(self.PRODUCT_PRICE)
    
    def select_size(self, size):
        self.click(self.SIZE_SELECTOR)
        size_option = (AppiumBy.XPATH, f"//android.widget.TextView[@text='{size}']")
        self.click(size_option)
        return self
    
    def add_to_cart(self):
        self.click(self.ADD_TO_CART_BTN)
        self.wait.until(EC.visibility_of_element_located(self.SUCCESS_MESSAGE))
        return self
    
    def verify_added_to_cart(self):
        message = self.get_text(self.SUCCESS_MESSAGE)
        return "Added to cart" in message


# shopping_cart_page.py
from appium.webdriver.common.appiumby import AppiumBy
from base_page import BasePage

class ShoppingCartPage(BasePage):
    # Locators
    CART_ITEMS = (AppiumBy.ID, "com.shopeasy:id/cart_item")
    ITEM_TITLE = (AppiumBy.ID, "com.shopeasy:id/item_title")
    ITEM_PRICE = (AppiumBy.ID, "com.shopeasy:id/item_price")
    QUANTITY_PLUS = (AppiumBy.ACCESSIBILITY_ID, "quantity_plus_{}")
    QUANTITY_MINUS = (AppiumBy.ACCESSIBILITY_ID, "quantity_minus_{}")
    REMOVE_BUTTON = (AppiumBy.ACCESSIBILITY_ID, "remove_item_{}")
    CHECKOUT_BUTTON = (AppiumBy.ACCESSIBILITY_ID, "checkout_button")
    TOTAL_PRICE = (AppiumBy.ID, "com.shopeasy:id/total_price")
    
    def get_cart_item_count(self):
        items = self.driver.find_elements(*self.CART_ITEMS)
        return len(items)
    
    def get_total_price(self):
        return self.get_text(self.TOTAL_PRICE)
    
    def increase_quantity(self, item_index):
        locator = (self.QUANTITY_PLUS[0], self.QUANTITY_PLUS[1].format(item_index))
        self.click(locator)
        return self
    
    def decrease_quantity(self, item_index):
        locator = (self.QUANTITY_MINUS[0], self.QUANTITY_MINUS[1].format(item_index))
        self.click(locator)
        return self
    
    def remove_item(self, item_index):
        locator = (self.REMOVE_BUTTON[0], self.REMOVE_BUTTON[1].format(item_index))
        self.click(locator)
        return self
    
    def proceed_to_checkout(self):
        self.click(self.CHECKOUT_BUTTON)
        # Return checkout page object
        return self


# test_shopping_flow.py
import pytest
from appium import webdriver
from appium.options.android import UiAutomator2Options
from home_page import HomePage

class TestShoppingFlow:
    
    @pytest.fixture
    def driver(self):
        options = UiAutomator2Options()
        options.platform_name = 'Android'
        options.device_name = 'Pixel_6'
        options.app = '/path/to/shopeasy.apk'
        options.app_package = 'com.shopeasy'
        options.app_activity = '.MainActivity'
        options.no_reset = False
        
        driver = webdriver.Remote('http://127.0.0.1:4723', options=options)
        yield driver
        driver.quit()
    
    def test_add_product_to_cart(self, driver):
        # Navigate to home page
        home_page = HomePage(driver)
        
        # Search for a product
        home_page.search_product("laptop")
        
        # Select first product
        product_page = home_page.select_product(0)
        
        # Get product details
        product_title = product_page.get_product_title()
        
        # Add to cart
        product_page.add_to_cart()
        
        # Verify success message
        assert product_page.verify_added_to_cart()
        
        # Navigate back to home
        driver.back()
        
        # Verify cart badge shows 1
        assert home_page.get_cart_badge_count() == 1
    
    def test_cart_management(self, driver):
        home_page = HomePage(driver)
        
        # Add multiple products
        for i in range(3):
            product_page = home_page.select_product(i)
            product_page.add_to_cart()
            driver.back()
        
        # Open cart
        cart_page = home_page.open_cart()
        
        # Verify 3 items in cart
        assert cart_page.get_cart_item_count() == 3
        
        # Increase quantity of first item
        cart_page.increase_quantity(0)
        
        # Remove second item
        cart_page.remove_item(1)
        
        # Verify 2 items remain
        assert cart_page.get_cart_item_count() == 2
```

---

## Example 3: Using Mobile Performance Role

### Prompt Used:
```
@mobile-performance-role.md

Create a performance test suite to measure ShopEasy app launch time and product list scroll performance on Android. Include cold start, warm start, and FPS measurement during scrolling.
```

### Generated Test Script:

```python
import time
import pytest
from appium import webdriver
from appium.options.android import UiAutomator2Options

class PerformanceMetrics:
    def __init__(self):
        self.cold_start_times = []
        self.warm_start_times = []
        self.scroll_fps = []
    
    def calculate_stats(self, data):
        return {
            'average': sum(data) / len(data),
            'min': min(data),
            'max': max(data),
            'count': len(data)
        }

class TestAppPerformance:
    
    @pytest.fixture
    def metrics(self):
        return PerformanceMetrics()
    
    def test_cold_start_performance(self, metrics):
        """Measure cold start time (app not in memory)"""
        iterations = 5
        
        for i in range(iterations):
            options = UiAutomator2Options()
            options.platform_name = 'Android'
            options.device_name = 'Pixel_6'
            options.app = '/path/to/shopeasy.apk'
            options.app_package = 'com.shopeasy'
            options.app_activity = '.MainActivity'
            options.no_reset = False
            
            start_time = time.time()
            driver = webdriver.Remote('http://127.0.0.1:4723', options=options)
            
            # Wait for home screen to be fully loaded
            driver.find_element('id', 'com.shopeasy:id/product_grid')
            
            end_time = time.time()
            launch_time = end_time - start_time
            metrics.cold_start_times.append(launch_time)
            
            print(f"Cold start {i+1}: {launch_time:.2f}s")
            driver.quit()
            time.sleep(2)
        
        stats = metrics.calculate_stats(metrics.cold_start_times)
        print(f"\nCold Start Stats: {stats}")
        
        # Assert average cold start is under 3 seconds
        assert stats['average'] < 3.0, f"Cold start too slow: {stats['average']:.2f}s"
    
    def test_scroll_performance(self):
        """Measure scroll performance (FPS)"""
        options = UiAutomator2Options()
        options.platform_name = 'Android'
        options.device_name = 'Pixel_6'
        options.app_package = 'com.shopeasy'
        options.app_activity = '.MainActivity'
        
        driver = webdriver.Remote('http://127.0.0.1:4723', options=options)
        
        # Navigate to product list
        driver.find_element('accessibility id', 'search_bar').click()
        driver.find_element('accessibility id', 'search_bar').send_keys('laptop')
        driver.press_keycode(66)  # Enter
        
        # Perform scroll and measure FPS
        size = driver.get_window_size()
        start_x = size['width'] // 2
        start_y = size['height'] * 0.8
        end_y = size['height'] * 0.2
        
        # Scroll multiple times
        for _ in range(10):
            driver.swipe(start_x, start_y, start_x, end_y, 500)
            time.sleep(0.1)
        
        # In real implementation, you would use Android Profiler or
        # dumpsys gfxinfo to get actual FPS data
        
        driver.quit()
```

---

## Example 4: Mobile Testing Checklist Usage

For ShopEasy app, we customized the mobile testing checklist:

### Critical Test Areas:
- ✅ Product search and filtering
- ✅ Add to cart functionality
- ✅ Cart persistence across app lifecycle
- ✅ Checkout flow with payment integration
- ✅ Push notifications for order updates
- ✅ Biometric authentication for login
- ✅ Offline browsing of previously viewed products
- ✅ Network interruption during checkout
- ✅ Performance on low-end Android devices

### Platform-Specific Tests:
- **iOS**: Apple Pay integration, Face ID authentication
- **Android**: Google Pay integration, Fingerprint authentication

---

## Summary

This example demonstrates how to leverage the mobile testing prompts and roles to:
1. Generate comprehensive test scenarios
2. Create automation scripts with Page Object Model
3. Implement performance testing
4. Use checklists for thorough coverage

The same approach can be applied to any mobile application by customizing the prompts with your app's specific features and requirements.
