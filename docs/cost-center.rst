Cost Center
===========

Get list of cost centers
------------------------

- Endpoint: |BASE_API_URL|.cost_center.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doctype": "Account",
        "fields": ["name", "cost_center_name", "cost_center_number", "disabled", "is_group", "parent_cost_center"],
        "filters": [["company", "=", "Demo Company Ltd"]],
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

Create Cost Center
------------------

- Endpoint: |BASE_API_URL|.cost_center.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
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


Update Cost Center
------------------

- Endpoint: |BASE_API_URL|.cost_center.update
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
 

Delete Cost Center
------------------

- Endpoint: |BASE_API_URL|.cost_center.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "Mombasa - DCLD"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Cost Center
------------------------

- Endpoint: |BASE_API_URL|.cost_center.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "Mombasa - DCLD"
    }

 
- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

