Financial Reports
=================

Trial Balance
------------- 

- The endpoint expects the following parameters:

    - **fiscal_year**. The fiscal year for which you wish to report
    - **from_date** (optional). Start date by which you wish to filter transactions. The date must fall within the selected fiscal year
    - **from_date** (optional). End date by which you wish to filter transactions. The date must fall within the selected fiscal year
    - **as_tree** (optional). If set to true, the Trial Balance will be return in a tree format
    - **show_zero_values** (optional). If set to true, the Trial Balance will show all the accounts including those with zero balances
   
- Endpoint: |BASE_API_URL|.financial_report.trial_balance
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "fiscal_year":"2025",
        "from_date": "2025-01-01",
        "to_date": "2025-02-28", 
        "as_tree": true,
        "with_period_closing_entry_for_opening": true,
        "with_period_closing_entry_for_current_period": true,
        "include_default_book_entries": true,
        "show_net_values": true,
        "show_zero_values": true
    }

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 


General Ledger
--------------

- The endpoint expects the following parameters:
 
    - **from_date** (optional). Start date by which you wish to filter transactions. The date must fall within the selected fiscal year
    - **from_date** (optional). End date by which you wish to filter transactions. The date must fall within the selected fiscal year 

- The account parameter in the payload accepts a list of account numbers
- Endpoint: |BASE_API_URL|.financial_report.general_ledger
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "from_date": "2025-01-01",
        "to_date": "2025-12-31", 
        "account": [],
        "voucher_no": null,
        "against_voucher_no": null,
        "party_type": null,
        "party": [],
        "group_by": "Group by Voucher (Consolidated)",
        "presentation_currency": null,
        "cost_center": [],
        "project": [],
        "include_dimensions": true,
        "show_opening_entries": false,
        "include_default_book_entries": true,
        "show_cancelled_entries": false,
        "show_net_values_in_party_account": false,
        "add_values_in_transaction_currency": false,
        "show_remarks": false,
        "ignore_err": false,
        "ignore_cr_dr_notes": false
    } 

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 


Profit and Loss Statement
-------------------------

- If you need to show the Profit and Loss Statement by fiscal year, make sure you specify the following parameters in the payload

.. code-block:: json
    
    { 
        "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
    }

- If you need to show the Profit and Loss Statement by date range, make sure you specify the following parameters in the payload

.. code-block:: json

    {
        "filter_based_on": "Date Range",
        "period_from_date": "2025-12-01",
        "period_to_date": "2025-02-28",
    }
     
- Endpoint: |BASE_API_URL|.financial_report.profit_loss_statement
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
        "period_from_date": null,
        "period_to_date": null,
        "periodicity": "Yearly",
        "presentation_currency": null,
        "cost_center": [],
        "project": [],
        "selected_view": "Report View",
        "accumulated_values": true,
        "include_default_book_entries": true
    }

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 


Balance Sheet
-------------

- If you need to show the Balance Sheet by fiscal year, make sure you specify the following parameters in the payload

.. code-block:: json

    { 
        "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
    }

- If you need to show the Balance Sheet by date range, make sure you specify the following parameters in the payload

.. code-block:: json

    {  
        "filter_based_on": "Date Range",
        "period_from_date": "2025-12-01",
        "period_to_date": "2025-02-28",
    }
     
- Endpoint: |BASE_API_URL|.financial_report.balance_sheet
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
        "period_from_date": null,
        "period_to_date": null,
        "periodicity": "Yearly",
        "presentation_currency": null,
        "cost_center": [],
        "project": [],
        "selected_view": "Report View",
        "accumulated_values": true,
        "include_default_book_entries": true
    }

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 


Cash Flow Statement
-------------------

- If you need to show Cash Flow Statement by fiscal year, make sure you specify the following parameters in the payload

.. code-block:: json

    {    
       "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
    }

- If you need to show Cash Flow Statement by date range, make sure you specify the following parameters in the payload

.. code-block:: json

    {
        "filter_based_on": "Date Range",
        "period_from_date": "2025-12-01",
        "period_to_date": "2025-02-28",
    }
     
- Endpoint: |BASE_API_URL|.financial_report.cashflow_statement
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "filter_based_on": "Fiscal Year",
        "from_fiscal_year": "2025",
        "to_fiscal_year": "2025",
        "period_from_date": null,
        "period_to_date": null,
        "periodicity": "Yearly",
        "presentation_currency": null,
        "cost_center": [],
        "project": [],
        "selected_view": "Report View",
        "accumulated_values": true,
        "include_default_book_entries": true
    }

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    } 