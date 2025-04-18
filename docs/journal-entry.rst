Journal Entry
=============

Create a Journal Entry
-------------------------

- Endpoint: |BASE_API_URL|.journal_entry.create
- Method: **POST**
- Payload

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-01-10",
        "title": "My Second JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "transaction_code": "CPO",
        "transaction_currency": "USD",
        "exchange_rate": 130,
        "accounts": [{
                "account": "1110",
                "party_type": null, 
                "party": null,
                "debit_in_transaction_currency": 0,
                "credit_in_transaction_currency": 2000
            },
            {
                "account": "1310",
                "party_type": "Customer", 
                "party": "Nyaga",
                "debit_in_transaction_currency": 2000,
                "credit_in_transaction_currency": 0
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

    - You provide the exchange_rate at the parent level
    - Both legs of the journal entry must be denominated in the same currency

.. warning::

    Because of the complex nature of multicurrency such that we allow postings against an account in different currencies, it means that we can only make multicurrency posting against only accounts that **DO NOT HAVE** currency specified for them. This is because if we were to allow, then we will have to deal with two levels of exchange rate conversion i.e

        - transaction currency -> account currency
        - account currency -> company base currency


- Endpoint: |BASE_API_URL|.journal_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-01-10",
        "title": "My Second JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "transaction_code": "CPO",
        "transaction_currency": "USD",
        "exchange_rate": 130,
        "accounts": [{
                "account": "1110",
                "party_type": null, 
                "party": null,
                "debit_in_transaction_currency": 0,
                "credit_in_transaction_currency": 2000
            },
            {
                "account": "1310",
                "party_type": "Customer", 
                "party": "Nyaga",
                "debit_in_transaction_currency": 2000,
                "credit_in_transaction_currency": 0
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

