Delete Data
===========

Delete all transactions and related data
----------------------------------------

- Endpoint: |BASE_API_URL|.data.delete_data
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "extra_data_types": ["Budget"]
    }

- Headers

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 

- This endpoint, by default, deletes transactions linked to a company and also other documents that are passed as list in the **extra_data_types** parameter. Currently, the following data types can be deleted

    - Customer
    - Supplier
    - Budget
  
- Call the **check deletion status** end point and ensure you get a success result before calling this endpoint

.. note:: 

    Deleting transactions may take a while and is a queued function. Bear this in mind that you will need to give some time to the deletion to complete, before making a subsequent endpoint call.

.. warning:: 

    The backend will run data integrity validations to ensure there are no orphaned records before deleting. There may be instances where deleting a data type will not succeed because a particular record is linked to another record of another type


Check Deletion Status
---------------------

- Check status of any data deletion tasks. Ensure you get a success result before issuing a transaction deletion API request

- Endpoint: |BASE_API_URL|.data.check_delete_status
- Method: **POST**
- Payload: Empty 
- Headers

.. code-block:: json
    
    {
        "Authorization": "token <YOUR_TOKEN>"
    }
 