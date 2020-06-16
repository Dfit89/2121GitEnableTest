---
description: 'PLM Solution: The following variant object types are
  required for the PLM private label food solution data model to work.'
title: '\[%=Heading.Level1%\]'
---

Variant Object Types
====================

The following variant object types are required for the PLM private
label food solution data model to work.

Design Specification Composite Variant
--------------------------------------

A Design Specification Composite Variant represents a specification for
a product variation that requires more than one recipe, such as a box of
macaroni and cheese, which contains separate recipes for the macaroni
and the cheese sauce.

![](../../../../Resources/Images/Solution%20Enablement/PLM/Design%20Specification%20Composite%20Variant%20Illustration.jpg)

Design Specification Variant
----------------------------

A design specification variant (recipe specification) represents a
flavor variation for one or more new products. Details about
specifications, requirements, and parameters for each flavor variation
are collected on this object.

For example, the Macaroni and Cheese Project will have two flavor
variations:

-   Elbow Macaroni
-   Spirals Macaroni

![](../../../../Resources/Images/Solution%20Enablement/PLM/DesignSpecificationV.png)

For a recipe specification, some attributes or object types that might
be included are the following:

+----------------+----------------+----------------+----------------+
| Recipe         | Specified      | Recipe         | Recipe         |
| Information    | Ingredients    | Requirements   | Parameters     |
+================+================+================+================+
| [Flavor        | Ingredient     | Requirement    | Parameter Type |
| Descriptio     |                | Type           |                |
| n]{style="font | Ingredient     |                | Help Text      |
| -size: 11pt;"} | Allowance      | Requirement    |                |
|                |                | Description    | Sort Order     |
|                | Ingredient     |                |                |
|                | Precision      | Help Text      |                |
|                |                |                |                |
|                | Ingredient     | Sort Order     |                |
|                | Quantity       |                |                |
|                |                |                |                |
|                | Specification  |                |                |
|                | Details        |                |                |
+----------------+----------------+----------------+----------------+

Design Specification Packaging Variant
--------------------------------------

A design specification packaging variant (packaging variant) represents
a package size variation for one or more new products. A packaging
variant description and requirements are collected on this object. In
the example below, the Macaroni & Cheese Project will be produced in one
package size: 7.25 oz.

![](../../../../Resources/Images/Solution%20Enablement/PLM/DSPVariant.png)

For a packaging variant, some of the following attributes may apply:

+-------------------------------+----------------------------------+
| Packaging Specification       | Packaging Requirements           |
+===============================+==================================+
| Packaging Name                | [Type]{style="font-size: 11pt;"} |
|                               |                                  |
| Packaging Variant Description | Requirement Description          |
|                               |                                  |
|                               | Help Text                        |
|                               |                                  |
|                               | Sort Order                       |
+-------------------------------+----------------------------------+

For each packaging specification, three \'Packaging Elements\' will be
created underneath the Packaging Elements node.

-   Consumer Packaging (Packaging Level 1)
-   Packaging Element (Packaging Level 2)
-   Packaging Tray (Packaging Level 3)

Design Specification Label Variant
----------------------------------

This represents a label variation for one or more new products. A label
variant represents a unique combination of one flavor variation, one
packaging variant, and one set of languages on the product label. It
represents the final item.

![](../../../../Resources/Images/Solution%20Enablement/PLM/DSLV.png)

For a label variant, some attributes that might be used are the
following:

+----------------------+----------------------+----------------------+
| Item Information     | Commercial Item      | Label Requirements   |
|                      | Information          |                      |
+======================+======================+======================+
| Unique Identifier    | Item Quantity Target | Label Requirement    |
| (product SKU, GTIN)  |                      | Type                 |
|                      | Item Cost Target     |                      |
|                      |                      | Requirement          |
|                      | Item Suggested       | Description          |
|                      | Retail Target        |                      |
|                      |                      | Requirement Valid    |
|                      | Item Revenue Target  | For                  |
|                      |                      |                      |
|                      | Item Gross Margin    | Help Text            |
|                      | (%) Target           |                      |
|                      |                      | Sort Order           |
+----------------------+----------------------+----------------------+
