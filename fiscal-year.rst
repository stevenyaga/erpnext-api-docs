Fiscal Year
===========

To create a Fiscal Year
-----------------------

- Endpoint: |BASE_API_URL|.fiscal_year.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "year": "2026",
        "year_start_date": "2026-01-01",
        "year_end_date": "2026-12-31"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Get list of Fiscal Years
------------------------

- Endpoint: |BASE_API_URL|.fiscal_year.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": ["year", "year_start_date", "year_end_date"],
        "filters": [["year_start_date", "<", "2035-02-24"]],
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


Get a single Fiscal Year
------------------------

- Endpoint: |BASE_API_URL|.fiscal_year.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "year": "2026"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Fiscal Year
--------------------

- Endpoint: |BASE_API_URL|.fiscal_year.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "year": "2026"
    }

