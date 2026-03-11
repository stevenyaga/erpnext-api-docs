Withholding Tax
===============

Core Concept
------------ 

When a supplier is subject to withholding tax:

- The supplier is paid less
- The withholding tax amount is recorded as payable to the tax authority

Implementation Steps
--------------------

1. Step 1: Create a Tax Withholding Category. Define:

    - Category Name – e.g., Professional Services WHT
    - Rate – e.g., 5%
    - Account Head – Withholding Tax Payable. The account_type of the account must be set to Tax
    - Company
    - Applicable Thresholds (optional). Just ensure that the value of Single Transaction Threshold is set to 1

2. Step 2: Assign Category to Supplier

    - Edit the Supplier record and set the value of Tax Withholding Category for the supplier. Now every purchase invoice for this supplier automatically applies WHT.

3. When Creating a Purchase Invoice

    - Create a Purchase Invoice as usual. Set the value of *tax_withholding_category* to be the Tax Category you just created.

4. Payment Entry Behavior

    - When you create a Payment Entry, the net outstanding amount is reflected
