Project
=======

Get list of projects
--------------------

- Endpoint: |BASE_API_URL|.project.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doctype": "Account",
        "fields": ["name", "project_name", "status", "is_active","priority", "cost_center"],
        "filters": [["company", "=", "Demo Company Ltd (Demo)"]],
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

Create Project
--------------

- Endpoint: |BASE_API_URL|.project.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "actual_end_date": null,
        "actual_start_date": null,
        "cost_center": null,
        "customer": null,
        "estimated_costing": 0,
        "expected_end_date": null,
        "expected_start_date": null,
        "is_active": "Yes",
        "priority": "Medium",
        "project_name": "Bridge Construction",
        "status": "Open"
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }


Update Project
--------------

- Endpoint: |BASE_API_URL|.project.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "id": "PROJ-0001",
        "actual_end_date": null,
        "actual_start_date": null,
        "cost_center": null,
        "customer": null,
        "estimated_costing": 0,
        "expected_end_date": null,
        "expected_start_date": null,
        "is_active": "Yes",
        "priority": "Medium",
        "project_name": "Lone Bridge Construction",
        "status": "Open"
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 

Delete Project
--------------

- Endpoint: |BASE_API_URL|.project.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "PROJ-0001"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Project
--------------------

- Endpoint: |BASE_API_URL|.project.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "PROJ-0001"
    }

 
- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

