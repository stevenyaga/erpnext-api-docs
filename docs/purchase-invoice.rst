
Purchase invoice
================

- This module handles purchase invoice operations which are also referred to as the LPO by the client

Create a Purchase Invoice
-------------------------

- Endpoint: |BASE_API_URL|.purchase_invoice.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "title": "First Purchase Invoice",
        "supplier": "Summit Traders Ltd.",
        "posting_date": "2025-02-01",
        "due_date": "2025-02-27",
        "items": [
            {
                "item": "Tractor",
                "qty": 2,
                "rate": 100
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Create a Multi-currency Purchase Invoice
----------------------------------------

**Notes**:

.. warning:: 

    - To create an Purchase Invoice that has been denominated in a currency that is different from the base currency (TZS), you will need to provide the following additional parameters in the payload:

        - **currency**. This is the ISO code for the transacting currency
  
        - **exchange_rate**. The exchange rate based on the transacting currency. This will be the equivalent of base currency units to 1 unit of the transacting currency, e.g if the currency is USD, the exchange rate may be something like 2598.4401


- Endpoint: |BASE_API_URL|.purchase_invoice.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "title": "First Purchase Invoice",
        "supplier": "Summit Traders Ltd.",
        "posting_date": "2025-02-01",
        "due_date": "2025-02-27",
        "currency": "USD",
        "exchange_rate": 2598.4401,
        "items": [
            {
                "item": "Tractor",
                "qty": 2,
                "rate": 100
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Create a Purchase Invoice specifying the transaction code
---------------------------------------------------------

**Notes**:

.. note:: 

    There are instances where you want to specify the account which will be affected when the Purchase Invoice is posted. If this account is not specified, the system will use the default accounts

- Endpoint: |BASE_API_URL|.purchase_invoice.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "title": "First Purchase Invoice",
        "supplier": "Summit Traders Ltd.",
        "posting_date": "2025-02-01",
        "due_date": "2025-02-27",
        "items": [
            {
                "item": "Fork list",
                "expense_account_number": "5204",
                "qty": 2,
                "rate": 100
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a list of Purchase Invoices
-------------------------------

- Endpoint: |BASE_API_URL|.purchase_invoice.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": ["name", "title", "posting_date", "supplier", "total"],
        "filters": [["posting_date", "<", "2035-02-24"]],
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


Get a single Purchase Invoice
-----------------------------

- Endpoint: |BASE_API_URL|.purchase_invoice.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id_": "ACC-PINV-2025-00010"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Purchase Invoice
-------------------------

- Endpoint: |BASE_API_URL|.purchase_invoice.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id_": "ACC-PINV-2025-00010"
    }

