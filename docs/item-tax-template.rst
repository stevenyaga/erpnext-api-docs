Item Tax Template
=================

If some of your Items have tax rates different from the standard tax rate assigned in the Taxes and Charges table, then you can create an Item Tax Template and assign it to an Item or Item Group. The rate assigned in the Item Tax Template will get preference over the standard tax rate assigned in the Taxes and Charges table.

Before creating and using an Item Tax Template, it is advised to create the following first:

    * Item
    * Enable 'Automatically add Taxes and Charges from Item Tax Template' in Account Settings

Tax templates are preset with values. For items which have a different tax rate than the others, you need to change it in the Item master. Go to the tax table in the Item, add a row, select the tax type and change the rate. Now, this new rate will over ride the template when creating an invoice. For the Item which is exempted from tax entirely, mention 0% as tax rate.

If you need to have different tax rate applied on some of the items in a Purchase Invoice, attach an item tax template to the purchase invoice item.

.. note::

    In sales and purchase transactions like Purchase Invoice, the taxes on items are calculated as per the Purchase Taxes and Charges Template selected. However, if some items have an Item Tax Template linked, then the taxes are calculated on those items as per the rates mentioned in the Item Tax Template instead of the rates mentioned in the Purchase Taxes and Charges Template.


Get list of templates
---------------------

- Endpoint: |BASE_API_URL|.item_tax_template.list
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


Create an Item Tax Template
---------------------------

- Endpoint: |BASE_API_URL|.item_tax_template.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "title": "Tanzania Zero Rated", 
        "disabled": false, 
        "taxes": [
            {
                "account": "970100", 
                "tax_rate": 0
            }
        ]
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }

- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Update an Item Tax Template
---------------------------

- Endpoint: |BASE_API_URL|.item_tax_template.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "name": "Tanzania Zero Rated - EFTA"
        "title": "Tanzania Zero Rated Updated", 
        "disabled": false, 
        "taxes": [
            {
                "account": "970100", 
                "tax_rate": 0
            }
        ]
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields are not exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Delete an Item Tax Template
---------------------------

- Endpoint: |BASE_API_URL|.item_tax_template.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "Tanzania Zero Rate - EFTA"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Item Tax Template
------------------------------

- Endpoint: |BASE_API_URL|.item_tax_template.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
       "doc_id": "Tanzania Zero Rated - EFTA"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Enable/Disable an Item Tax Template
-----------------------------------

To disable or enable an item tax template, use this endpoint

- Endpoint: |BASE_API_URL|.item_tax_template.toggle_status
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "name": "Tanzania Zero Rated - EFTA", 
        "enabled": true 
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }
