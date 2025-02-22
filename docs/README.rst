ERPNext API Integration
=======================

- This project documents the various ERPNext endpoints that can be consumed during integration with the accounts module

- The full documentation is hosted at `Read the Docs <https://erpnext-api.readthedocs.io/>`_.

- Run the below command to build html version for local preview. You will then serve the HTML files as shown in the subsequent command

.. code-block:: bash

    sphinx-build /docs docs/html/


- To serve the docs locally

.. code-block:: bash

    python3 -m http.server 8080


.. note:: 

    To generate local PDF outputs

       - Install Sphinx-SimplePDF extension `Simple PDF instructions <https://sphinx-simplepdf.readthedocs.io/en/latest/_downloads/b7f58750273e059215e38486bce6e343/Sphinx-SimplePDF.pdf>`_
       
       - Run the following command to output PDF
   
            .. code-block:: bash

                sphinx-build -M simplepdf . _build

       - Navigate to the _build directory and the PDF output will be inside that folder

