SauceDemo – Manual Bug Reports

BUG-001 – Incorrect Product Image Display

Severity: Medium  
Priority: Medium  
Status: Open  
Test Account: `problem_user`

Preconditions

- User is on the SauceDemo login page.
- `problem_user` account is available.

Steps to Reproduce

1. Login using `problem_user`.
2. Enter password `secret_sauce`.
3. Navigate to the Products page.
4. Review the product names and their corresponding images.
5. Compare the displayed image with the selected product.

Expected Result

Each product should display an image corresponding to the correct product.

Actual Result

The product image does not consistently correspond to the expected product.

Impact

Incorrect product imagery can confuse customers and may cause them to select or purchase an unintended product.

xEvidence

Attach screenshot: `BUG-001.png`

---

BUG-002 – Product Removal Does Not Behave Correctly

Severity: High  
Priority: High  
Status: Open  
Test Account: `problem_user`

Preconditions

- User is logged in as `problem_user`.
- At least one product can be added to the cart.

Steps to Reproduce

1. Login using `problem_user`.
2. Add a product to the cart.
3. Open the shopping cart.
4. Click the Remove button for the product.
5. Observe the cart contents and cart counter.

Expected Result

The selected product should be removed from the cart and the cart counter should update accordingly.

Actual Result

The product/cart state does not behave as expected after attempting to remove the item.

Impact

Incorrect cart behavior can result in customers seeing or purchasing products they intended to remove.

Evidence

Attach screenshot: `BUG-002.png`

BUG-003 – Checkout First Name Value Is Not Retained Correctly

Severity: High  
Priority: High  
Status: Open  
Test Account: `problem_user`

Preconditions

- User is logged in as `problem_user`.
- At least one product has been added to the cart.

Steps to Reproduce

1. Open the shopping cart.
2. Click Checkout.
3. Enter a first name in the First Name field.
4. Enter a last name.
5. Enter a postal code.
6. Observe the First Name field before continuing.

Expected Result

The complete value entered into the First Name field should remain unchanged.

Actual Result

The First Name value is not retained/displayed as expected.

Impact

Incorrect customer information can lead to invalid checkout data and may prevent successful completion of the checkout process.

Evidence

Attach screenshot: `BUG-003.png`

---

BUG-004 – Cart Count and Cart Contents Can Become Inconsistent

Severity: High  
Priority: High  
Status: Open  
Test Account: `problem_user`

Preconditions

- User is logged in as `problem_user`.

Steps to Reproduce

1. Add multiple products to the cart.
2. Open the shopping cart.
3. Note the number of products displayed.
4. Remove one of the products.
5. Navigate back to the Products page.
6. Add another product.
7. Open the cart again.
8. Compare the cart counter with the products displayed.

Expected Result

The cart counter should always match the number of products currently present in the cart.

Actual Result

The cart counter and/or cart contents can become inconsistent after adding and removing products.

Impact

An incorrect cart state can cause users to misunderstand which products they have selected.

Evidence

Attach screenshot: `BUG-004.png`

---

BUG-005 – Checkout Flow Behaves Incorrectly for Problem User

Severity: High  
Priority: High  
Status: Open  
Test Account: `problem_user`

Preconditions

- User is logged in as `problem_user`.
- At least one product is present in the cart.

Steps to Reproduce

1. Open the shopping cart.
2. Click Checkout.
3. Enter valid customer information.
4. Click Continue.
5. Review the checkout overview.
6. Observe the displayed customer/product information and navigation behavior.

Expected Result

The checkout information should be retained correctly and the user should be able to proceed normally through the checkout workflow.

Actual Result

Checkout information and/or checkout navigation does not behave as expected for the problem user.

Impact

Checkout problems can prevent users from completing an order and directly affect the core purchasing workflow.

Evidence

Attach screenshot/video: `BUG-005.png`

---

Notes

All reported defects should be reproduced on the assigned SauceDemo environment before final submission.

Screenshots or screen recordings should be attached to each confirmed defect.