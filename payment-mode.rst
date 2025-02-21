
Payment Mode
============

Create a Payment Mode
---------------------
 
- Endpoint: |BASE_API_URL|.payment_mode.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "mode_of_payment": "Mpesa",
        "enabled": "true",
        "type": "Cash",
        "default_account_number": "1110"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a list of Payment Modes
---------------------------

- Endpoint: |BASE_API_URL|.payment_mode.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": ["mode_of_payment", "type", "enabled"],
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


- Refer to `Document List API Parameters <general-guidance.html>`_ for guidance on the payload. 

Get a single Payment Mode

- Endpoint: |BASE_API_URL|.payment_mode.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "payment_mode": "Mpesa"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Delete a Payment Mode

- Endpoint: |BASE_API_URL|.payment_mode.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "payment_mode": "Mpesa"
    }
