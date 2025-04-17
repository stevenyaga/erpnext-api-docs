Supplier & Customer Payment
===========================

- This module handles any type of payment made by a customer or a to a supplier.
- For **payments to a supplier**:

    - set the value of **payment_type** to **Pay**
    - set the value of **party_type** to **Supplier**
    - set the value of **party** to the name of the supplier

- For **payments by a customer**:

    - set the value of **payment_type** to **Receive**
    - set the value of **party_type** to **Customer**
    - set the value of **party** to the name of the customer

- If you need to attach a payment against an existing document such as a Purchase Invoice, make sure you provide the details of the document under the **payment_references** field. If you are not attaching to an existing document, do not provide values to the **payment_references**. However, note that by not doing so, you will have to manually reconcile payments yourself
- The id of the existing document must be provided and is the id that exists on the backend.
- If you are unsure which ID it is, you can get the ids using the **.list** endpoint of the respective document type such as {SERVER_URL}/api/method/eclectics.api.purchase_invoice.list and pass the relevant filters. You can then filter through the returned items and pick the one of interest
- The standard type of the document must also be specified e.g Purchase Invoice


Create a Supplier Payment Entry
-------------------------------

- Endpoint: |BASE_API_URL|.payment_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "payment_type": "Pay",
        "mode_of_payment": "Cash",
        "party_type": "Supplier",
        "party": "Summit Traders Ltd.",
        "paid_amount": 300,
        "posting_date": "2025-02-24",
        "transaction_code": "COP",
        "reference_no": null,
        "reference_date": null,
        "payment_references": [
            {
                "document_type": "Purchase Invoice",
                "document_name": "ACC-PINV-2025-00005",
                "allocated_amount": 100
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept

Create a Multi-Currency Supplier Payment Entry
----------------------------------------------

**Notes**:

.. warning:: 

  You will be able to include accounts which have different currencies in a Payment Entry. If you have a Mode of Payment which refers to an account that is different from the company base currency, you must provide the exchange against the base currency.


- Endpoint: |BASE_API_URL|.payment_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "payment_type": "Pay",
        "mode_of_payment": "Wire Transfer USD",
        "party_type": "Supplier",
        "party": "Summit Traders Ltd.",
        "paid_amount": 30,
        "posting_date": "2025-02-24",
        "transaction_code": "COP",
        "exchange_rate": 2598.4401,
        "reference_no": "TRFFFSG245874",
        "reference_date": "2025-01-31",
        "payment_references": [
            {
                "document_type": "Purchase Invoice",
                "document_name": "ACC-PINV-2025-00005",
                "allocated_amount": 10
            }
        ]
    }


- In the example above, the mode of payment *Wire Transfer USD* is linked to an account that has its currency as USD. For this payment, a total of 30 USD was paid and only 10 USD went towards clearing the purchase invoice ACC-PINV-2025-00005. The prevailing exchange of 1USD - TSZ is 2598.4401.

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Create a Customer Payment Entry
-------------------------------

**Details**

- Endpoint: |BASE_API_URL|.payment_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "title": "First Customer Payment",
        "payment_type": "Receive",
        "mode_of_payment": "Cash",
        "party_type": "Customer",
        "party": "West View Software Ltd.",
        "paid_amount": 1000,
        "posting_date": "2025-02-19",
        "reference_no": null,
        "reference_date": null,
        "payment_references": [
            {
                "document_name": "ACC-SINV-2025-00003",
                "document_type": "Sales Invoice",
                "allocated_amount": 1000
            }
        ]
    }


- Headers:

.. code-block:: json
        
    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Create a Multi-Currency Customer Payment Entry
----------------------------------------------

.. warning:: 
  - You will be able to include accounts which have different currencies in a Payment Entry. If you have a Mode of Payment which refers to an account that is different from the company base currency, you must provide the exchange against the base currency.


- Endpoint: |BASE_API_URL|.payment_entry.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "transaction_date": "2025-04-10",
        "created_by": "Nyaga",
        "created_on": "2025-04-16",
        "approved_by": "Steve",
        "approved_on": "2025-04-20",
        "title": "First Multi Currency Payment",
        "payment_type": "Receive",
        "mode_of_payment": "Wire Transfer USD",
        "party_type": "Customer",
        "party": "West View Software Ltd.",
        "paid_amount": 100,
        "posting_date": "2025-02-19",
        "exchange_rate": 2598.4401,
        "reference_no": "TRSG232XX344",
        "reference_date": "2025-01-31",
        "payment_references": [
            {
                "document_name": "ACC-SINV-2025-00003",
                "document_type": "Sales Invoice",
                "allocated_amount": 100
            }
        ]
    }


- In the example above, the mode of payment *Wire Transfer USD* is linked to an account that has its currency as USD. For this payment, a total of 100 USD was received and the full amount went towards clearing the purchase invoice ACC-PINV-2025-00005. The prevailing exchange of 1USD - TSZ is 2598.4401.

- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Get a list of Payment Entries
-----------------------------

- Endpoint: |BASE_API_URL|.payment_entry.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": [
            "name",
            "posting_date",
            "payment_type",
            "party_type",
            "party",
            "paid_amount"
        ],
        "filters": [["posting_date", "<", "2025-02-24"]],
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


Get a single Payment Entry
--------------------------

- Endpoint: |BASE_API_URL|.payment_entry.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id_": "ACC-PAY-2025-00011"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Payment Entry
-------------------------

- Endpoint: |BASE_API_URL|.payment_entry.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id_": "ACC-PAY-2025-00011"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

