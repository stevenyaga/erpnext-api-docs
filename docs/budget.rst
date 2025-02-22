Budget
======

To create a Budget
------------------

.. note:: 

    - When creating a budget against a cost center, you must provide the value of the cost center
    - When creating a budget against a project, you must provide the value of the project
    - To get a list of cost centers, use the Cost Center list API
    - To get a list of projects, use the Project list API

- Endpoint: |BASE_API_URL|.Budget.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "action_if_accumulated_monthly_budget_exceeded": "Warn",
        "action_if_accumulated_monthly_budget_exceeded_on_mr": "",
        "action_if_accumulated_monthly_budget_exceeded_on_po": "",
        "action_if_annual_budget_exceeded": "Stop",
        "action_if_annual_budget_exceeded_on_mr": "",
        "action_if_annual_budget_exceeded_on_po": "", 
        "applicable_on_booking_actual_expenses": true,
        "applicable_on_material_request": false,
        "applicable_on_purchase_order": false,
        "budget_against": "Cost Center", 
        "cost_center": "Main - DCLD",
        "fiscal_year": "2025",
        "monthly_distribution": null, 
        "project": null,
        "accounts": [{
                "account": "5201",
                "budget_amount": 50000
            },
            {
                "account": "5214",
                "budget_amount": 150000
            },
            {
                "account": "4120",
                "budget_amount": 2000000
            }
        ]
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }
  

Get list of Budgets
-------------------

- Endpoint: |BASE_API_URL|.budget.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": ["fiscal_year", "cost_center", "project"],
        "filters": [["fiscal_year", "=", "2025"]],
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


Get a single Budget
-------------------

- Endpoint: |BASE_API_URL|.budget.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "Main - DCLD/2025/001"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Budget
---------------

- Endpoint: |BASE_API_URL|.budget.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "Main - DCLD/2025/001"
    }

