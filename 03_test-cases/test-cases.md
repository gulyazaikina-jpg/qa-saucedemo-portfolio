# Test Cases — SauceDemo (Swag Labs) — Chrome

**Test data:** standard_user / secret_sauce  
**URL:** https://www.saucedemo.com  
**Browsers:** Chrome (latest)

> Статусы: Not run / Pass / Fail / Blocked  
> Issue: ставить `#номер` (например `#12`), если есть дефект/улучшение  
> Evidence: путь до скрина/видео (например `evidence/screenshots/TC-014_pass.png`)

| ID | Title | Preconditions | Steps | Expected Result | Type | Priority | Status | Issue | Evidence |
|---|---|---|---|---|---|---|---|---|---|
| TC-001 | Login with valid credentials | Login page | 1) Enter `standard_user`<br>2) Enter `secret_sauce`<br>3) Click **Login** | Inventory page opens, products list visible | Positive | High | Not run | - | - |
| TC-002 | Login with invalid password | Login page | 1) Enter `standard_user`<br>2) Enter wrong password<br>3) Click **Login** | Error message shown, stay on login page | Negative | High | Not run | - | - |
| TC-003 | Login with empty username | Login page | 1) Leave username empty<br>2) Enter any password<br>3) Click **Login** | Validation/error message shown | Negative | High | Not run | - | - |
| TC-004 | Login with empty password | Login page | 1) Enter any username<br>2) Leave password empty<br>3) Click **Login** | Validation/error message shown | Negative | High | Not run | - | - |
| TC-005 | Logout from Inventory | Logged in, Inventory | 1) Open burger menu<br>2) Click **Logout** | Redirect to login page | Positive | High | Not run | - | - |
| TC-006 | Restricted access to Inventory without login | Not logged in | 1) Open inventory URL directly | Redirect to login / access blocked | Negative | High | Not run | - | - |
| TC-007 | Inventory shows product cards | Logged in | 1) Open Inventory page | Product cards contain name, price, image, Add/Remove button | Positive | Medium | Not run | - | - |
| TC-008 | Sort: Name (A to Z) | Logged in, Inventory | 1) Select sort **Name (A to Z)** | Items sorted A→Z | Positive | Medium | Not run | - | - |
| TC-009 | Sort: Name (Z to A) | Logged in, Inventory | 1) Select sort **Name (Z to A)** | Items sorted Z→A | Positive | Medium | Not run | - | - |
| TC-010 | Sort: Price (low to high) | Logged in, Inventory | 1) Select sort **Price (low to high)** | Prices sorted ascending | Positive | Medium | Not run | - | - |
| TC-011 | Sort: Price (high to low) | Logged in, Inventory | 1) Select sort **Price (high to low)** | Prices sorted descending | Positive | Medium | Not run | - | - |
| TC-012 | Open product details from Inventory | Logged in, Inventory | 1) Click product name | Product details open; name/price/description visible | Positive | Medium | Not run | - | - |
| TC-013 | Back to products from details | On product details page | 1) Click **Back to products** | Inventory page opens | Positive | Low | Not run | - | - |
| TC-014 | Add item to cart from Inventory | Logged in, Inventory | 1) Click **Add to cart** on any item | Button becomes **Remove**, cart badge = 1 | Positive | High | Not run | - | - |
| TC-015 | Remove item from Inventory | Item added | 1) Click **Remove** on same item | Item removed, badge decrements, button back to **Add to cart** | Positive | High | Not run | - | - |
| TC-016 | Add item to cart from Product Details | Logged in, Details page | 1) Click **Add to cart** | Button becomes **Remove**, badge increments | Positive | High | Not run | - | - |
| TC-017 | Cart icon opens Cart page | Logged in | 1) Click cart icon | Cart page opens | Positive | High | Not run | - | - |
| TC-018 | Cart shows added items | ≥1 item in cart | 1) Open Cart | Added items listed; name/price match selected items | Positive | High | Not run | - | - |
| TC-019 | Remove item from Cart page | ≥1 item in cart | 1) Open Cart<br>2) Click **Remove** on an item | Item removed from list, badge updates | Positive | High | Not run | - | - |
| TC-020 | Continue shopping from Cart | On Cart page | 1) Click **Continue Shopping** | Inventory page opens | Positive | Medium | Not run | - | - |
| TC-021 | Start checkout from Cart | ≥1 item in cart | 1) Open Cart<br>2) Click **Checkout** | Checkout Step One opens | Positive | High | Not run | - | - |
| TC-022 | Checkout validation: all fields empty | Checkout Step One | 1) Leave all empty<br>2) Click **Continue** | Validation error shown, stay on Step One | Negative | High | Not run | - | - |
| TC-023 | Checkout validation: missing First Name | Checkout Step One | 1) Fill Last Name + Zip<br>2) Leave First Name empty<br>3) Continue | Error for First Name required | Negative | High | Not run | - | - |
| TC-024 | Checkout validation: missing Last Name | Checkout Step One | 1) Fill First Name + Zip<br>2) Leave Last Name empty<br>3) Continue | Error for Last Name required | Negative | High | Not run | - | - |
| TC-025 | Checkout happy path: finish order | ≥1 item in cart | 1) Checkout<br>2) Fill First/Last/Zip<br>3) Continue<br>4) Finish | Complete page shown; cart becomes empty (badge cleared) | Positive | High | Not run | - | - |
| TC-026 | Cart state persists after refresh | Logged in, 1 item added | 1) Check badge = 1<br>2) Refresh (F5) on Inventory | Added item state persists, badge not reset | Positive | Medium | Not run | - | - |
| TC-027 | Cart persists after back/forward navigation | Logged in, 1 item added | 1) Go to Cart<br>2) Browser Back<br>3) Browser Forward | Cart content and badge remain correct | Positive | Medium | Not run | - | - |
| TC-028 | Sorting selection persists after product navigation | Logged in, Inventory | 1) Set sort (e.g., low→high)<br>2) Open product details<br>3) Back to products | Sorting remains selected (если сброс — оформить issue) | Positive | Low | Not run | - | - |
| TC-029 | Add multiple items: badge count | Logged in, Inventory | 1) Add 3 different items<br>2) Open Cart | Badge = 3, cart has 3 items | Positive | High | Not run | - | - |
| TC-030 | Remove one of multiple: badge updates | Logged in, 3 items in cart | 1) Open Cart<br>2) Remove 1 item | Badge decreases by 1; removed item disappears | Positive | High | Not run | - | - |
| TC-031 | Checkout Step One: Cancel returns to Cart | Step One open | 1) Click **Cancel** | Returns to Cart; cart state preserved | Positive | Medium | Not run | - | - |
| TC-032 | Checkout Overview: Cancel returns to Inventory | Overview open | 1) Click **Cancel** | Returns to Inventory; cart state preserved | Positive | Medium | Not run | - | - |
| TC-033 | Checkout validation: spaces only | Checkout Step One | 1) Enter only spaces in First/Last/Zip<br>2) Continue | Validation error shown (если пропускает — issue) | Negative | High | Not run | - | - |
| TC-034 | Checkout robustness: very long inputs | Checkout Step One | 1) Enter 200+ chars in First/Last<br>2) Continue | App doesn’t break UI/crash; shows validation or accepts safely | Negative | Medium | Not run | - | - |
| TC-035 | Overview totals consistency | Overview open with ≥2 items | 1) Compare Item total with sum of item prices<br>2) Check Total = Item total + Tax | Totals consistent with displayed values | Positive | High | Not run | - | - |
