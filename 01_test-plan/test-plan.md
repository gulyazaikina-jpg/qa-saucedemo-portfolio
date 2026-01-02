# Test Plan — SauceDemo (Swag Labs)

## 1. Goal
Verify that a user can:
1) log in,
2) select a product,
3) add it to the cart,
4) complete checkout successfully.

## 2. Scope (What will be tested)
- Login / Logout
- Inventory (product list): products are visible, sorting works
- Product details page
- Cart: add/remove items, cart badge count
- Checkout: customer info → overview → finish
- Basic validations and negative scenarios

## 3. Out of scope (What will NOT be tested)
- Payments and integrations (not available in this demo)
- Performance / load testing
- Database checks (no access)
- Deep security testing (only basic access/session checks)

## 4. Test environment
- URL: https://www.saucedemo.com
- Browser: Chrome 143.0.7499.110 (64 bit)
- OS: Windows 10
- Test date: 2025-12-23

## 5. Test data
- Username: standard_user
- Password: secret_sauce

## 6. Test approach

### 6.1 Smoke test (quick build check)
Goal: confirm the app is testable.
- Login works and Inventory page opens
- Add 1 item to cart (badge updates)
- Cart page opens and item is visible
- Checkout Step One page opens

### 6.2 Critical path (main business flow)
Goal: confirm the end-to-end purchase flow works.
Login → add item → cart → checkout (customer info) → overview → finish  
Plus: verify totals on Overview (Item total + Tax = Total).

### 6.3 Functional tests
- Sorting (A–Z, Z–A, price low–high, high–low)
- Add/remove multiple items, cart badge count
- Checkout validations (empty fields, spaces-only)
- Navigation/state checks (refresh, back/forward)

### 6.4 Negative tests
- Invalid login
- Required fields validation in checkout

## 7. Entry and exit criteria

### Entry criteria
- Application is accessible in Chrome
- Test credentials are available (standard_user / secret_sauce)
- Tester environment is ready (Windows 10, Chrome)

### Exit criteria
- Smoke test executed
- Critical path executed
- At least 80% of planned test cases executed
- All found defects/improvements logged in GitHub Issues with evidence
- Test summary report completed

## 8. Key risks (focus areas)
- Checkout cannot be completed (user cannot finish order)
- Cart state issues (badge/items mismatch, items lost/duplicated)
- Incorrect totals on Overview
- Sorting works incorrectly / inconsistent order
- Session/access issues (protected pages accessible after logout)

## 9. Deliverables (portfolio artifacts)
- Smoke checklist: `02_checklists/smoke-checklist.md`
- Test cases: `03_test-cases/test-cases.md`
- Defects/Improvements: GitHub Issues (with evidence)
- Test summary: `05_test-summary/test-summary.md`
- Evidence folder: `evidence/` (screenshots/videos/har if needed)
- Test summary: `05_test-summary/test-summary.md`
