---
description: 'A Product is an item that you, the Retailer, buys from a
  supplier and that you sell to a customer. In MDM terminology, it can
  be called a \''sell side product\'' or \''sell side item.\'' '
title: '\[%=Heading.AnyLevel%\]'
---

PMDM for Retail Products and Product Data
=========================================

A product is an item that you, the retailer, buys from a supplier, and
that you sell to a customer. In PMDM terminology, it can be called a
\'sell side product\' or \'sell side item.\'

![](../../../Resources/Images/PMDM%20for%20Retail/retailerBuysSells.png)

**Retailer Buys and Sells - Click to Play**

[ ]{.wistia_embed .wistia_async_uw0qzg1r3h .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:287px;position:relative;width:533px"}

The Product Content Management module of the PMDM for Retail module only
deals with the sell side products.

Various types of products should be considered:

-   **Products** are any of the items that you sell.

![](../../../Resources/Images/PMDM%20for%20Retail/typicalProducts.png)

-   **Variant products** are versions of a single product, such as a
    shirt that is available in a variety of sizes and colors (PCM only).

![](../../../Resources/Images/PMDM%20for%20Retail/variantProducts.png)

-   Other product types depend upon your data model as defined during
    your STEP implementation. For example:
-   Samples: items that are not sold but are distributed.
-   Kits: a repair kit that links to other products.
-   Packs: a group that contains a selection of other items.
-   Bundles: a set of products plus the installation service delivered
    by a specialist.

Buy Side and Sell Side
----------------------

It is common practice to make a distinction between products being
bought and products being sold as follows:

-   The \'buy side\' product is what you, the retailer, buys from a
    supplier.
-   The \'sell side\' product is what you, the retailer, sells to your
    customer.

![](../../../Resources/Images/PMDM%20for%20Retail/buySideSellSide.png)

Consider the following scenarios:

-   **The same product is bought and sold** - You buy a product and you
    sell the same product (PCM only).

![](../../../Resources/Images/PMDM%20for%20Retail/sameProductBoughtAndSold.png)

-   **Multiple products are sold as the same product** - You buy
    equivalent products from several suppliers and you sell them as the
    same product (VDO only).

[![](../../../Resources/Images/PMDM%20for%20Retail/multipleProductsSoldAsSame.png)]{style="color: #ff0000;"}

-   **Single product is sold as different products** - You buy one
    product from a supplier and you sell it as different products.

![](../../../Resources/Images/PMDM%20for%20Retail/productSoldAsDiff.png)

Product Data
------------

Often the terms \'product\' and \'product data\' are used
interchangeably. In PMDM, \'product\' refers to the item being bought
and sold, while \'product data\' is the supporting information about the
item being bought and sold.

Product data is any data that describes it: its name, identifiers (GTIN,
EAN, SKU id), product description (such as GPC attributes, marketing
texts), pictures, links to other products, link to a classification,
etc.

Data for a product is held by the following elements:

-   **Attributes** hold characteristics about the product. For more
    information, see the **Attributes** topic in the **System Setup /
    Super User Guide** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.
-   **References** hold links to other products, such as cross sell
    items, up-sell items, packs, etc. For more information, see the
    **Reference and Link Types** topic in the **System Setup / Super
    User Guide** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.
-   **Assets** are digital items such as images, specifications,
    instruction manuals, etc. For more information, see the **Digital
    Assets** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Product Hierarchy and Classification
------------------------------------

The primary product hierarchy is a type of classification used to manage
products and identify product families. For more information, see the
**Product Hierarchy** section of the **Products** topic in the **Getting
Started / User Guide** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

The product is classified in a unique location in the Primary Product
Hierarchy. GPC classification and Open classification are two types of
classification \'content\' that can be used, as defined below.

-   **GPC classification** allows the standard GPC attributes to be
    automatically attached to each relevant \'level\'.
-   **Open classification** allows you to manually define the attributes
    needed for each node of the classification.

The two possibilities of Product Hierarchy as implemented in Product
Content Management:

+----------------------------------+----------------------------------+
| ![](../../../Resources/Ima       | ![](../..                        |
| ges/PMDM%20for%20Retail/GS1.png) | /../Resources/Images/PMDM%20for% |
|                                  | 20Retail/openClassification.png) |
| Below is an example of populated |                                  |
| GPC hierarchy:                   | Below is the data structure:     |
|                                  |                                  |
| ![](../.                         | ![](                             |
| ./../Resources/Images/PMDM%20for | ../../../Resources/Images/PMDM%2 |
| %20Retail/GPCclassification.png) | 0for%20Retail/prodHierarchy.png) |
+----------------------------------+----------------------------------+

The two possibilities of Product Hierarchy as implemented in Vendor Data
Onboarding.

In the Vendor Data Onboarding Module, there is a primary product
hierarchy for the purchased products (referred to as "External Data
Source") and sold products (referred to as "Internal Data Source"). The
logic is the same, but there are two hierarchies instead of one.

 

+----------------------------------+----------------------------------+
| ![](../../../Resource            | ![](../../../Resources/Image     |
| s/Images/Solution%20Enablement/P | s/Solution%20Enablement/PMDM/PMD |
| MDM/PMDM%20For%20Retail/GS1.png) | M%20For%20Retail/Magnifying.png) |
|                                  |                                  |
| Below is an example of populated | Below is the overarching data    |
| GPC hierarchy.                   | structure.                       |
|                                  |                                  |
| The "External Data Source"       | For External Data Sources:       |
| hierarchy:                       |                                  |
|                                  | ![](../../                       |
| ![](../                          | ../Resources/Images/Solution%20E |
| ../../Resources/Images/Solution% | nablement/PMDM/PMDM%20For%20Reta |
| 20Enablement/PMDM/PMDM%20For%20R | il/ExtDataSourceOverarching.png) |
| etail/ExtDataSourceHierarcy.png) |                                  |
+----------------------------------+----------------------------------+
| The "Internal Data Source"       | For External Data Sources:       |
| hierarchy:                       |                                  |
|                                  | ![](../../../Resources/I         |
| ![](../../../Resources/          | mages/Solution%20Enablement/PMDM |
| Images/Solution%20Enablement/PMD | /PMDM%20For%20Retail/DSIDS1.png) |
| M/PMDM%20For%20Retail/DSIDS.png) |                                  |
+----------------------------------+----------------------------------+

 

Another classification type is the web classification, as illustrated in
the \'Web Hierarchy\' classification shown below. A common practice is
to use an \'alternate\' classification to export data to the E-commerce
platform.

In the example web classification, the bottle of wine product can be
placed at several locations, for instance, in the \'Wine and Spirits\'
folder, as well as in the \'Promotions\' folder.

![](../../../Resources/Images/PMDM%20for%20Retail/prodHierarchyWebClassification.png)

Product Distribution Channels
-----------------------------

The retailer can distribute its products in different ways:

-   **Directly** through its own shops (physical stores), online
    channels (site, app), distance selling (phone and mail, paper
    catalogs, TV shopping as showcases).
-   **Indirectly** through marketplaces such as Amazon, eBay, Walmart,
    Wayfair, BOL.com, CDiscount, PriceMinister, Google Shopping, Etsy,
    Facebook, etc.
-   **White label** for another brand. The retailer sells its own
    products, but with a different brand, operating this brand's
    channel.

Each of these \'channels\' can have different assortments. For example,
stores in one area will not have the same assortment as stores in
another area. The products available in a physical store may not be
available online (for instance, because home delivery is not possible),
and vice versa. There can also be online-only products.

Multichannel or omnichannel scenarios are common practice in retail. The
idea is to have a continuity of purchase experience through the
different channels. The most common example is \'click and collect\'
where you buy a product online and pick it up in a shop. Another
scenario is the other way around where you buy a product in a store and
it is delivered at home. This requires the capacity to manage product
data across these channels.

To cover these distribution needs, a common practice is to use one
\'alternate classification\' per channel, such as the \'Web Hierarchy\'
classification mentioned above. The retailer creates dedicated alternate
classifications for each of its channels.
