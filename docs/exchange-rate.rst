Exchange Rate
=============

Get list of exchange rates
--------------------------

- Endpoint: |BASE_API_URL|.exchange_rate.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doctype": "Account",
        "fields": ["name", "from_currency", "to_currency", "exchange_rate","for_buying", "for_selling"],
        "filters": [["date", ">=", "1970-01-01"]],
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

Create Exchange Rate
--------------------

- Endpoint: |BASE_API_URL|.exchange_rate.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "date" : "2025-06-01",
        "from_currency" : "USD",
        "to_currency" : "TZS",
        "exchange_rate" : 2500,
        "for_buying" : 1,
        "for_selling" : 1 
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }


Update Exchange Rate
--------------------

- Endpoint: |BASE_API_URL|.exchange_rate.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "id": "2025-06-01-USD-TZS-Selling-Buying",
        "date" : "2025-06-01",
        "from_currency" : "USD",
        "to_currency" : "TZS",
        "exchange_rate" : 3000,
        "for_buying" : 1,
        "for_selling" : 1 
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 

Delete Exchange Rate
--------------------

- Endpoint: |BASE_API_URL|.exchange_rate.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "doc_id": "2025-06-01-USD-TZS-Selling-Buying"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Exchange Rate
--------------------------

- Endpoint: |BASE_API_URL|.exchange_rate.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "doc_id": "2025-06-01-USD-TZS-Selling-Buying"
    }

 
- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

