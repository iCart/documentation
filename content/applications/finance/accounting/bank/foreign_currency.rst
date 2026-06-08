===========================================
Manage a bank account in a foreign currency
===========================================

In Odoo, every transaction is recorded in the default currency of the company, and reports are all
based on that default currency. With a bank account in a foreign currency, for every
transaction, Odoo stores two values:

-  The debit/credit in the currency of the company.
-  The debit/credit in the currency of the bank account.

Currency rates are updated automatically using the web services of a banking institution. By
default, Odoo uses the European Central Bank's web services but other options are available.

.. seealso::
   :doc:`../get_started/multi_currency`

Create a new bank account
=========================

Go to :menuselection:`Accounting --> Configuration --> Journals` and click :guilabel:`New`.
Select the type :guilabel:`Bank` or :guilabel:`Card` to configure a bank account.
Once back in the journal, enter a :guilabel:`Journal Name`.

.. image:: foreign_currency/foreign-journal.png
   :align: center
   :alt: Example of a created bank journal.

Upon creation of the journal, the bank account is automatically linked to the journal. It can be
found under :menuselection:`Accounting --> Configuration --> Chart of Accounts`.
A currency can be added in the account by accessing the account, selecting a currency in the
:guilabel:`Currency` field, and then clicking :guilabel:`Save`.

Unrealized Currencies Report
============================

This report gives an overview of all unrealized amounts in a foreign currency on the balance sheet,
and allows the adjustment of an entry or manually set an exchange rate. To access this report, go to
:menuselection:`Review --> Unrealized Currencies` and have access to all open entries in the
balance sheet.

.. image:: foreign_currency/foreign-gains-losses.png
   :align: center
   :alt: View of the Unrealized Gains/Losses journal.

To use a different currency rate than the one set in
:menuselection:`Accounting --> Configuration --> Settings`, click the :guilabel:`Exchange Rates`
button and change the rate of the foreign currencies in the report.

.. image:: foreign_currency/foreign-exchange-rates.png
   :align: center
   :alt: Menu to manually change exchange rates.

When manually changing exchange rates, a yellow banner appears allowing a reset back to Odoo's rate.
To do so, simply click :guilabel:`Reset to Odoo's Rate`.

.. image:: foreign_currency/foreign-reset-rates.png
   :align: center
   :alt: Banner to reset back to Odoo's rates.

In order to update the balance sheet with the amount of the :guilabel:`Adjustment` column,
click on the :guilabel:`Adjustment Entry` button in the top-left-corner. In the pop-up window,
select a :guilabel:`Journal`, an :guilabel:`Expense Account` and an :guilabel:`Income Account` to
calculate and process the unrealized gains and losses.

You can set the date of the report in the :guilabel:`Date` field. Odoo automatically reverses the
booking entry to the date set in :guilabel:`Reversal Date`.

Once posted, the :guilabel:`Adjustment` column should indicate `0.00`, meaning all unrealized
gains and losses have been adjusted.

.. image:: foreign_currency/foreign-adjustment.png
   :align: center
   :alt: Unrealized Currency Gains/Losses report once adjusted.
