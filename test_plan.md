
Swag Labs – Software QA Test Plan

1. Document Information

 Field            : Details                                                     

 Project          : Swag Labs / SauceDemo                                       
 Application URL  : https://www.saucedemo.com/                                  
 Document Type    : Software QA Test Plan                                       
 Testing Approach : Functional, UI, Negative, Edge-Case and Exploratory Testing 
 Prepared By      : Abhishek                                                    
 Application Type : E-commerce Web Application                                  

2. Objective

The objective of this test plan is to evaluate the functionality, usability, reliability and basic compatibility of the Swag Labs e-commerce application.

The testing will focus on the main customer journey, starting from user authentication and continuing through product browsing, cart management and checkout.

The application will also be tested with negative scenarios, edge cases and exploratory testing techniques to identify unexpected behavior and defects.

3. Scope

3.1 In Scope

 User Authentication

* Login using valid credentials
* Login using invalid credentials
* Login using locked-out user
* Empty username and password validation
* Login error messages
* Logout functionality

Product Catalog

* Product listing
* Product names
* Product descriptions
* Product prices
* Product images
* Product sorting
* Product detail page
* Add/remove products

Shopping Cart

* Adding products to the cart
* Removing products from the cart
* Cart item count
* Cart contents
* Cart navigation
* Adding multiple products
* Maintaining correct cart state

Checkout

* Checkout navigation
* Customer information form
* Required-field validation
* Invalid and incomplete input
* Checkout overview
* Product and price verification
* Order completion
* Order confirmation

User Interface

* Buttons and links
* Navigation
* Text visibility
* Product images
* Error messages
* Page layout
* Basic responsive behavior

4. Out of Scope

* Real payment gateway integration
* Real-world shipping integration
* Backend infrastructure testing
* Database-level testing
* Load and stress testing
* Security penetration testing
* Source-code review

5. Types of Testing

5.1 Functional Testing

Functional testing will be performed to verify that application features behave according to their intended functionality.

Examples include:

* Valid users can log in.
* Products can be added to the cart.
* Products can be removed from the cart.
* Users can proceed through checkout.
* Users can complete an order successfully.

5.2 UI Testing

UI testing will verify the presentation and usability of important application elements, including:

* Buttons
* Links
* Product images
* Product information
* Navigation elements
* Error messages
* Page layout
* Cart and checkout screens

5.3 Negative Testing

Negative testing will verify how the application behaves when users provide invalid information or perform unsupported actions.

Examples include:

* Incorrect username
* Incorrect password
* Empty login fields
* Empty checkout fields
* Incomplete checkout information
* Invalid input values
* Attempting to continue without required information

5.4 Edge-Case Testing

Edge-case testing will cover unusual but possible user actions, such as:

* Adding several products to the cart
* Removing all products from the cart
* Repeatedly adding and removing products
* Navigating backward and forward during checkout
* Refreshing pages during a transaction
* Entering unusually long input values
* Attempting checkout without completing required information

5.5 Exploratory Testing

Exploratory testing will be performed in addition to predefined test cases.

The tester will explore the application using different user accounts and different combinations of actions to identify defects that may not be discovered through scripted testing.

Particular attention will be given to:

* Unexpected UI behavior
* Incorrect application state
* Inconsistent product or cart information
* Navigation issues
* Unexpected validation behavior
* Account-specific behavior
* Unusual combinations of user actions

5.6 Cross-Browser Testing

Basic browser compatibility testing will be considered for:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox

Google Chrome will be used as the primary browser for detailed testing.

6. Test Environment

Hardware

* Desktop/Laptop computer
* Keyboard and mouse
* Stable internet connection

Operating System

* Windows 10/11

Browsers

 Browser                            : Priority 
 Google Chrome – Latest Available   : High     
 Microsoft Edge – Latest Available  : Medium   
 Mozilla Firefox – Latest Available : Medium

Automation Environment

* Python 3.x
* Selenium WebDriver
* PyTest
* WebDriver Manager

7. Test Data

The following accounts are provided for testing:

Username                  : Purpose                                

`standard_user`           : Normal application functionality       
`locked_out_user`         : Verify locked-user login behavior      
`problem_user`            : Explore application defects            
`performance_glitch_user` : Test behavior with delayed performance 

Common Password

```text
secret_sauce
```

Checkout Test Data

 Field       : Test Value

First Name  : Abhishek   
Last Name   : Tester     
Postal Code : 560001     

Invalid, empty and boundary-value inputs will also be considered during negative and edge-case testing.

8. Test Cases

 TC-001 – Login With Valid Credentials

Priority: High

Test Type: Functional

Preconditions:

The user is on the Swag Labs login page.

Steps

1. Enter `standard_user` in the Username field.
2. Enter `secret_sauce` in the Password field.
3. Click the Login button.

Expected Result

The user should be successfully authenticated and redirected to the Products page.

TC-002 – Login With Locked-Out User

Priority: High

Test Type: Negative / Functional

Preconditions :

The user is on the login page.

Steps

1. Enter `locked_out_user` in the Username field.
2. Enter `secret_sauce` in the Password field.
3. Click the Login button.

Expected Result

The login attempt should be rejected and an appropriate error message should be displayed.

The user should not be allowed to access the Products page.

TC-003 – Add Product to Cart

Priority: High

Test Type: Functional

Preconditions

The user is successfully logged in using `standard_user`.

Steps

1. Open the Products page.
2. Select an available product.
3. Click Add to cart.
4. Open the shopping cart.

Expected Result

The selected product should appear in the shopping cart.

The cart indicator should display the appropriate number of items.

TC-004 – Remove Product From Cart

Priority: High

Test Type: Functional

Preconditions

The user is logged in and has at least one product in the cart.

Steps

1. Open the shopping cart.
2. Identify the added product.
3. Click Remove.
4. Observe the cart.

Expected Result

The selected product should be removed from the cart.

The cart contents and item count should be updated appropriately.

TC-005 – Complete Checkout

Priority: Critical

Test Type: Functional / End-to-End

Preconditions

The user is logged in and has at least one product in the cart.

Steps

1. Open the shopping cart.
2. Click Checkout.
3. Enter a valid first name.
4. Enter a valid last name.
5. Enter a valid postal code.
6. Click Continue.
7. Review the checkout summary.
8. Click Finish.

Expected Result

The checkout process should complete successfully.

The application should display an order confirmation.

TC-006 – Checkout With Empty Required Fields

Priority: High

Test Type: Negative

Preconditions

The user is logged in and has a product in the cart.

Steps

1. Open the shopping cart.
2. Click Checkout.
3. Leave the required customer information fields empty.
4. Click Continue.

Expected Result

The application should prevent the user from proceeding and display an appropriate validation message.

TC-007 – Product Sorting

Priority: Medium

Test Type: Functional / UI

Preconditions

The user is logged in and is on the Products page.

Steps

1. Open the product sorting dropdown.
2. Select one of the available sorting options.
3. Observe the product list.
4. Repeat the test with the other available sorting options.

Expected Result

Products should be displayed according to the selected sorting option.

The displayed order should be consistent with the selected sorting criteria.

TC-008 – Multiple Products in Cart

Priority: Medium

Test Type: Functional / Edge Case

Preconditions

The user is logged in.

Steps

1. Add multiple different products to the cart.
2. Open the cart.
3. Verify all selected products.
4. Remove one product.
5. Verify the remaining products.

Expected Result

All selected products should be displayed correctly.

Removing one product should not affect the remaining products.

The cart item count should be updated correctly.

9. Entry Criteria

Testing can begin when:

* The application is accessible.
* The login page is available.
* Test credentials are available.
* The required testing environment is ready.
* The browser can access the application.
* The application is available for functional testing.

10. Exit Criteria

Testing can be considered complete when:

* All planned high-priority test cases have been executed.
* Authentication scenarios have been tested.
* Product functionality has been tested.
* Shopping cart functionality has been tested.
* Checkout functionality has been tested.
* Negative and edge-case scenarios have been explored.
* Identified defects have been documented.
* Required automation tests have been completed.
* Test results have been reviewed.

11. Risk Assessment

 Risk                                    : Probability : Impact   : Risk Level :  Mitigation                                              

Login functionality fails               : Medium      : High     : High       : Test valid, invalid and locked-user accounts            
Product information is incorrect        : Medium      : Medium   : Medium     : Verify product names, prices, descriptions and images   
Cart state becomes inconsistent         : High        : High     : High       : Test add, remove and multiple-product scenarios         
Checkout validation fails               : Medium      : High     : High       : Test valid and invalid customer information            
Order completion fails                  : Medium      : Critical : High       : Perform complete end-to-end checkout testing            
UI elements behave inconsistently       : Medium      : Medium   : Medium     : Perform UI and cross-browser testing                   
Application responds slowly             : Medium      : Medium   : Medium     : Test the performance-glitch account                     
Browser compatibility issue             : Low/Medium  : Medium   : Medium     : Test Chrome, Edge and Firefox                           
Unexpected behavior with `problem_user` : High        : High     : High       : Perform exploratory testing using the dedicated account

12. Priority Classification

Critical

A defect that prevents completion of a major business workflow or makes the core application unusable.

Example:
The user cannot complete the checkout process.

High

A defect affecting an important application function or a significant part of the user journey.

Examples:

* User cannot log in.
* Product cannot be added to the cart.
* Checkout cannot proceed.
* Cart contents are incorrect.

Medium

A defect that affects functionality but does not completely prevent the user from completing the main workflow.

Examples:

* Incorrect sorting behavior.
* Minor cart information inconsistency.
* Non-critical navigation issue.

Low

A defect with limited functional or business impact, generally related to presentation or minor usability issues.

Examples:
* Minor alignment issue.
* Minor spacing problem.
* Cosmetic UI inconsistency.

13. Testing Approach

The testing approach will combine predefined functional test cases with exploratory testing.

The testing process will follow these stages:

1. Verify authentication using the supplied user accounts.
2. Explore the product catalog.
3. Verify product names, descriptions, prices and images.
4. Test adding and removing products.
5. Test multiple-product cart scenarios.
6. Verify checkout navigation and validation.
7. Complete an end-to-end purchase flow.
8. Perform negative testing.
9. Perform edge-case testing.
10. Perform exploratory testing using different user accounts.
11. Document reproducible defects.
12. Automate important and repeatable user workflows.

The `problem_user` account will receive additional exploratory attention because the assignment identifies it as an account containing intentional defects.


14. Defect Reporting Approach

Every identified defect will be documented with sufficient information for another tester or developer to reproduce it.

Each bug report will contain:

* Bug ID
* Bug title
* Environment
* User/account used
* Preconditions
* Steps to reproduce
* Expected result
* Actual result
* Severity
* Priority
* User/business impact
* Screenshot or video evidence where applicable

Only reproducible issues observed during testing will be recorded as confirmed defects

15. Automation Scope

The following critical flows will be automated using Selenium WebDriver:

Automated Flow 1 – Valid Login

Verify that `standard_user` can successfully authenticate and access the Products page.

Automated Flow 2 – Cart and Checkout

Verify that a user can:

1. Log in.
2. Select a product.
3. Add the product to the cart.
4. Open the cart.
5. Proceed to checkout.
6. Enter customer information.
7. Complete the order.
8. Verify the confirmation.

Automated Flow 3 – Locked User

Verify that `locked_out_user` cannot successfully log in and that the expected error message is displayed.

16. Deliverables

The QA assignment will include:

* Test Plan
* Detailed Test Cases
* Bug Reports
* Selenium Automation Tests
* `README.md`
* Required configuration/dependency files
* Loom Video 1 – Test Plan and Automation Overview
* Loom Video 2 – Manual Bug Discovery Demonstration

17. Conclusion

This test plan provides a structured approach for evaluating the major functionality of the Swag Labs e-commerce application.

The primary focus will be on authentication, product browsing, shopping cart operations and checkout because these workflows represent the main customer journey.

Functional testing will be combined with negative, edge-case, UI, cross-browser and exploratory testing to provide broader coverage.

Critical and high-priority issues will be investigated first because defects in these areas can directly affect a user's ability to browse products, manage their cart or complete an order.

