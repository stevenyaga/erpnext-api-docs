Exchange Rate Revaluation
=========================

The purpose of Exchange Rate Revaluation is to adjust the balance in General Ledger accounts according to any changes in the currency exchange rates. This is useful when you are closing your accounts books and want to update your Company's GL accounts by bringing in the money from other currency accounts. Exchange Rate Revaluation feature is for dealing with the situation when you have accounts with different currencies in one Company's Chart of Accounts.

Exchange rate revaluation is the process of adjusting the value of foreign currency-denominated assets and liabilities on a company's balance sheet to reflect current exchange rates. This ensures that financial statements accurately represent the company's financial position, particularly when dealing with transactions in multiple currencies. 


Get list of Exchange Rate Revaluations
--------------------------------------

- Endpoint: |BASE_API_URL|.exchange_rate_revaluation.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doctype": "Exchange Rate Revaluation",
        "fields": ["name", "posting_date", "total_gain_loss"],
        "filters": [["posting_date", ">=", "1970-01-01"]],
        "start": 0,
        "page_length": 0,
        "order_by": "creation desc"
    }

- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 

- Refer to `Document List API Parameters <general-guidance.html>`_ for guidance on the payload


Get a single Exchange Rate Revaluation
--------------------------------------

- Endpoint: |BASE_API_URL|.exchange_rate_revaluation.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "<DOC_ID>"
    }

 
- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Create Exchange Rate Revaluation
--------------------------------

It is important to note that only foreign denominated accounts with balances are subject to revaluation. 

To get the list of accounts that can be revalued at a specific point (end of month etc), use the below endpoint

- Endpoint: |BASE_API_URL|.exchange_rate_revaluation.get_accounts_to_revalue
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "as_at_date": "2025-06-30"
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }

- The response will be of the from

.. code-block:: json

    {
        "message": {
            "success": true,
            "status": 200,
            "data": [
                {
                    "account": "1201 - KCB - USD - DCL",
                    "party_type": "",
                    "party": "",
                    "account_currency": "USD",
                    "balance_in_base_currency": 256000.0,
                    "balance_in_account_currency": 2000.0,
                    "zero_balance": false,
                    "current_exchange_rate": 128.0,
                    "new_exchange_rate": 0.0,
                    "new_balance_in_base_currency": 0.0,
                    "new_balance_in_account_currency": 2000.0,
                    "gain_loss": -256000.0
                }
            ]
        }
    }


- The list of accounts in the **data** property represent those that can be revalued at the specified **posting_date**. If the list is empty, it means there is no foreign currency denominated account that has a balance to revalue. 

.. note::

    - Use this **get_accounts_to_revalue** to get a list of the accounts to be revalued as you are creating an Exchange Rate Revaluation record. Use it to get the accounts to revalue including the current balance
    - Getting the list of revaluable accounts is important in situations when an institution does not want to revalue all the foreign currency denominated accounts


To create an Exchange Rate Revaluation record, call this endpoint

- Endpoint: |BASE_API_URL|.exchange_rate_revaluation.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "posting_date" : "2025-06-30", 
        "company": "Demo Company Ltd",
        "new_exchange_rate" : 131, 
        "accounts": [{
                    "account": "1201"
                }
            ]
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }


.. warning::

    - Creating an Exchange Rate Revaluation involves 2 steps:
        
        1. Retrieve the list of accounts that can be revalued. The list comes with the balance for each account. Use the **get_accounts_to_revalue** end point
        2. Call the **create** end point with the relevant payload 

    - Exchange Rate Revaluations are made at the end of a period e.g month or financial year. You can automate this process by having a scheduled job


Reverse Exchange Rate Revaluation
---------------------------------

Reversals of Exchange Revaluations are usually done at the beginning of a period. The reversal is for the exchange rate revaluation that was made in the previous month. Refer to `Exchange Rate Gain/Loss <exchange-rate-gain-loss.html>`_ for guidance on reversals

To reverse an Exchange Rate Revaluation, follow the steps below:

- Retrieve the list of Exchange Rate Revaluation and order them by the posting date. Get the most recent revaluation
- Using the id of the most recent revaluation, call the **reverse** end point for journal entry. Refer to `Journal Entry API <journal-entry.html>`_ for guidance on the payload


Delete Exchange Rate Revaluation
--------------------------------

An Exchange Rate Revaluation generates journal entries when it is created. Before you can delete an exchange rate revaluation, ensure you have deleted any journal entries and reversal journal entries linked to the exchange rate revaluation. 

After deleting these journals, you can now call this endpoint

- Endpoint: |BASE_API_URL|.exchange_rate_revaluation.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "<DOC_ID>"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


