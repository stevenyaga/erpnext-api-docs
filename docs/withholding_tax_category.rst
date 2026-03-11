Withholding Tax Category
========================

Get list of Withholding Tax Categories
--------------------------------------

- Endpoint: |BASE_API_URL|.withholding_tax_category.list
- Method: **GET**
- Payload:

.. code-block:: json

   {
        "fields": ["name", "category_name"],
        "filters": [],
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

Create Withholding Tax Category
-------------------------------

- Endpoint: |BASE_API_URL|.withholding_tax_category.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "category_name": "Withholding Tax (5%)",
        "round_off_tax_amount": 0,
        "consider_party_ledger_amount": 0,
        "tax_on_excess_amount": 0,
        "rates": [
            {
                "from_date": "2025-01-01",
                "to_date": "2030-12-31",
                "tax_withholding_rate": 15.0,
                "single_threshold": 1.0,
                "cumulative_threshold": 0.0
            }
        ],
        "accounts": [
            {
                "company": "EQUITY FOR TANZANIA",
                "account": "220200 - Withholding Tax Payable - EFTA"
            }
        ]
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }


Update Withholding Tax Category
-------------------------------

- Endpoint: |BASE_API_URL|.withholding_tax_category.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "id": "Mombasa - DCLD",
        "cost_center_name" : "Mombasa",
        "cost_center_number" : null,
        "disabled" : false,
        "is_group" : false,
        "parent_cost_center" : "Demo Company Ltd (Demo) - DCLD"
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 

Delete Withholding Tax Category
-------------------------------

- Endpoint: |BASE_API_URL|.withholding_tax_category.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "Withholding Tax (15%)"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Withholding Tax Category
-------------------------------------

- Endpoint: |BASE_API_URL|.withholding_tax_category.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "Withholding Tax (15%)"
    }

 
- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

