---
description: 'Within the Product Content Management module, the
  \''acquire\'' activity is performed by the buyer working with the sell
  side. '
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Acquire\' Activity
===============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMAcquire.png)

Within the Product Content Management module, the \'acquire\' activity
is performed by the buyer working with the sell side products.

Product data can be created via the following activities and is defined
below:

-   In STEP Web UI by the retailer.
-   With an Excel Smartsheet by the retailer.
-   From the ERP via an inbound integration endpoint (IIEP).

Regardless of the method used to create product data, a unique Product
Creation Workflow is executed. Among other things, the workflow
communicates with the ERP and performs the following tasks (see the
**PMDM and an ERP** section of the **Product Data Lifecycle** topic
([here]{.mcFormatColor style="color: Blue;"})):

-   Requests the SKU ID from the ERP: a common scenario in retail is
    that the ERP holds SKU identifiers. This logic is included in the
    process.
-   Automatically classifies the product: implements the \'manage\'
    activity, which consists of dispatching the enrichment and review
    activities of the team.

The topics that describe the \'acquire\' activity include:

-   \'Acquire\' Activity - Common STEP Workflow ([here]{.mcFormatColor
    style="color: Blue;"})
-   \'Acquire\' Activity - Create Products in Web UI
    ([here]{.mcFormatColor style="color: Blue;"})
-   \'Acquire\' Activity - Create Products via Excel Smartsheet
    ([here]{.mcFormatColor style="color: Blue;"})
-   \'Acquire\' Activity - Create Products via IIEP
    ([here]{.mcFormatColor style="color: Blue;"})
