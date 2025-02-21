General Guidance
================

Document List API Parameters
----------------------------

- The API to get a list of documents expects a number of parameters. They are

 - **doctype**: This is the type of data you are retrieving e.g Journal Entry, Account, Report
 - **fields**: This is a list of fields that you want to select from the database
 - **start**: Used when pagination is active to specify the offset from which to start record selection
 - **page_length**: Used when pagination is active to specify the number of records to retrieve during selection
 - **order_by**: Specifies how the records should be ordered. See examples below:

   1. `"name desc"`. Sort by name field descending
   2. `"name desc, creation asc"`. Sort by name field descending first then by creation in an ascending order

 - **filters**: These are the filters that will be applied when selecting data. This can be a simple json object or a list of lists. See examples below

   - Filters as a Json object
  
            .. code-block:: json
               :caption: Filters as a Json object

                {
                    "posting_date": "2025-02-08",
                    "supplier": "ABC Ltd"
                }


   - Filters as a list

        .. code-block:: python

            [
                ["posting_date", "=", "2025-02-08"],
                ["supplier", "=", "ABC Ltd"]
            ] 


Passing auth token
------------------

- The authorization token is passed via headers. The header name is **Authorization** and the value is a combination of the word token and the actual token as below.

::  
    
    "Authorization": "token {ACTUAL_TOKEN}"

- The sample payloads included here may not include all the fields that an end point may expect. To see all the parameters that an end point can accept, navigate to **{SERVER_URL}/swagger**. Drill down to the specific end point and all the parameters will be shown there

