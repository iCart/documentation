=====
Basiq
=====

Basiq is a paid third-party service that enables companies and professionals to connect multiple
bank accounts to a single platform. It provides a unified view of all transactions within a single
interface. When integrated with Odoo, it automatically synchronizes bank transactions directly into
its database.

.. note::
   Basiq bank synchronization service is free for Odoo users.

.. seealso::
   - :doc:`../bank_synchronization`
   - `Financial institutions available on Basiq <https://www.basiq.io/resources/supported-insitutions.html>`_

.. _bank-synchronization/basiq/configuration:

Configuration
=============

Basiq account creation
----------------------

To create a Basiq account, go to the `Basiq website <https://dashboard.basiq.io/register>`_ and
follow the registration instructions.

.. _bank-synchronization/basiq/payments:

Business Banking Data Sharing
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Under Australia's Consumer Data Right (CDR) regime, sharing business banking data (for entities
like Sole Traders, Partnerships, Companies, and Trusts) requires an explicit **opt-in**.
Consequently, setting up a business account with Basiq may require additional configuration steps
compared to a standard personal account.

For detailed setup instructions, refer to Basiq's `online documentation <https://api.basiq.io/docs/connecting-business-accounts-via-cdr>`_.

.. seealso::
   `CDR Compliance <https://api.basiq.io/docs/cdr-compliance>`_

.. _bank-synchronization/basiq/odoo-connection:

Connection with Odoo
--------------------

When :ref:`connecting a bank to Odoo <accounting/bank-synchronization/first-synchronization>` using
Basiq as the third-party provider, follow these steps:

#. When connecting to the desired bank, make sure Basiq is selected as the third-party
   :guilabel:`Provider`.
#. Select the :guilabel:`Type of account` and click :guilabel:`Connect`.
#. Fill out the additional information when prompted, and :guilabel:`Continue`.
#. Agree to share data by checking you declare using this service for business purposes, and then
   :guilabel:`Approve`.
#. In the pop-up window, login to Basiq using your **Basiq credentials**. Upon a successful
   connection, you will be redirected to the **Odoo Accounting** dashboard.
#. Select the specific bank account to connect to, and click :guilabel:`Connect Bank`.
#. Access your **Bank Reconciliation** dashboard using your **bank** journal to verify if the
   synchronization was succesful.

.. tip::
   Repeat the process for all banking institutions and accounts for which you need synchronization.

.. seealso::
   :ref:`Update synchronization credentials <accounting/bank-synchronization/update-credentials>`
