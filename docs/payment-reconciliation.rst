Payment Reconciliation
======================

Sometimes there is no direct link between payments and invoices. For example, suppose a party is a customer, you send invoices to a customer and the customer sends you block payments or payments based on some schedule that is not linked to your invoices.

In such cases, you can match Payments with Invoices using Payment Reconciliation.



To retrieve unreconciled entries
--------------------------------

- Endpoint: |BASE_API_URL|.payment_reconciliation.get_unreconciled_entries
- Method: **POST**
- Payload:

.. code-block:: json

    {
        "company": "EQUITY FOR TANZANIA",
        "party_type": "Supplier",
        "party": "Sameer Motors Co Ltd",
        "receivable_payable_account": "0001929-USD - Sameer Motors Co Ltd-USD - EFTA"
    }


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- This endpoint returns a list of hanging payments and invoices that have a balance for a specific party


Auto Allocate Payments
----------------------

- Endpoint: |BASE_API_URL|.payment_reconciliation.allocate
- Method: **POST**
- Payload:

.. code-block:: json

   {
    "name": "Payment Reconciliation",
    "owner": null,
    "creation": null,
    "modified": null,
    "modified_by": null,
    "docstatus": null,
    "idx": null,
    "company": "EQUITY FOR TANZANIA",
    "party_type": "Supplier",
    "party": "Sameer Motors Co Ltd",
    "receivable_payable_account": "0001929-USD - Sameer Motors Co Ltd-USD - EFTA",
    "default_advance_account": null,
    "from_invoice_date": null,
    "from_payment_date": null,
    "minimum_invoice_amount": 0.0,
    "minimum_payment_amount": 0.0,
    "to_invoice_date": null,
    "to_payment_date": null,
    "maximum_invoice_amount": 0.0,
    "maximum_payment_amount": 0.0,
    "invoice_limit": 50,
    "payment_limit": 50,
    "bank_cash_account": null,
    "cost_center": null,
    "project": null,
    "invoice_name": null,
    "payment_name": null,
    "doctype": "Payment Reconciliation",
    "payments": [
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 1,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600000",
            "posting_date": "2026-05-28",
            "is_advance": 0,
            "reference_row": null,
            "amount": 0.12,
            "difference_amount": 0.0,
            "remarks": "Amount USD 0.12 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-05-28\nAmount USD 0.12 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 2607.4475,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 2,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600001",
            "posting_date": "2026-05-28",
            "is_advance": 0,
            "reference_row": null,
            "amount": 1815.10999999,
            "difference_amount": 0.0,
            "remarks": "Amount USD 1815.11 to Sameer Motors Co Ltd\nTransaction reference no PI260528145837 dated 2026-05-28\nAmount USD 1815.11 against Purchase Invoice GPI2600025",
            "currency": "USD",
            "exchange_rate": 2607.4475,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 3,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600002",
            "posting_date": "2026-05-29",
            "is_advance": 0,
            "reference_row": null,
            "amount": 400.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 400.0 to Sameer Motors Co Ltd\nTransaction reference no PI260528154241 dated 2026-05-29\nAmount USD 400.0 against Purchase Invoice GPI2600026",
            "currency": "USD",
            "exchange_rate": 2609.3381,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 4,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600003",
            "posting_date": "2026-05-29",
            "is_advance": 0,
            "reference_row": null,
            "amount": 195700.38,
            "difference_amount": 0.0,
            "remarks": "Amount USD 195700.38 to Sameer Motors Co Ltd\nTransaction reference no PI260528154241 dated 2026-05-29\nAmount USD 75.0 against Purchase Invoice GPI2600026",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 5,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600004",
            "posting_date": "2026-05-29",
            "is_advance": 0,
            "reference_row": null,
            "amount": 4718185.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 4718185.0 to Sameer Motors Co Ltd\nTransaction reference no PI260528145837 dated 2026-05-29\nAmount USD 4718184.89 against Purchase Invoice GPI2600025",
            "currency": "USD",
            "exchange_rate": 2609.3381,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 6,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600007",
            "posting_date": "2026-06-03",
            "is_advance": 0,
            "reference_row": null,
            "amount": 100.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 100.0 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-06-03\nAmount USD 100.0 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 2607.0696,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 7,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600009",
            "posting_date": "2026-06-04",
            "is_advance": 0,
            "reference_row": null,
            "amount": 540000.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 540000.0 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-06-04\nAmount USD 203.88 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 8,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600013",
            "posting_date": "2026-06-05",
            "is_advance": 0,
            "reference_row": null,
            "amount": 5211.38,
            "difference_amount": 0.0,
            "remarks": "Amount USD 5213.38 to Sameer Motors Co Ltd\nTransaction reference no PI260605090819 dated 2026-06-05\nAmount USD 2.0 against Purchase Invoice GPI2600005",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        }
    ],
    "allocation": [],
    "invoices": [
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 1,
            "invoice_type": "Purchase Invoice",
            "invoice_number": "GPI2600007",
            "invoice_date": "2026-06-01",
            "amount": 99.99,
            "outstanding_amount": 99.99,
            "currency": "USD",
            "exchange_rate": 0.0,
            "parent": "Payment Reconciliation",
            "parentfield": "invoices",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Invoice",
            "__islocal": 1
        }
    ]
}


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }


- Tha above payload contains all the parameters that are needed to complete the allocation process
- You can either select any particular entries to be allocated or you can click on Allocate button without selecting anything to allocate all the entries. 
- Allocation table will be populated based on FIFO or/and selection.
- Allocated Amount is the amount you want to allocate for the reconciliation.
- Once you have completed the allocation, you can proceed to reconcile the allocated amounts


Reconcile Payments
------------------

- Endpoint: |BASE_API_URL|.payment_reconciliation.reconcile
- Method: **POST**
- Payload:

.. code-block:: json

     {
    "name": "Payment Reconciliation",
    "owner": null,
    "creation": null,
    "modified": null,
    "modified_by": null,
    "docstatus": 0,
    "idx": null,
    "company": "EQUITY FOR TANZANIA",
    "party_type": "Supplier",
    "party": "Sameer Motors Co Ltd",
    "receivable_payable_account": "0001929-USD - Sameer Motors Co Ltd-USD - EFTA",
    "default_advance_account": null,
    "from_invoice_date": null,
    "from_payment_date": null,
    "minimum_invoice_amount": 0.0,
    "minimum_payment_amount": 0.0,
    "to_invoice_date": null,
    "to_payment_date": null,
    "maximum_invoice_amount": 0.0,
    "maximum_payment_amount": 0.0,
    "invoice_limit": 50,
    "payment_limit": 50,
    "bank_cash_account": null,
    "cost_center": null,
    "project": null,
    "invoice_name": null,
    "payment_name": null,
    "doctype": "Payment Reconciliation",
    "invoices": [
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 1,
            "invoice_type": "Purchase Invoice",
            "invoice_number": "GPI2600007",
            "invoice_date": "2026-06-01",
            "amount": 99.99,
            "outstanding_amount": 99.99,
            "currency": "USD",
            "exchange_rate": 0.0,
            "parent": "Payment Reconciliation",
            "parentfield": "invoices",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Invoice",
            "__islocal": 1
        }
    ],
    "allocation": [
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 1,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600000",
            "reference_row": null,
            "invoice_type": "Purchase Invoice",
            "invoice_number": "GPI2600007",
            "allocated_amount": 0.12,
            "unreconciled_amount": 0.12,
            "amount": 0.12,
            "is_advance": null,
            "difference_amount": -0.02509999999995216,
            "gain_loss_posting_date": "2026-05-28",
            "debit_or_credit_note_posting_date": null,
            "difference_account": "900002 - Foreign Exchange Gain / Loss - EFTA",
            "exchange_rate": 2607.6566,
            "currency": "USD",
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "allocation",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Allocation",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 2,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600001",
            "reference_row": null,
            "invoice_type": "Purchase Invoice",
            "invoice_number": "GPI2600007",
            "allocated_amount": 99.86999999999999,
            "unreconciled_amount": 1815.10999999,
            "amount": 1815.10999999,
            "is_advance": null,
            "difference_amount": -20.88279999999213,
            "gain_loss_posting_date": "2026-05-28",
            "debit_or_credit_note_posting_date": null,
            "difference_account": "900002 - Foreign Exchange Gain / Loss - EFTA",
            "exchange_rate": 2607.6566,
            "currency": "USD",
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "allocation",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Allocation",
            "__islocal": 1
        }
    ],
    "payments": [
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 1,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600000",
            "posting_date": "2026-05-28",
            "is_advance": false,
            "reference_row": null,
            "amount": 0.12,
            "difference_amount": 0.0,
            "remarks": "Amount USD 0.12 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-05-28\nAmount USD 0.12 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 2607.4475,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 2,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600001",
            "posting_date": "2026-05-28",
            "is_advance": false,
            "reference_row": null,
            "amount": 1815.10999999,
            "difference_amount": 0.0,
            "remarks": "Amount USD 1815.11 to Sameer Motors Co Ltd\nTransaction reference no PI260528145837 dated 2026-05-28\nAmount USD 1815.11 against Purchase Invoice GPI2600025",
            "currency": "USD",
            "exchange_rate": 2607.4475,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 3,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600002",
            "posting_date": "2026-05-29",
            "is_advance": false,
            "reference_row": null,
            "amount": 400.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 400.0 to Sameer Motors Co Ltd\nTransaction reference no PI260528154241 dated 2026-05-29\nAmount USD 400.0 against Purchase Invoice GPI2600026",
            "currency": "USD",
            "exchange_rate": 2609.3381,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 4,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600003",
            "posting_date": "2026-05-29",
            "is_advance": false,
            "reference_row": null,
            "amount": 195700.38,
            "difference_amount": 0.0,
            "remarks": "Amount USD 195700.38 to Sameer Motors Co Ltd\nTransaction reference no PI260528154241 dated 2026-05-29\nAmount USD 75.0 against Purchase Invoice GPI2600026",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 5,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600004",
            "posting_date": "2026-05-29",
            "is_advance": false,
            "reference_row": null,
            "amount": 4718185.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 4718185.0 to Sameer Motors Co Ltd\nTransaction reference no PI260528145837 dated 2026-05-29\nAmount USD 4718184.89 against Purchase Invoice GPI2600025",
            "currency": "USD",
            "exchange_rate": 2609.3381,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 6,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600007",
            "posting_date": "2026-06-03",
            "is_advance": false,
            "reference_row": null,
            "amount": 100.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 100.0 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-06-03\nAmount USD 100.0 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 2607.0696,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 7,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600009",
            "posting_date": "2026-06-04",
            "is_advance": false,
            "reference_row": null,
            "amount": 540000.0,
            "difference_amount": 0.0,
            "remarks": "Amount USD 540000.0 to Sameer Motors Co Ltd\nTransaction reference no PI260525153836 dated 2026-06-04\nAmount USD 203.88 against Purchase Invoice GPI2600018",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        },
        {
            "name": null,
            "owner": null,
            "creation": null,
            "modified": null,
            "modified_by": null,
            "docstatus": 0,
            "idx": 8,
            "reference_type": "Payment Entry",
            "reference_name": "GPE2600013",
            "posting_date": "2026-06-05",
            "is_advance": false,
            "reference_row": null,
            "amount": 5211.38,
            "difference_amount": 0.0,
            "remarks": "Amount USD 5213.38 to Sameer Motors Co Ltd\nTransaction reference no PI260605090819 dated 2026-06-05\nAmount USD 2.0 against Purchase Invoice GPI2600005",
            "currency": "USD",
            "exchange_rate": 1.0,
            "cost_center": null,
            "parent": "Payment Reconciliation",
            "parentfield": "payments",
            "parenttype": "Payment Reconciliation",
            "doctype": "Payment Reconciliation Payment",
            "__islocal": 1
        }
    ]
}


- Headers:

.. code-block:: json

    {
        "Authorization": "token <YOUR_TOKEN>"
    }

- Ensure you have populated the value of **allocations** before triggering the reconcile endpoint
 
