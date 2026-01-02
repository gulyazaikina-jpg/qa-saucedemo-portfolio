# Test Cases — SauceDemo (Swag Labs) — Chrome

**Test data:** standard_user / secret_sauce  
**URL:** https://www.saucedemo.com  
**Browsers:** Chrome 143.0.7499.110 (64 bit)

> Статусы: Not run / Pass / Fail / Blocked  
> Issue: ставить `#номер` (например `#12`), если есть дефект/улучшение  
> Evidence: путь до скрина/видео (например `evidence/screenshots/TC-014_pass.png`)

| ID | Title | Preconditions | Steps | Expected Result | Type | Priority | Status | Issue | Evidence |
|---|---|---|---|---|---|---|---|---|---|
| TC-001 | Login with valid credentials | Login page | 1) Enter `standard_user`<br>2) Enter `secret_sauce`<br>3) Click **Login** | Inventory page opens, products list visible | Positive | High | Pass| - | - |
| TC-002 | Login with invalid password | Login page | 1) Enter `standard_user`<br>2) Enter wrong password<br>3) Click **Login** | Error message shown "Epic sadface: Username and password do not match any user in this service", stay on login page | Negative | High | Pass | - | - |
| TC-003 | Login with empty username | Login page | 1) Leave username empty<br>2) Enter any password<br>3) Click **Login** | Validation/error message shown "Epic sadface: Username is required" | Negative | High | Pass | - | - |
| TC-004 | Login with empty password | Login page | 1) Enter any username<br>2) Leave password empty<br>3) Click **Login** | Validation/error message shown "Epic sadface: Password is required" | Negative | High | Pass | - | - |
| TC-005 | Logout from Inventory | Logged in, Inventory | 1) Open burger menu<br>2) Click **Logout** | Redirect to login page | Positive | High | Pass| - | - |
| TC-006 | Restricted access to Inventory without login | Not logged in | 1) Open inventory URL directly | Redirect to login / access blocked | Negative | High | Pass| - | - |
| TC-007 | Inventory shows product cards | Logged in | 1) Open Inventory page | Product cards contain name, price, image, Add/Remove button | Positive | Medium | Pass | - | - |
| TC-008 | Sort: Name (A to Z) | Logged in, Inventory | 1) Select sort **Name (A to Z)** | Items sorted A→Z | Positive | Medium | Pass | - | - |
| TC-009 | Sort: Name (Z to A) | Logged in, Inventory | 1) Select sort **Name (Z to A)** | Items sorted Z→A | Positive | Medium | Pass | - | - |
| TC-010 | Sort: Price (low to high) | Logged in, Inventory | 1) Select sort **Price (low to high)** | Prices sorted ascending | Positive | Medium | Pass | - | - |
| TC-011 | Sort: Price (high to low) | Logged in, Inventory | 1) Select sort **Price (high to low)** | Prices sorted descending | Positive | Medium | Pass | - | - |
| TC-012 | Open product details from Inventory | Logged in, Inventory | 1) Click product name | Product details open; name/price/description visible | Positive | Medium | Pass | #1 | Attached in issue #N1 |
| TC-013 | Back to products from details | On product details page | 1) Click **Back to products** | Inventory page opens | Positive | Low | Pass | - | - |
| TC-014 | Add item to cart from Inventory | Logged in, Inventory | 1) Click **Add to cart** on any item | Button becomes **Remove**, cart badge = 1 | Positive | High | Pass | - | - |
| TC-015 | Remove item from Inventory | Logged in, on Inventory page, a specific item is already in cart (badge > 0).| 1) Click **Remove** on same item | Item removed, badge decrements, button back to **Add to cart** | Positive | High | Pass| - | - |
| TC-016 | Add item to cart from Product Details | Logged in, Details page | 1) Click **Add to cart** | Button becomes **Remove**, badge increments | Positive | High | Pass | - | - |
| TC-017 | Cart icon opens Cart page | Logged in | 1) Click cart icon | Cart page opens | Positive | High | Pass | - | - |
| TC-018 | Cart shows added items | Logged in, ≥1 item in cart | 1) Open Cart | Added items listed; name/price match selected items | Positive | High | Pass | - | - |
| TC-019 | Remove item from Cart page | Logged in, ≥1 item in cart | 1) Open Cart<br>2) Click **Remove** on an item | Item removed from list, badge updates | Positive | High | Pass | - | - |
| TC-020 | Continue shopping from Cart | Logged in, On Cart page | 1) Click **Continue Shopping** | Inventory page opens | Positive | Medium | Pass | - | - |
| TC-021 | Start checkout from Cart | Logged in, ≥1 item in cart | 1) Open Cart<br>2) Click **Checkout** | Checkout Step One opens | Positive | High | Pass | - | - |
| TC-022 | Checkout validation: all fields empty | Logged in, ≥1 item in cart, Checkout: Your Information (Step One) | 1)First Name, Last Name, Zip/Postal Code are empty<br>2) Click **Continue** | Validation error shown "Error: First Name is required", stay on Step One | Negative | High | Pass | - | - |
| TC-023 | Checkout validation: missing First Name | Logged in, ≥1 item in cart, Checkout: Your Information (Step One) | 1) Fill Last Name + Zip<br>2) Leave First Name empty<br>3) Continue | Error for First Name required | Negative | High | Pass | - | - |
| TC-024 | Checkout validation: missing Last Name | Logged in, ≥1 item in cart, Checkout: Your Information (Step One) | 1) Fill First Name + Zip<br>2) Leave Last Name empty<br>3) Continue | Error for Last Name required | Negative | High | Pass | - | - |
| TC-025 | Checkout happy path: finish order |Logged in; cart empty; on Inventory| 1) 1) Add specific item (e.g., Sauce Labs Backpack)<br>2) Open Cart<br>3) Click Checkout<br>4) Fill First/Last/Zip with valid data<br>5) Click Continue<br>6) Verify Checkout: Overview page opens<br>7) Click Finish |Checkout Complete page shown (e.g., “Checkout: Complete!” and success message, Back Home visible); badge cleared; Cart page shows empty| Positive | High | Pass | - | - |
| TC-026 | Cart state persists after refresh | Logged in, 1 item added | 1) Check badge = 1<br>2) Refresh (F5) on Inventory | Added item state persists, badge not reset | Positive | Medium | Pass | - | - |
| TC-027 | Cart persists after back/forward navigation | Logged in, 1 item added | 1) Go to Cart<br>2) Browser Back<br>3) Browser Forward | Cart content and badge remain correct | Positive | Medium | Pass | - | - |
| TC-028 | Sorting selection persists after product navigation | Logged in, Inventory | 1) Set sort (e.g., Price (low to high))<br>2) Open product details<br>3) Back to products | Sorting remains selected | Positive | Low | Fail | #2 | Attached in Issue #2 |
| TC-029 | Add multiple items: badge count | Logged in, Inventory | 1) Add 3 different items<br>2) Open Cart | Badge = 3, cart has 3 items | Positive | High | Pass | - | - |
| TC-030 | Remove one of multiple: badge updates | Logged in, 3 items in cart | 1) Open Cart<br>2) Remove 1 item | Badge decreases by 1; removed item disappears | Positive | High | Pass | - | - |
| TC-031 | Checkout Step One: Cancel returns to Cart | Logged in; cart has 1 item; Checkout Step One open (/checkout-step-one.html) | 1) Click **Cancel** | User is redirected to **Your Cart** page (/cart.html); previously added item(s) remain in cart; badge value unchanged | Positive | Medium | Pass | - | - |
| TC-032 | Checkout Overview: Cancel returns to Inventory | Overview open | 1) Click **Cancel** | Returns to Inventory; cart state preserved | Positive | Medium | Pass | - | - |
| TC-033 | Checkout validation: spaces only | Checkout Step One | 1) Enter only spaces in First/Last/Zip<br>2) Click **Continue** |Error displayed (e.g., required field error); user stays on Step One; checkout does not proceed to Overview | Negative | High | Fail| #3 | Attached in Issue #3 |
| TC-034 | Checkout robustness: very long inputs | Checkout Step One | 1) Enter 200+ chars in First/Last<br>2) Click **Continue**  | App doesn’t break UI/crash; shows validation or accepts safely | Negative | Medium | Pass | - | - |
| TC-035 | Overview totals consistency | Logged in; Checkout: Overview open (/checkout-step-two.html); cart has ≥2 items| 1) Compare Item total with sum of item prices<br>2) Check Total = Item total + Tax |  Item total matches sum of item prices; Total matches Item total + Tax (as displayed) | Positive | High | Pass | - | - |
