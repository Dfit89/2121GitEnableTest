---
description: 'Regardless of the method used to add a product (in the Web
  UI, Excel Smartsheet, or IIEP), a single STEP workflow handles the
  business processes defined in this topic.'
title: '\[%=Heading.AnyLevel%\]'
---

\'Acquire\' Activity - Common STEP Workflow
===========================================

Regardless of the method used to add a product---in the Web UI
([here]{.mcFormatColor style="color: Blue;"}), Excel Smartsheet
([here]{.mcFormatColor style="color: Blue;"}), or IIEP
([here]{.mcFormatColor style="color: Blue;"})---a single STEP workflow
handles the business processes in the red frame below.

For more information, see the **Workflows** documentation[
here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/PMDM%20for%20Retail/commonSTEPWorkflow.png)

### Workflow Status Flag

In a specific state, the product can be in two statuses: \'Normal\' or
\'High.\' When a product enters the workflow, the status is set to
\'Normal.\' When a product is \'rejected\' by the QA group, the status
becomes \'High.\'

### SKU ID

The SKU ID is the identifier sent by the ERP for a specific product.
When the product is created by the ERP, it is assumed that it has a SKU
ID, in PMDM this attribute is \'SKU (PMDM.AT.SKU)\'.

### ERP Product Classification

Mapping identifies a relationship between the ERP and PMDM for the
following two attributes:

-   \'ERP Product Classification (PMDM.AT.ERPLine)\' attribute sent by
    the ERP.
-   \'ExternalIdentifier (ExternalIdentifier)\' attribute on the primary
    product hierarchy node to which the product must be attached.

This mapping is maintained in the \'ERP To PMDM Mapping
(PMDM.LUT.ERPToPMDMMapping)\' lookup table.
