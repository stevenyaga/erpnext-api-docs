================================
Integration of Backend API Guide
================================

.. note::

    - All the interactions with the backend must be authenticated using Token Authentication. A user has to authenticate first by calling the login endpoint
    
    - On successful login, a token will be provided.
    
    - This token has to be supplied as a header when calling the api. See the `Passing auth token <general-guidance.html>` section. 
    
    - When you need to specify a transaction code, be sure to provide the code under **transaction_code** in the payload. Note the transaction_code is not applicable when making payments


Terms
=====


- **SERVER_URL** is a placeholder representing the fully qualified domain name or Ip address of the backend server
