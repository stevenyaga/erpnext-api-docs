Chart of Accounts
=================

Get list of accounts
--------------------

- Endpoint: |BASE_API_URL|.account.list
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "fields": [
            "name",
            "account_name",
            "parent_account",
            "account_type",
            "root_type",
            "is_disabled"
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

Create an Account
-----------------

- Endpoint: |BASE_API_URL|.account.create
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "account_name": "Cash 2",
        "account_number": "1110",
        "parent_account_number": "1100",
        "account_type": "",
        "is_group": false
    }

- Headers

.. code-block:: json

    {
       "Authorization": "token <YOUR_TOKEN>"
    }

- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept


Update an Account
-----------------

- Endpoint: |BASE_API_URL|.account.update
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "account_number": "1110",
        "account_name": "Updated Cash 2",
        "parent_account_number": "1100",
        "account_type": "",
        "is_group": false
    }


- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- These fields may not be exhaustive. Check the general guidance section on how to check all the parameters that an endpoint can accept

Delete an Account
-----------------

- Endpoint: |BASE_API_URL|.account.delete
- Method: **DELETE**
- Payload:

.. code-block:: json

    {
        "account_number": "1110"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


Get a single Account details
----------------------------

- Endpoint: |BASE_API_URL|.account.get
- Method: **GET**
- Payload:

.. code-block:: json

    {
        "account_number": "1110"
    }


- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

