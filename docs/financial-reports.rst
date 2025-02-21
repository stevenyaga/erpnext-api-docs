Financial Reports
=================

Trial Balance
-------------

To generate a Trial Balance
+++++++++++++++++++++++++++

- The endpoint expects the following parameters:

    - **fiscal_year**. The fiscal year for which you wish to report
    - **from_date** (optional). Start date by which you wish to filter transactions. The date must fall within the selected fiscal year
    - **from_date** (optional). End date by which you wish to filter transactions. The date must fall within the selected fiscal year
    - **show_zero_values** (optional). If set to true, the Trial Balance will show all the accounts including those with zero balances


- Endpoint: |BASE_API_URL|.financial_report.trial_balance
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "fiscal_year": "2025",
        "from_date": "2025-01-01",
        "to_date": "2025-02-28"
    } 

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 