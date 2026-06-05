# SauceDemo Detailed Test Cases

This document contains the step-by-step test cases executed against the SauceDemo web application.

---

### TC_ID: TC_LOGIN_001
* **Description:** Verify successful login with standard user credentials.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `standard_user` in the Username field.
  2. Enter `secret_sauce` in the Password field.
  3. Click the Login button.
* **Expected Result:** User is logged in successfully and redirected to the `/inventory.html` page.
* **Actual Result:** User is logged in successfully and redirected to the `/inventory.html` page.
* **Status:** Pass

---

### TC_ID: TC_LOGIN_002
* **Description:** Verify login failure when entering an invalid username with a valid password.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `standard_customer` in the Username field.
  2. Enter `secret_sauce` in the Password field.
  3. Click the Login button.
* **Expected Result:** User is blocked from logging in, and the error message *"Epic sadface: Username and password do not match any user in this service"* is displayed.
* **Actual Result:** User was blocked from logging in, and the message *"Epic sadface: Username and password do not match any user in this service"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_LOGIN_003
* **Description:** Verify login failure when entering a valid username with an invalid password.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `standard_user` in the Username field.
  2. Enter `secret_source` in the Password field.
  3. Click the Login button.
* **Expected Result:** User is blocked from logging in, and the error message *"Epic sadface: Username and password do not match any user in this service"* is displayed.
* **Actual Result:** User was blocked from logging in, and the message *"Epic sadface: Username and password do not match any user in this service"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_LOGIN_004
* **Description:** Verify login failure when leaving the password field blank.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `standard_user` in the Username field.
  2. Leave the Password field empty.
  3. Click the Login button.
* **Expected Result:** User is blocked from logging in, and the error message *"Epic sadface: Password is required"* is displayed.
* **Actual Result:** User was blocked from logging in, and the message *"Epic sadface: Password is required"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_LOGIN_005
* **Description:** Verify login failure with the locked_out_user account.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `locked_out_user` in the Username field.
  2. Enter `secret_sauce` in the Password field.
  3. Click the Login button.
* **Expected Result:** User is blocked from logging in, and the error message *"Epic sadface: Sorry, this user has been locked out"* is displayed.
* **Actual Result:** User was blocked from logging in, and the message *"Epic sadface: Sorry, this user has been locked out"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_LOGIN_006
* **Description:** Verify that trying to access `/inventory.html` directly in the browser address bar without logging in redirects to the login page and shows the security error.
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter the URL `https://www.saucedemo.com/inventory.html` directly in the browser address bar without logging in.
  2. Click the Enter button.
* **Expected Result:** User is blocked from navigating to the inventory page, redirected back to the login page, and the error message *"Epic sadface: You can only access '/inventory.html' when you are logged in."* is displayed.
* **Actual Result:** User was redirected to the login page and the error message *"Epic sadface: You can only access '/inventory.html' when you are logged in."* was displayed.
* **Status:** Pass

---

### TC_ID: TC_INVENTORY_007
* **Description:** Verify product sorting alphabetically from A to Z.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the product sorting dropdown menu in the top right.
  2. Select the "Name (A to Z)" option.
* **Expected Result:** The products are sorted alphabetically. The first product displayed is "Sauce Labs Backpack" and the last product displayed is "Test.allTheThings() T-Shirt (Red)".
* **Actual Result:** The products were sorted alphabetically. The first product displayed was "Sauce Labs Backpack" and the last product displayed was "Test.allTheThings() T-Shirt (Red)".
* **Status:** Pass

---

### TC_ID: TC_INVENTORY_008
* **Description:** Verify product sorting by price from Low to High.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the product sorting dropdown menu in the top right.
  2. Select the "Price (low to high)" option.
* **Expected Result:** The products are sorted by price in ascending order. The first product displayed is "Sauce Labs Onesie" with a price of "$7.99".
* **Actual Result:** The products were sorted by price in ascending order. The first product displayed was "Sauce Labs Onesie" with a price of "$7.99".
* **Status:** Pass

---

### TC_ID: TC_INVENTORY_009
* **Description:** Verify navigation to the product details page by clicking the product image.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the image of the "Sauce Labs Backpack" product.
* **Expected Result:** The user is redirected to the product details page containing the exact description, image, and price ($29.99) of the "Sauce Labs Backpack".
* **Actual Result:** The user was redirected to the product details page containing the exact description, image, and price ($29.99) of the "Sauce Labs Backpack".
* **Status:** Pass

---

### TC_ID: TC_INVENTORY_010
* **Description:** Verify adding a product to the cart from the details page and checking the cart badge.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the title of the "Sauce Labs Backpack" to open its details page.
  2. Click the "Add to cart" button.
* **Expected Result:** The product is added to the cart, the button text changes to "Remove", and the red numeric cart badge in the top right displays "1".
* **Actual Result:** The product was added to the cart, the button text changed to "Remove", and the red numeric cart badge in the top right displayed "1".
* **Status:** Pass

---

### TC_ID: TC_INVENTORY_011
* **Description:** Verify removing a product from the inventory list and checking if the badge disappears.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click the "Add to cart" button for the "Sauce Labs Backpack" product.
  2. Verify the red numeric cart badge displays "1".
  3. Click the "Remove" button for the same product.
* **Expected Result:** The product is removed from the cart, the button text reverts to "Add to cart", and the red numeric cart badge disappears.
* **Actual Result:** The product was removed from the cart, the button text reverted to "Add to cart", and the red numeric cart badge disappeared.
* **Status:** Pass

---

### TC_ID: TC_CART_012
* **Description:** Verify system behavior when attempting to checkout with an empty cart.
* **Pre-conditions:** User is logged in and is on the SauceDemo cart page with 0 items in the cart.
* **Steps:**
  1. Click the "Checkout" button.
  2. Fill out all fields on the "Your Information" page with valid data.
  3. Click the "Continue" button.
* **Expected Result:** The "Checkout: Overview" page should appear, and both the Item Total and Tax should display $0.00.
* **Actual Result:** The Overview page appeared, and both the Item Total and Tax displayed $0.00.
* **Status:** Pass

---

### TC_ID: TC_CART_013
* **Description:** Verify that the correct product name, price, and quantity are displayed in the Cart.
* **Pre-conditions:** User is logged in and is on the SauceDemo inventory page.
* **Steps:**
  1. Click the "Add to cart" button for the "Sauce Labs Backpack" product.
  2. Click the shopping cart icon to navigate to the Cart page.
  3. Verify the displayed product details.
* **Expected Result:** The Cart displays the correct product name ("Sauce Labs Backpack"), price ("$29.99"), and quantity ("1").
* **Actual Result:** The Cart displayed the correct product name ("Sauce Labs Backpack"), price ("$29.99"), and quantity ("1").
* **Status:** Pass

---

### TC_ID: TC_CART_014
* **Description:** Verify error handling when clicking "Continue" on the checkout page with all fields empty.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. Leave all fields empty on the "Your Information" page.
  3. Click the "Continue" button.
* **Expected Result:** User is blocked from proceeding, and the error message *"Error: First Name is required"* is displayed.
* **Actual Result:** User was blocked from proceeding, and the error message *"Error: First Name is required"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_CART_015
* **Description:** Verify error handling when clicking "Continue" with the First Name field empty.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, leave the First Name field empty.
  3. Enter a valid Last Name (e.g., "Mawa") and Postal Code (e.g., "1234").
  4. Click the "Continue" button.
* **Expected Result:** User is blocked from proceeding, and the error message *"Error: First Name is required"* is displayed.
* **Actual Result:** User was blocked from proceeding, and the error message *"Error: First Name is required"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_CART_016
* **Description:** Verify error handling when clicking "Continue" with the Last Name field empty.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name (e.g., "Mawa").
  3. Leave the Last Name field empty.
  4. Enter a valid Postal Code (e.g., "1234").
  5. Click the "Continue" button.
* **Expected Result:** User is blocked from proceeding, and the error message *"Error: Last Name is required"* is displayed.
* **Actual Result:** User was blocked from proceeding, and the error message *"Error: Last Name is required"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_CART_017
* **Description:** Verify error handling when clicking "Continue" with the Zip/Postal Code field empty.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name (e.g., "Mawa") and Last Name (e.g., "QA").
  3. Leave the Zip/Postal Code field empty.
  4. Click the "Continue" button.
* **Expected Result:** User is blocked from proceeding, and the error message *"Error: Postal Code is required"* is displayed.
* **Actual Result:** User was blocked from proceeding, and the error message *"Error: Postal Code is required"* was displayed.
* **Status:** Pass

---

### TC_ID: TC_Overview_018
* **Description:** Verify that the "Item Total" display matches the actual price of the item added (e.g., $29.99 for the backpack).
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
* **Expected Result:** In the price total section, the "Item Total" text displays exactly: "Item total: $29.99".
* **Actual Result:** In the price total section, the "Item Total" text displays exactly: "Item total: $29.99".
* **Status:** Pass

---

### TC_ID: TC_Overview_019
* **Description:** Verify that a tax value greater than $0.00 is displayed and added to the calculation.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
* **Expected Result:** In the price total section, the tax value is displayed as a value greater than $0.00 (e.g., "Tax: $2.40").
* **Actual Result:** In the price total section, the tax value is displayed as a value greater than $0.00 ("Tax: $2.40").
* **Status:** Pass

---

### TC_ID: TC_Overview_020
* **Description:** Verify that "Total" is mathematically correct (Item Total + Tax = Total).
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
* **Expected Result:** In the price total section, the "Total" display mathematically equals the sum of Item Total and Tax ("Total: $32.39").
* **Actual Result:** In the price total section, the "Total" display mathematically equals the sum of Item Total and Tax ("Total: $32.39").
* **Status:** Pass

---

### TC_ID: TC_Overview_021
* **Description:** Verify that clicking "Cancel" on the Overview page cancels the order and safely redirects you back to the main inventory page.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
  4. Click the "Cancel" button on the Checkout: Overview page.
* **Expected Result:** The order is cancelled, and the user is redirected to the main inventory page (https://www.saucedemo.com/inventory.html).
* **Actual Result:** The order was cancelled, and the user was redirected back to the main inventory page.
* **Status:** Pass

---

### TC_ID: TC_Overview_022
* **Description:** Verify that clicking "Finish" redirects you to the "Checkout: Complete!" page and displays the confirmation header: "Thank you for your order!"
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
  4. Click the "Finish" button.
* **Expected Result:** The order is completed, the user is redirected to the checkout-complete page, and the confirmation header displays exactly: "Thank you for your order!"
* **Actual Result:** The order was completed, the user was redirected, and the confirmation header displayed exactly: "Thank you for your order!".
* **Status:** Pass

---

### TC_ID: TC_Overview_023
* **Description:** Verify that the subheader text "Your order has been dispatched, and will arrive just as fast as the pony can ride!" is displayed on the complete page.
* **Pre-conditions:** User is logged in and has added "Sauce Labs Backpack" to the cart.
* **Steps:**
  1. Navigate to the Cart page and click the "Checkout" button.
  2. On the "Your Information" page, enter a valid First Name ("Mawa"), Last Name ("QA"), and Postal Code ("1234").
  3. Click the "Continue" button.
  4. Click the "Finish" button.
* **Expected Result:** The order is completed, and the subheader text displays exactly: "Your order has been dispatched, and will arrive just as fast as the pony can ride!".
* **Actual Result:** The order was completed, and the subheader text displayed exactly: "Your order has been dispatched, and will arrive just as fast as the pony can ride!".
* **Status:** Pass

---

### TC_ID: TC_SDB_024
* **Description:** Verify logging out from the sidebar removes session data and blocks back navigation.
* **Pre-conditions:** User is logged in as `standard_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click the hamburger menu icon in the top-left corner to expand the sidebar.
  2. Click the "Logout" button.
  3. Try clicking the browser's "Back" arrow button.
* **Expected Result:** The user is logged out, redirected to the login page (https://www.saucedemo.com/), and blocked from accessing any internal page via the browser's back navigation.
* **Actual Result:** The user was logged out, redirected to the login page, and blocked from accessing the inventory page via browser back navigation.
* **Status:** Pass

---

### TC_ID: TC_SDB_025
* **Description:** Verify that clicking "Reset App State" inside the sidebar clears the cart badge completely.
* **Pre-conditions:** User is logged in as `standard_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the title of the "Sauce Labs Backpack" to open its details page.
  2. Click the "Add to cart" button.
  3. Click the hamburger menu icon in the top-left corner to expand the sidebar.
  4. Click the "Reset App State" option.
* **Expected Result:** The red shopping cart numeric badge is cleared and completely disappears from the screen (updated from "1" to no badge displayed).
* **Actual Result:** The red shopping cart numeric badge is cleared and completely disappears from the screen.
* **Status:** Pass

---

### TC_ID: TC_SDB_026
* **Description:** Verify that clicking "Reset App State" reverts active "Remove" buttons back to "Add to cart".
* **Pre-conditions:** User is logged in as `standard_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click the "Add to cart" button for the "Sauce Labs Backpack" product.
  2. Click the hamburger menu icon in the top-left corner to expand the sidebar.
  3. Click the "Reset App State" option in the menu.
  4. Click the "X" (close) button to close the sidebar.
  5. Observe the button state for the "Sauce Labs Backpack" product on the inventory page.
* **Expected Result:** The active button for the "Sauce Labs Backpack" successfully changes from "Remove" back to "Add to cart", and the shopping cart numeric badge is cleared completely.
* **Actual Result:** The shopping cart numeric badge is cleared completely, but the button for the "Sauce Labs Backpack" remains stuck as "Remove" and does not revert to "Add to cart".
* **Status:** Fail

---

### TC_ID: TC_SDB_027
* **Description:** Verify that clicking the "X" button on the sidebar menu collapses/closes the menu correctly.
* **Pre-conditions:** User is logged in as `standard_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click the hamburger menu icon in the top-left corner to expand the sidebar.
  2. Click the "X" (close) button on the sidebar.
* **Expected Result:** The sidebar menu collapses and closes correctly, returning full focus to the main inventory page.
* **Actual Result:** The sidebar menu collapses and closes correctly.
* **Status:** Pass

---

### TC_ID: TC_DET_028
* **Description:** On a product details page, verify that clicking "Back to products" redirects safely to the main catalog page.
* **Pre-conditions:** User is logged in as `standard_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the title of the "Sauce Labs Backpack" to open its details page.
  2. Click on the "Back to products" button.
* **Expected Result:** The user is safely redirected back to the main inventory catalog page (https://www.saucedemo.com/inventory.html).
* **Actual Result:** The user was successfully redirected back to the main inventory catalog page.
* **Status:** Pass

---

### TC_ID: TC_DET_029
* **Description:** Verify that the "Remove" button functions correctly on a product detail page when logged in as the "problem_user".
* **Pre-conditions:** User is logged in as `problem_user` and is on the SauceDemo inventory page.
* **Steps:**
  1. Click on the title of the "Sauce Labs Backpack" to open its details page.
  2. Click the "Add to cart" button.
  3. Click the "Remove" button that appears.
* **Expected Result:** Clicking the "Remove" button successfully removes the product from the cart, reverts the button to "Add to cart", and decrements the cart badge.
* **Actual Result:** Clicking the "Remove" button has no effect; the button remains stuck as "Remove", and the item is not removed from the cart.
* **Status:** Fail

---

### TC_ID: TC_DET_030
* **Description:** Verify system behavior and load times when logging in as the "performance_glitch_user".
* **Pre-conditions:** Browser is open, user is on the SauceDemo login page.
* **Steps:**
  1. Enter `performance_glitch_user` in the Username field.
  2. Enter `secret_sauce` in the Password field.
  3. Click the Login button.
* **Expected Result:** The system processes the request immediately and redirects the user to the main inventory page within 1–2 seconds.
* **Actual Result:** There is a severe delay of approximately 5 seconds before the API response is received and the user is redirected to the main inventory page.
* **Status:** Fail
