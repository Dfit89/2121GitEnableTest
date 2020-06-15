---
description: 'Product data is crucial for your business. To sell
  efficiently, product data needs to be accurate. To sell fast, product
  data must be available, centralized, and controlled. With the Product
  Content Management module, the retailer can govern, acquire, manage,
  and share product data directly into Stibo Systems\'' MDM.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Data Lifecycle
======================

Product data is crucial for your business. To sell efficiently, product
data needs to be accurate. To sell fast, product data must be available,
centralized, and controlled. With the **Product Content
Management** module, the retailer can add, enrich, maintain, and publish
product data directly into Stibo Systems\' MDM.

With the **Vendor Data Onboarding** module, the suppliers will submit
their product data directly to the retailer using Product Data
Syndication or PDS.

Siloed, duplicated, and inaccurate product information has a strong
competitive business impact on any retail business: impersonal
experiences, higher product return rate, low up-sell / cross-sell
conversion. Agile and fast decisions are key to support customer-centric
brand experiences.

Managing accurate, up-to-date product information enables you to
increase up-sell / cross-sell and to reduce the returns rate. You also
gain the insight to manage products with complex hierarchies and
attributes, and to fuel customers\' engagement with products, create
customer retention, and drive more sales.

PMDM for Retail allows organizations
to acquire, manage, and share product data from a variety of internal
and external systems with their customers and value chain partners. The
Product Content Management module implements this logic using a typical
business process which covers the scenarios frequently encountered.

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMLifeCycle.png)

Both the Product Content Management module and the Vendor Data
Onboarding module include these activities:

-   **Govern** - maintain key elements of the data model like
    attributes, LOVs, and mappings ([here]{.mcFormatColor
    style="color: Blue;"})
-   **Acquire** - add or import product data into the MDM
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Manage** - enrich the product data: copyright, digital assets, and
    warehouse data ([here]{.mcFormatColor style="color: Blue;"})
-   **Share** - export product data for users or external systems
    ([here]{.mcFormatColor style="color: Blue;"})

The Data Lifecycle for PCM and VDO will be presented in their own
sections.

PRODOC note: JOPI: The following H3 is a video that can be played in
online help. The two icons displayed are scripts.

[ ]{.wistia_embed .wistia_async_mm6osjlaj6 .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:300px;position:relative;width:533px"}

PMDM and an ERP
---------------

Frequently, STEP and an ERP (enterprise resource planning) software
communicate to manage:

**Attribution of a unique identifier by the ERP** - The ERP holds the
product identifier, also called \'SKU ID.\' When a product is created in
STEP directly, STEP requires an ID from the ERP.

![](../../../Resources/Images/PMDM%20for%20Retail/PDF_PMDMandERP.png)

Request SKU ID - Click to Play

**Mapping of the ERP classification with the one of the PMDM
classifications** - PMDM and the ERP have specific product
classifications that can differ from one another. A \'mapping\'
describes the classifications in PMDM that are equivalent to the ones in
the ERP. This mapping is maintained by the data steward, during the
\'govern\' activity.

![](../../../Resources/Images/PMDM%20for%20Retail/ERP-MDMClassification.png)

**Mapping between ERP and PMDM - Click to Play**

[ ]{.wistia_embed .wistia_async_zvnegy0isj .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:281px;position:relative;width:533px"}

A mapping identifies a relationship between the following two
attributes:

-   \'ERP Product Classification (PMDM.AT.ERPLine)\' attribute sent by
    the ERP.
-   \'ExternalIdentifier (ExternalIdentifier)\' attribute on the primary
    product hierarchy node to which the product must be attached.

This mapping is maintained in the \'ERP To PMDM Mapping
(PMDM.LUT.ERPToPMDMMapping)\' lookup table.
