Purchase Taxes Template
=======================

By setting up Purchase Taxes and Charges Templates, you streamline the process of applying taxes to purchase transactions. This ensures accuracy in tax calculations, facilitates compliance with tax regulations, and provides transparency in your financial records.

The templates created here can be used in Purchase Invoices for internal records. There is already a default template that has been created. Check it before you can create a new one.

- Tax Type: Choose the appropriate tax type applicable i.e on actual or on net total 

    - Actual: You can directly enter the amount for the expense.
    - On Net Total: On the net total of all the items.
- Select an account head which has pre set tax rates or create your own
- Selecting default will apply this template by default for new Purchase transactions.
- Add or Deduct: Whether you want to add or deduct the tax from the item.
- Is this Tax included in Basic Rate?: If checked, the tax amount will be considered as already included in the Print Rate / Print Amount.
- Account Head: The Account ledger under which this tax will be booked. If you select VAT or any other preset heads, the rate will be automatically filled.
- Cost Center: If the tax/charge is an income (like shipping) or expense it needs to be booked against a Cost Center.
- Description: Description of the tax (that will be printed in invoices/quotes).
- Rate: The Tax rate, eg 16%. This is only applicable where the type of tax is set as On Net Total
- Amount: The Tax amount to be applied. This is only applicable where the type of tax is set as Actual

Get list of templates
---------------------

- Endpoint: |BASE_API_URL|.purchase_tax_template.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": [
            "name",
            "title",
            "disabled",
            "is_default"
        ],
        "filters": [],
        "start": 0,
        "page_length": 0,
        "order_by": "name asc"
    } 

- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

- Refer to `Document List API Parameters <general-guidance.html>`_ for guidance on the payload


Create an Purchase Tax Template
-------------------------------

- Endpoint: |BASE_API_URL|.purchase_tax_template.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "title": "Tanzania VAT Exclusive", 
        "is_disabled": false,
        "is_default": false,
        "taxes": [
            {
                "account": "970100",
                "description": "Provisional Income Taxes",
                "tax_rate": 19,
                "charge_type": "On Net Total",
                "included_in_basic_rate": false,
                "add_deduct_tax": "Add"
            }
        ]
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }

- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Update an Purchase Tax Template
-------------------------------

- Endpoint: |BASE_API_URL|.purchase_tax_template.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "name": "Tanzania VAT Exclusive - EFTA",
        "title": "Tanzania VAT Exclusive Updated", 
        "is_disabled": false,
        "is_default": false,
        "taxes": [
            {
                "account": "970100",
                "description": "Provisional Income Taxes",
                "tax_rate": 20,
                "charge_type": "On Net Total",
                "included_in_basic_rate": false,
                "add_deduct_tax": "Add"
            }
        ]
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields are not exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Delete a Purchase Tax Template
------------------------------

- Endpoint: |BASE_API_URL|.purchase_tax_template.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "Tanzania Tax - EFTA"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

Calling this end point will return a message that you should disable the template instead of deleting it. So consider using the toggle status endpoint to disable the template


Get a single Purchase Tax Template
----------------------------------

- Endpoint: |BASE_API_URL|.purchase_tax_template.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
       "doc_id": "Tanzania Tax - EFTA"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Enable/Disable a Purchase Tax Template
--------------------------------------

To disable or enable a purchase tax template, use this endpoint

- Endpoint: |BASE_API_URL|.purchase_tax_template.toggle_status
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "name": "Tanzania VAT Exclusive - EFTA", 
        "enabled": true 
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }
