# SauceDemo High-Level Test Scenarios

This document contains the 20 core test scenarios identified during the requirement analysis phase of the SauceDemo application.

### 🔐 User Authentication (Login)
- [ ] **TS_001:** Verify error handling when logging in with an invalid username and valid password.
- [ ] **TS_002:** Verify error handling when logging in with a valid username and invalid password.
- [ ] **TS_003:** Verify successful login when using valid credentials.
- [ ] **TS_004:** Verify error handling when logging in with an unregistered custom username.
- [ ] **TS_005:** Verify error handling when attempting to log in with a valid username and an empty password field.
- [ ] **TS_006:** Verify error handling when attempting to log in with a locked-out user account.

### 🛍️ Inventory & Product Catalog
- [ ] **TS_007:** Verify sorting products alphabetically (Name: A to Z and Name: Z to A).
- [ ] **TS_008:** Verify sorting products by price (Price: Low to High and Price: High to Low).
- [ ] **TS_009:** Verify navigation to the product details page when clicking on the product title or image.

### 🛒 Shopping Cart & Checkout
- [ ] **TS_010:** Verify that clicking 'Remove' on the product list reverts the button to 'Add to cart' and decrements the cart badge.
- [ ] **TS_011:** Verify behavior when attempting to checkout with an empty cart.
- [ ] **TS_012:** Verify that items added to the cart are correctly displayed on the Cart page.
- [ ] **TS_013:** Verify error handling on "Checkout: Your Information" when submitting blank fields.
- [ ] **TS_014:** Verify that removing an item from the Cart page updates the list and the cart badge.
- [ ] **TS_015:** Verify that clicking "Cancel" on the checkout screens redirects back to the correct previous page.
- [ ] **TS_016:** Verify mathematically correct calculation of Item Total, Tax, and Total.
- [ ] **TS_017:** Verify that clicking the 'Finish' button completes the order.

### ⚙️ Session & State Management
- [ ] **TS_018:** Verify successful logout and redirection to the login page.
- [ ] **TS_019:** Verify 'Reset App State' clears the shopping cart and resets elements.
- [ ] **TS_020:** Verify that a logged-out user cannot access internal pages directly via URL browser paths.
