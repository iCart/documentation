=============
Field service
=============

The field service feature allows onsite interventions to be scheduled directly in the Planning
app. Work performed can be recorded using custom :ref:`worksheets
<planning/field-service/worksheets>`, while :ref:`materials used
<planning/field-service/products>` and time spent can be tracked on the :ref:`shift
<planning/field-service/record>` and billed to the customer. A customer report can also be
generated at the end of the intervention for signature, and :ref:`itineraries
<planning/field-service/itinerary>` can be planned for field employees.

To activate the feature, go to :menuselection:`Planning --> Configuration --> Settings`, enable
:guilabel:`Field Service`, and click :guilabel:`Save`.

.. _planning/field-service/shifts:

Intervention planning
=====================

xxx or should the heading say field service shift instead of intervention?


Field service shifts can be created:

- directly from the Planning app, in the same way as standard :ref:`shifts <planning/create-shift>`
- :ref:`from sales order <planning/field-service/shifts-sales-orders>`
- :ref:`from helpdesk tickets <planning/field-service/ticket>`
- xxx check what else

Field service-specific information is added manually or automatically, depending on the use case,
using the following fields on the shift form:

- :guilabel:`Customer`: Select or create the relevant customer.
- :guilabel:`Sales Order`: If the intervention must be :ref:`billed
  <planning/field-service/billing>`, select the relevant sales order. Only the sales orders linked
  to the specified customer and containing service products are available in the dropdown menu. If
  the shift was :ref:`created from a sales order <planning/field-service/shifts-sales-orders>`, this
  field is filled automatically.

xxx check this

-:guilabel:`Worksheet`: the default :ref:`planning/field-service/worksheets>` is automatically
  selected. Choose a different one from the dropdown menu if needed.
- :guilabel:`Under warranty`: xxx ask about this

.. tip::
   Ensure the customer has a valid address if :ref:`itinerary planning
   <planning/field-service/itinerary>` is required.

xxx change/check this whole paragraph above

Once the shift has been created, click :guilabel:`Publish` to schedule it and notify the assigned
employee by email.

.. _planning/field-service/shifts-sales-orders:

Creating field service shifts from sales orders
-----------------------------------------------

Field service shifts can be created directly from a sales order.

Create a quotation in :guilabel:`Sales`, select :guilabel:`Field Service` as the product, and
click :guilabel:`Confirm`. Click the :guilabel:`Field Service` smart button to schedule it. if the
:guilabel:`Plan Services` feature is enabled in the settings of your Field Service product, click
the :guilabel:`To Plan` smart button. That way, only the role selected to perform your Field
Service shift will be displayed to schedule the shift.

xxx add that Field Service product automatically created when Field service feature enabled (double-check
to be sure)

xxx add this maybe: avec ce produit field service ajouté dans le sales order et configuré comme
tel, si je clique dans le calendrier d'une personne, il propose les shifts avec le client blabla

.. _planning/field-service/ticket:

Creating shifts from helpdesk tickets
-------------------------------------

If you have the Helpdesk app installed, you can
:ref:`create field service shifts from a helpdesk ticket <helpdesk/field>`.

.. _planning/field-service/record:

Intervention recording
======================

xxx need to add that you can only sign in to a shift if it has been published!

To record the activity of a field service shift as a worker on site:
xxx check whole doc to see if we can maybe reuse this formulation of imperative + "as a technician"
or something similar

#. Go to :menuselection:`Planning --> Planning --> My Planning`.
#. Click on a field service shift.
#. Click the :guilabel:`Sign in` button to confirm you're starting to work on the shift, making
   the shift go from :guilabel:`Scheduled` to :guilabel:`In Progress`.
#. Fill the shift form with the required items, such as photos, note,
   :ref:`worksheet <field-service/worksheets/on-site>`, :ref:`products <field-service/product>` etc.
#. Click :guilabel:`Complete` to confirm the field service work is done and open the field service
   report preview in the customer portal.

.. _planning/field-service/geolocation:

Geolocation
-----------

To track the technician's location at the start and end of (i.e., when they sign
in and complete) an intervention, go to :menuselection:`Planning --> Configuration --> Settings` and
enable :guilabel:`Geolocation` in the :guilabel:`Field service` section.

Once enabled, technicians are geolocalized when click :guilabel:`Sign in` and :guilabel:`Complete`
on a shift.

.. _planning/field-service/billing:

Billing
=======

To invoice customers for time spent on and :ref:`materials <planning/field-service/products>` used
during onsite interventions, go to :menuselection:`Planning --> Configuration --> Settings` and
enable :guilabel:`Billing` in the :guilabel:`Field service` section.

  .. note::
     - Enabling the :guilabel:`Billing` feature automatically installs the :doc:`Sales app
       </applications/sales/sales>`.
     - The :ref:`Products <planning/field-service/products>` and :ref:`Customer Report
       <planning/field-service/customer-report>` features are enabled by default when
       :guilabel:`Billing` is activated.


xxx explain process?
possible to add a sales order already on the shift
or sales order created
what happens if sales order already linked to shift AND we add products on a shift? are those added
to the existing sales order?

.. _planning/field-service/products:

Products
--------

Field service workers commonly use materials to complete their work. These :doc:`products
</applications/websites/ecommerce/configuration/products>` can be recorded in field service shifts
so they can be billed to customers.

To be able to add products to shifts, the :ref:`Billing <planning/field-service/billing>` feature
must be enabled in the Planning settings. The :guilabel:`Products` setting is then automatically
enabled as well.

.. _field-service/product/product-shift:

Using products on a field service shift
---------------------------------------

To add products to a shift as a field service worker performing a job on site,
:ref:`start working on a field service task in planning <field-service/performing-shift>`, then
follow these steps:

#. Click the :guilabel:`0 products`  button.
#. Click :guilabel:`Add` on a product card to add it to your task.
#. If needed, adjust the number of products using the :guilabel:`-` and :guilabel:`+` buttons.
#. Click the :guilabel:`Back` button to return to the shift.

Going back to your task, the products button now displays the amount of products you added to the
shift. You can return to the product catalog at any time to edit the product selection.

.. tip::
   - To create and edit products from the Planning app, go to :menuselection:`Planning -->
     Configuration --> Products`.
   - To find your products more easily in the catalog, use the search bar and filter your products
     by :guilabel:`Product Category` and :guilabel:`Attributes`.

.. note::


Si y a un produit dans le shift, ça crée un sales order automatiquement
si pas de sales order défini sur le shift (ou produit ajouté qui a créé un sales order), le shift n'est pas billable

.. _planning/field-service/quotations:

Quotations
----------

Quotations can be created directly from field service shifts if necessary, for example when
additional work or materials are identified on-site. To activate this feature, go to
:menuselection:`Planning --> Configuration --> Settings` and  enable :guilabel:`Quotations` in the
:guilabel:`Field service` section.

To create a quotation from a shift, click the :guilabel:`Quotation` button.
xxx check this

.. _planning/field-service/customer-report:

Customer report
---------------

To be able to generation a customer report upon shift completion, the :ref:`Billing
<planning/field-service/billing>` feature must be enabled in the Planning settings. The
:guilabel:`Customer Report` setting is then automatically enabled as well.

.. tip::
   Enable :guilabel:`Hide prices on customer report` under :guilabel:`Products` in the Planning
   settings to generate a report without product prices. xxx test this!

The report is generated automatically at the end of the intervention if :ref:`products
<planning/field-service/products>` have been added to the shift and/or if a :ref:`worksheet
<planning/field-service/worksheets>` has been filled. It opens in the customer portal when
the technician click :guilabel:`Complete`in the shift form. Clicking :guilabel:`Sign Report` allows
to collect the customer's signature and send the report to the customer.

xxx check when report is sent to customer exactly and if we need the signature for this

.. _planning/field-service/worksheets:

Worksheets
==========

Worksheets help field service workers perform and report on-site shifts. They can include various
content, such as instructions and to-do lists.

.. _planning/field-service/worksheet-configuration:

Configuration
-------------

To use worksheets for field service interventions, go to :menuselection:`Planning --> Configuration
--> Settings`, enable :guilabel:`Worksheets` in the :guilabel:`Field service` section, and click
:guilabel:`Save`.

Then, create worksheet templates:

#. Go to :menuselection:`Planning --> Configuration --> Worksheet Templates`.
#. Click :guilabel:`New`.
#. Enter a :guilabel:`Name` and, if applicable, select a :guilabel:`Company`.
#. Click :guilabel:`Add Property`, then :ref:`configure the property field <property_field/add>` as
   needed.
#. Repeat as needed for each additional property field.

.. tip::
   - To edit a property field, click the :icon:`fa-pencil` (:guilabel:`pencil`) icon next to it,
     perform the necessary changes in the popover, then click outside the popover to save the
     changes.
   - To remove a property field, click the :icon:`fa-pencil` (:guilabel:`pencil`) icon next to it,
     click `:icon:`fa-trash` :guilabel:`Delete` in the popover, then click :guilabel:`Delete Field`.
   - To reorder property fields, use the :icon:`oi-draggable` (:guilabel:`drag handle`) icon.

.. seealso::
   :doc:`/applications/essentials/property_fields`

.. note::
   - The first worksheet in the list view is applied by default to field service shifts, unless one is
     :ref:`manually selected <planning/field-service/worksheet-shift>`. To reorder worksheet
     templates, use the :icon:`oi-draggable` (:guilabel:`drag handle`) icon.
   - Worksheet templates can also be :ref:`created and/or edited from the shift form
     <planning/field-service/worksheet-shift>`.

.. _planning/field-service/worksheet-shift:

Worksheets in shifts
--------------------

The default :ref:`worksheet template <planning/field-service/worksheet-configuration>` is
automatically selected in the :guilabel:`Worksheet` field on the shift form upon :ref:`creation
<planning/field-service/shifts>`. Select a different one from the dropdown menu if needed.

.. tip::
   To edit a worksheet template from the shift, hover over the :guilabel:`Worksheet` dropdown menu,
   click the :icon:`fa-external-link` (:guilabel:`internal link`) icon, then
   :ref:`edit the template <property_field/add>`. Changes apply to all shifts using that template.

The worksheet can then be filled in the :guilabel:`Worksheet` tab on the shift form :ref:`during
on-site interventions <planning/field-service/record>`.

.. _planning/field-service/itinerary:

Itinerary planning
==================

By default, Odoo Planning displays a static map with all intervention locations for the day
pinned. To view it, go to :menuselection:`Planning --> Planning --> Maps`. To display an
itinerary on the map, enable MapBox:

#. Create or sign in to a `MapBox account <https://www.mapbox.com/>`_.
#. `Create a token <https://docs.mapbox.com/help/getting-started/access-tokens/#adding-url-restrictions-to-access-tokens>`_.
#. Go to the `Access tokens <https://account.mapbox.com/access-tokens/>`_ page on MapBox and copy
   the token.
#. In Odoo, open the Settings app and scroll down to the :guilabel:`Integrations` section.
#. Paste the MapBox access token in the :guilabel:`Token` field under :guilabel:`Map Routes`, then
   click :guilabel:`Save`.

.. _planning/field-service/map:

Viewing the intervention itinerary
----------------------------------

.. important::
   For a field service shift to appear on the map, a valid address must be provided for the
   customer.

Technicians can display their field service interventions for the day on a map by going to
:menuselection:`Planning --> Planning --> My Map`. Shifts are sorted by :guilabel:`Planned Date` in
the left pane. They can open the complete itinerary on the Google Maps website or app by clicking
:guilabel:`Maps`. Google Maps uses the current location as the starting point.

.. tip::
   - By default, the map displays today's planned interventions. Remove the :guilabel:`Start Date:
     Today` filter in the search bar to display all shifts, sorted by date and time in the left
     pane.
   - Click a shift in the left pane or its map pin to display the task details. From there, click
     :guilabel:`Open` to open the shift form, or :guilabel:`Navigate to` to get directions from the
     current location to the intervention's location.

xxx should we also talk about Planning --> Maps? when would it be used?
