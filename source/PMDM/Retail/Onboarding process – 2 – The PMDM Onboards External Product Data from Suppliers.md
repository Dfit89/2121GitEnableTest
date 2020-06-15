---
description: The product data received from the Supplier via PDS or
  subscribed to and received from GDSN is being created in PMDM for
  Retail as a separate product object of the type External Source Record
  in the External Product Hierarchy and optionally separate packaging
  objects in the External Packaging hierarchy.
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 2 -- The PMDM Onboards External Product Data from Suppliers
=================================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess2.png)

The product data received from the Supplier via PDS or subscribed to and
received from GDSN is being created in PMDM for Retail as a separate
product object of the type External Source Record in the External
Product Hierarchy and optionally separate packaging objects in the
External Packaging hierarchy. As part of the creation, the External
Source Record is being initiated in the External Source Record Handling
workflow which will guide the External Source Record through the
different states of the onboarding process.

The External Source Record is being linked to a Supplier classification
to keep track of the products delivered per Suppliers. If product data
for the same product is being received by multiple Suppliers or Content
Providers they will be created as separate External Source Records, each
linked to the relevant supplier.

The data on the External Source Record is owned by the Supplier and it
will not be maintained by the retailer.
