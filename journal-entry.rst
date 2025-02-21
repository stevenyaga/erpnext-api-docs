Journal Entry
=============

Create a Journal Entry
-------------------------

- Endpoint: |BASE_API_URL|.journal_entry.create
- Method: **POST**
- Payload

.. code-block:: json

    {
        "cheque_date": null,
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-02-13",
        "title": "My First JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "accounts": [
            {
            "account": "1110 - Creditors - DCL",
            "party_type": "Supplier",
            "party": "ABC Ltd",
            "debit_in_account_currency": 0,
            "credit_in_account_currency": 5000
            },
            {
            "account": "5201 - Administrative Expenses - DCL",
            "party_type": null,
            "party": null,
            "debit_in_account_currency": 5000,
            "credit_in_account_currency": 0
            }
        ]
    }

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Create a Multi Currency Journal Entry
----------------------------------------

- You will be able to include accounts which have different currencies in a Journal Entry. If you have a transaction that was conducted in a currency that is different from the company base currency, you must provide the exchange against the base currency.

.. note:: 

    You only provide the exchange_rate value for only the accounts whose currency is different from the base currency


- Endpoint: |BASE_API_URL|.journal_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-01-10",
        "title": "My Second JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "transaction_code": "CPO",
        "accounts": [
            {
            "account": "5222",
            "party_type": null,
            "party": null,
            "debit_in_account_currency": 0,
            "credit_in_account_currency": 2,
            "exchange_rate": 2598.4401
            },
            {
            "account": "1310",
            "party_type": "Customer",
            "party": "Nyaga",
            "debit_in_account_currency": 5196.8802,
            "credit_in_account_currency": 0
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Get list of Journal Entries
---------------------------

- Endpoint: |BASE_API_URL|.journal_entry.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": [
            "name",
            "title",
            "posting_date",
            "voucher_type",
            "total_amount_currency"
        ],
        "filters": [],
        "start": 0,
        "page_length": 0,
        "order_by": "creation desc"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- Refer to `Document List API Parameters <general-guidance.html>`_ for guidance on the payload


Get a single Journal Entry
-----------------------------

- Endpoint: |BASE_API_URL|.journal_entry.get
- Method: **GET**
- Payload:

.. code-block:: json
    
    {
        "doc_id_": "<DOC_ID>"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Journal Entry
-------------------------

- Endpoint: |BASE_API_URL|.journal_entry.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id_": "<DOC_ID>"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

