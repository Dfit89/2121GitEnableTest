---
description: 'PLM Solution: The following sample object types are
  required for the PLM private label food solution data model to work.'
title: '\[%=Heading.Level1%\]'
---

Sample Object Types
===================

The following sample object types are required for the PLM private label
food solution data model to work.

Composite Sample
----------------

Composite Sample represents a product variation that contains more than
one recipe. It is where suppliers see an overview of the product, the
recipes contained in the product and enter data that is relevant to the
product as a whole.

![](../../../../Resources/Images/Solution%20Enablement/PLM/Composite%20Sample%20Illustration.jpg)

Sample
------

A Sample, also known as a Supplier Response, is an object that is
created for each supplier who should respond to recipe specifications.
This is where the supplier details the proposed recipe based on the
specification received from the customer.

Each supplier has one equivalent object per variant where they respond
to the specifications. All objects displayed underneath the Macaroni and
Cheese Project in the image below are used to handle Suppliers\'
recipes.

![](../../../../Resources/Images/Solution%20Enablement/PLM/SampleSupplierResponse.png)

For a recipe response, some attributes that might be included are the
following:

+---------------------+---------------------+-----------------------+
| Recipe Requirements | Recipe Parameters   | Recipe Ingredients    |
+=====================+=====================+=======================+
| Meets Requirement?  | Meets Requirement?  | Ingredient            |
|                     |                     |                       |
| Response Detail     | Response Detail     | Ingredient Quantity % |
|                     |                     |                       |
| Additional Comments | Method              | Country of Origin     |
|                     |                     |                       |
|                     | Additional Comments |                       |
+---------------------+---------------------+-----------------------+

Additionally, a supplier can provide Nutritional Information and Other
Information related to the product.

Label Variant Sample
--------------------

This is an object that is created for each supplier who should respond
to package label specifications.

![](../../../../Resources/Images/Solution%20Enablement/PLM/LabelVariantSample.png)

For a label response, some attributes that might be included are the
following:

+----------------------+----------------------+----------------------+
| Label Requirements   | Label Details        | [Applicable          |
|                      |                      | Recycling            |
|                      |                      | Codes]{style         |
|                      |                      | ="font-size: 11pt;"} |
+======================+======================+======================+
| Meets Requirement?   | Barcode Placement    | [List of values to   |
|                      |                      | select applicable    |
| Response Detail      | Running Direction Of | recycling            |
|                      | Barcode              | codes]{style         |
| Additional Supplier  |                      | ="font-size: 11pt;"} |
| Comments             | Net Content          |                      |
|                      | (Imperial)           |                      |
| Help Text            |                      |                      |
|                      | Net Content (Metric) |                      |
|                      |                      |                      |
|                      | Net Weight           |                      |
|                      | (Imperial)           |                      |
|                      |                      |                      |
|                      | Net Weight (Metric)  |                      |
|                      |                      |                      |
|                      | Applicable Recycling |                      |
|                      | Codes                |                      |
+----------------------+----------------------+----------------------+

Packaging Variant Sample
------------------------

An object that is created for each supplier who should respond to
packaging specifications.

![](../../../../Resources/Images/Solution%20Enablement/PLM/PackagingVariantSample.png)

For a recipe response, some attributes that might be included are the
following:

+------------------------------+---------------------------------+
| Packaging Requirements       | Packaging Elements              |
+==============================+=================================+
| Meets Requirement?           | Packaging Level                 |
|                              |                                 |
| Response Detail              | Packaging Type                  |
|                              |                                 |
| Additional Supplier Comments | Packaging Element Type          |
|                              |                                 |
|                              | Packaging Element Description   |
|                              |                                 |
|                              | Packaging Material Function     |
|                              |                                 |
|                              | Packaging Material Type         |
|                              |                                 |
|                              | Packaging Material Type (other) |
|                              |                                 |
|                              | Is Material Recyclable          |
|                              |                                 |
|                              | Packaging Material Color        |
|                              |                                 |
|                              | Packaging Height                |
|                              |                                 |
|                              | Packaging Depth                 |
|                              |                                 |
|                              | Packaging Width                 |
|                              |                                 |
|                              | Packaging Diameter              |
|                              |                                 |
|                              | Packaging Material Thickness    |
|                              |                                 |
|                              |                                 |
+------------------------------+---------------------------------+

For each Packaging specification, three Packaging Elements will be
created underneath the Packaging Elements node: Consumer Packaging
(Packaging Level 1), Packaging Element (Packaging Level 2), Packaging
Tray (Packaging Level 3)
