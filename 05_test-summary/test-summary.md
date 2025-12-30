# Test Summary Report — SauceDemo 

## Scope
Login → Inventory → Cart → Checkout.

## Execution results
- Planned test cases: 35
- Executed: 35
- Passed: 33
- Failed: 2
- Blocked: 0

## Issues
- Total issues: 3
- Bugs: 2
- Enhancement: 1

## Notes / Findings
- The overall critical flow (login → cart → checkout → finish) works in Chrome on Windows 10.
- Bug: Checkout Step One accepts spaces-only input and allows proceeding. See issue #3 (TC-033).
- Bug: Sorting on Inventory resets after navigating to Product Details and returning back. See issue #2(TC-033).
- Improvement: Some product content looks like code in product name and in description), which may confuse non-technical users. See issue #1.

## Risks / Limitations
- Testing was performed only on Chrome (Windows 10).
- No API checks and no performance testing.

## Next steps
Re-test fixed bugs from issues #2 and #3 (TC-028, TC-033) and run the regression set.
