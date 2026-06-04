=========
Cashmatic
=========

`Cashmatic <https://cashmatic.eu/>`_ :doc:`cash machines <../cash_machines>` enable the automation
of cash transactions.

.. note::
   - The integration with the Cashmatic cash machine only supports payments and refunds.
   - Tasks such as filling and emptying the machine must be performed directly through the cash
     machine interface or via the MyCasmatic app/website, available on `Android
     <https://play.google.com/store/apps/details?id=com.cashmatic.app&pcampaignid=web_share>`_ or
     `iOS <https://apps.apple.com/us/app/mycashmatic/id1661294811>`_.

.. _pos/cashmatic/configuration:

Cash machine configuration
==========================

.. important::
   - Setting up the Cashmatic machine requires the hardware administrator's password and technical
     knowledge. Contact your Cashmatic integration partner for configuration support if assistance
     is needed.
   - The Cashmatic machine must be assigned a static IP address to ensure stable operation.
   - The Cashmatic machine must be on the same local network as the device running Odoo Point of Sale.

To configure the Cashmatic machine as a :ref:`payment method in Odoo
<pos/cashmatic/odoo_configuration>`, first locate the machine's IP address. The IP address is
required regardless of whether the connection uses HTTP or HTTPS. While HTTPS provides a more
secure connection, it requires additional configuration, whereas HTTP is simpler to set up.

To locate the IP address on the Cashmatic machine, go to :menuselection:`Settings --> IP address`.
To locate the IP address using the MyCashmatic app/website, sign in to your account and go to
:menuselection:`Settings --> Network`.

To connect the Cashmatic machine using HTTPS, a valid :doc:`SSL certificate
<../../hardware_network/epos_ssc>` is required:

- **Self-signed certificate**: Navigate to ``https://<cashmatic-ip>:50301`` in your browser,
  replacing ``<cashmatic-ip>`` with the machine's IP address, and manually accept the security
  warning to trust the certificate.
- **Certificate issued by Cashmatic**: Contact your Cashmatic integration partner to request a
  trusted :doc:`SSL certificate <../../hardware_network/epos_ssc>` for your machine.

To enable the HTTP setting on the Cashmatic machine, follow the next steps:

#. On the machine, go to :menuselection:`Settings --> Trusted mode`.
#. Set the mode to :guilabel:`Yes`.
#. In the MyCashmatic app, go to :menuselection:`Settings --> System`, then enable
   :guilabel:`Unsecured APIs`.

.. note::
   Enable HTTP on the cash machine to allow communication through :doc:`Local Network Access (LNA)
   <../../hardware_network/pos_lna>`.

.. _pos/cashmatic/odoo_configuration:

Odoo configuration
==================

To connect the Cashmatic machine to Odoo, follow the next steps:

#. :ref:`Install <general/install>` the :guilabel:`POS Cashmatic Cash Machines` module.
#. Go to :menuselection:`Point of Sale --> Configuration --> Payment Methods` and click
   :guilabel:`New`.
#. Set the :guilabel:`Journal` field to :guilabel:`Cash`.
#. Select the relevant POS in the :guilabel:`Point of Sale` field.
#. Set the :guilabel:`Integration` field to :guilabel:`Cash Machine (Cashmatic)`.
#. In the :guilabel:`Cashmatic Settings` tab, enter the Cashmatic machine's IP address in the
   :guilabel:`Cashmatic IP` field.
#. Enter your Cashmatic user credentials in the :guilabel:`Cashmatic Username` and :guilabel:`Cashmatic
   Password` fields.
#. Enable :guilabel:`Cashmatic Local Network Access` to connect the machine over `HTTP`.

.. note::
   It is highly recommended to use :doc:`Local Network Access <../../hardware_network/pos_lna>`, as
   it bypasses the need for an :doc:`SSL certificate <../../hardware_network/epos_ssc>`.

.. seealso::
   :doc:`../../payment_methods`
