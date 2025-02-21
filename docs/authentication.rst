Authentication
==============

- To login, make a **POST** request as below

- Endpoint: |BASE_API_URL|.user.login
- Method: **POST**
- Payload

.. code-block:: json

    {
        "usr": "user@domain.com",
        "pwd": "password"
    }


- A response will be as below:

.. code-block:: json 

    {
        "message": {
            "success": true,
            "status": 200,
            "message": "Logged in",
            "data": {
            "id": "user@domain.com",
            "full_name": "user",
            "token": "03dfdfdfd3:weserttf3434"
            }
        },
        "home_page": "/app",
        "full_name": "User"
    }

.. note:: 

  - Store the returned value of the **token** property as this is token will be supplied to subsequent API calls for authentication purposes