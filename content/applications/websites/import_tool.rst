===========
Import Tool
===========

The **Import Tool** lets you recreate your existing website inside
Odoo by simply providing a URL. The tool fetches the pages, rebuilds them as Odoo
website pages, and optionally pulls in products and blog posts at the same time.
Your images, sitemap, header and footer will also be imported.

Getting There
-------------

Go to **Settings ▸ Website ▸ Import Website**.

Filling in the Form
-------------------

**Website URL**
   Paste the address of the site you want to import (e.g. ``https://www.example.com``).
   The limit for the number of pages is 500. If you need more, reach out to https://www.odoo.com/help

**Import products**
   Turn this on if your website sells products and you want them imported into your Odoo shop.
   The required module is installed automatically. By default, all products found will be imported.

   Currently, we support product imports from:

   - Metadata
   - WooCommerce
   - Shopify
   - :ref:`PrestaShop <import_tool/prestashop>`

**Import blogs**
   Turn this on to import your blogs. The required module is installed automatically.
   By default, all blogs found will be imported.

   Currently, we support blog imports from:

   - WordPress
   - :ref:`Ghost <import_tool/ghost>`

Submitting the Request
----------------------

Click **Import my website**. Once the request is finished, you will receive an email or notification
with some information about the number of pages, products and blogs imported.

.. _import_tool/prestashop:

PrestaShop
----------

**Creating an API key**

To import PrestaShop products, you will need to turn on the Webservice setting and provide an API
key. For all versions from PrestaShop 1.7 and up, the process of creating an API key is the same.

1. Go to your website settings, e.g., ``https://example.com/admin1``

2. Navigate to *Advanced Parameters*

   .. image:: import_tool/prestashop-advanced-parameters.png
      :alt: Advanced Parameters

3. Click *Webservice*

   .. image:: import_tool/prestashop-webservice.png
      :alt: Webservice

4. *Enable PrestaShop's webservice*

   .. image:: import_tool/prestashop-toggle-webservice.png
      :alt: Enable PrestaShop's webservice

5. *Add new webservice key*

   .. image:: import_tool/prestashop-create-api-key.png
      :alt: Add new webservice key

6. Set the permissions. Below are the permissions required. If any are missing, it may not work as
   expected.

   .. list-table::
      :header-rows: 1

      * - Resource
        - Method
      * - products
        - GET
      * - categories
        - GET
      * - combinations
        - GET
      * - product_option_values
        - GET
      * - product_options
        - GET
      * - images
        - GET

7. Copy the API key and click save.

   .. image:: import_tool/prestashop-api-key.png
      :alt: Copy the API key and save

.. _import_tool/ghost:

Ghost
-----

**Creating an API key**

To import blogs from your Ghost website, you will need to create an API key. To do this, follow the
steps on `Ghost Content API documentation <https://docs.ghost.org/content-api#key>`_.
Copy the *Content API key* into the import form to import your blogs.

Note that no permissions need to be set, since this API key only gives access to public data
anyway.

Tips
----

- Do a trial on `Website Import Tool Trial <https://www.odoo.com/fr_FR/page/startwebsite>`_ to see if
  the tool is able to import your website.
- You do not have to import your website with your product or blogs. You can always just import the
  products or blogs independently.
- If a page does not look right after import, you can edit it directly in the
  Odoo website builder like any other page.
- Make sure your website is accessible and not protected by Cloud Flare and
  similar things.
- For the best result, make sure you have your database updated to the most
  recent version of Odoo.
