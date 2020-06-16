---
description: 'Configuration of the Product Content Management business
  module is largely handled automatically upon installation. This topic
  provides high-level information only, including how to access the
  module on your system.'
title: '\[%=Heading.AnyLevel%\]'
---

Module - Vendor Data Onboarding
===============================

The Vendor Data Onboarding allows for multiple supplier-side products
for one retailer-side product (buy-side, sell-side). In this
configuration, the Suppliers onboard their data (while in the "Product
Content Management" module, the Retailer was onboarding the Product
Data). A distinction is made between the product data coming from the
suppliers (which may vary from one supplier to the other) and the
product data as maintained by the retailer.

![](../../../Resources/Images/PMDM%20for%20Retail/multipleProductsSoldAsSame.png)

The Source Records (or purchased product and sold product, or buy-side / sell side and other expressions)
---------------------------------------------------------------------------------------------------------

While you may know about \'buy-side product,\' \'supplier product,\' and
\'vendor product,\' a more generic naming is relevant. Product data can
come from a supplier, but it can also come from a content provider (such
as GDSN, Salsify, etc.), so the term \'source record\' is used.

There are three types of Product Data, or "Source Records".

+----------------------+----------------------+----------------------+
| Object               | Also known as        | Definition           |
+======================+======================+======================+
| External Source      | Buy-side product,    | An External Source   |
| Record               | supplier product,    | record is a Product  |
|                      | purchased product    | data object coming   |
|                      |                      | from a supplier, who |
|                      |                      | would like the       |
|                      |                      | Retailer to buy its  |
|                      |                      | product, of from a   |
|                      |                      | product data         |
|                      |                      | provider (GDSN,      |
|                      |                      | etc.), which         |
|                      |                      | contains quality     |
|                      |                      | data on products.    |
|                      |                      | They are external to |
|                      |                      | the retailer.        |
+----------------------+----------------------+----------------------+
| Internal Source      | Silver record,       | Mixing the data      |
| Record               | sell-side product,   | provided by the      |
|                      | sold product         | supplier and present |
|                      |                      | it directly to the   |
|                      |                      | consumer is often    |
|                      |                      | not enough. The      |
|                      |                      | Retailer needs       |
|                      |                      | specific data to     |
|                      |                      | make its product     |
|                      |                      | sell very well. This |
|                      |                      | could be for         |
|                      |                      | instance: a powerful |
|                      |                      | marketing text to    |
|                      |                      | tempt the consumer,  |
|                      |                      | an impactful         |
|                      |                      | picture, convincing  |
|                      |                      | argument explaining  |
|                      |                      | why it is best to    |
|                      |                      | buy it from the      |
|                      |                      | Retailer and not     |
|                      |                      | from a competitor,   |
|                      |                      | etc.                 |
|                      |                      |                      |
|                      |                      | The Internal Source  |
|                      |                      | Record is a Product  |
|                      |                      | data object on the   |
|                      |                      | retailer side        |
|                      |                      | containing           |
|                      |                      | retailer-specific    |
|                      |                      | data which will also |
|                      |                      | be promoted to the   |
|                      |                      | Golden Record.       |
+----------------------+----------------------+----------------------+
| Golden Record        |                      | When there are       |
|                      |                      | several data sources |
|                      |                      | for the same         |
|                      |                      | Product, it is       |
|                      |                      | indispensible to     |
|                      |                      | take the best of the |
|                      |                      | data and aggregate   |
|                      |                      | them into a          |
|                      |                      | read-only object:    |
|                      |                      | this is the role of  |
|                      |                      | the Golden Record.   |
|                      |                      |                      |
|                      |                      | It is the source of  |
|                      |                      | truth for product    |
|                      |                      | data that mixes the  |
|                      |                      | most relevant data   |
|                      |                      | from the external    |
|                      |                      | and internal         |
|                      |                      | sources.             |
|                      |                      |                      |
|                      |                      | -   Contains both    |
|                      |                      |     buy-side and     |
|                      |                      |     sell-side data.  |
|                      |                      | -   Published to the |
|                      |                      |     sales channels.  |
+----------------------+----------------------+----------------------+

A quick look at the Onboarding Process
--------------------------------------

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/QuickLookOnboardingProcess.png)

The process will be detailed in the next sections.
