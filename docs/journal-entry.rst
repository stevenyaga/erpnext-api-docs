Journal Entry
=============
 
Create a Journal Entry - (Single currency/multi-currency)
---------------------------------------------------------

- Journal entries are created from this single endpoint regardless of whether they are single of multi-currency
- You will be able to include accounts which have different currencies in a Journal Entry. If you have a transaction that was conducted in a currency that is different from the company base currency, you must provide the exchange against the base currency.

.. note:: 

    - You provide the exchange_rate at the parent level and not at an account level
    - Both legs of the journal entry must be denominated in the same transaction currency

.. warning::

    Because of the complex nature of multicurrency such that we allow postings against an account in different currencies, it means that we can only make multicurrency posting against only accounts that **DO NOT HAVE** currency specified for them. This is because if we were to allow, then we will have to deal with two levels of exchange rate conversion i.e

        - transaction currency -> account currency
        - account currency -> company base currency


- Endpoint: |BASE_API_URL|.journal_entry.create
- Method: **POST**
- Payload:

- **Example of a payload for a single currency (base currency) journal entry**

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "company_code": "001",
        "branch_code": "Branch 2",
        "branch_dim_code": "Branch Dim 2",
        "document_type": "Contractual",
        "document_no": "333/45",
        "contract_no": "333/45/2025",
        "customer_no": "CUST-1",
        "customer_name": "XYZ Customer",
        "reversed": false,
        "document_date": "2025-01-02",
        "enquiry_no": "INQ/1/2025",
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-01-10",
        "title": "Single Currency JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "transaction_code": "CPO",
        "transaction_currency": "TZS",
        "exchange_rate": 1,
        "accounts": [{
                "account": "1110",
                "party_type": null, 
                "party": null,
                "debit": 0,
                "credit": 5000000
            },
            {
                "account": "1310",
                "party_type": "Customer", 
                "party": "Nyaga",
                "debit": 5000000,
                "credit": 0
            }
        ]
    }

- **Example of a payload for a foreign currency journal entry**

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "company_code": "001",
        "branch_code": "Branch 2",
        "branch_dim_code": "Branch Dim 2",
        "document_type": "Contractual",
        "document_no": "333/45",
        "contract_no": "333/45/2025",
        "customer_no": "CUST-1",
        "customer_name": "XYZ Customer",
        "reversed": false,
        "document_date": "2025-01-02",
        "enquiry_no": "INQ/1/2025",
        "cheque_no": "",
        "is_opening": "No",
        "posting_date": "2025-01-10",
        "title": "Multi Currency JE",
        "user_remark": "No Other comments",
        "voucher_type": "Journal Entry",
        "transaction_code": "CPO",
        "transaction_currency": "USD",
        "exchange_rate": 130,
        "accounts": [{
                "account": "1110",
                "party_type": null, 
                "party": null,
                "debit": 0,
                "credit": 2000
            },
            {
                "account": "1310",
                "party_type": "Customer", 
                "party": "Nyaga",
                "debit": 2000,
                "credit": 0
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

