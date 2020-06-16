---
description: 'Products, as well as families and variants, can be created
  by an inbound integration endpoint (IIEP) \''Products Inbound
  (PMDM.IIEP.ProductsInbound)\'', connected to the ERP.'
title: '\[%=Heading.AnyLevel%\]'
---

\'Acquire\' Activity - Create Products via IIEP
===============================================

Products, as well as families and variants, can be created by an inbound
integration endpoint (IIEP) \'Products Inbound
(PMDM.IIEP.ProductsInbound)\', connected to the ERP.

![](../../../Resources/Images/PMDM%20for%20Retail/productCreationViaIIEP.png)

-   The ERP creates product data with a few pieces of key information,
    one of them being the \'SKU.\' The ERP generates a STEPXML file and
    saves it in a hotfolder.
-   STEP automatically imports the STEPXML file and creates and/or
    updates products.
-   The products created already have a SKU assigned by the ERP and are
    initiated into the \'Product Creation Workflow.\'

For more information, see the **Creating an Inbound Integration
Endpoint** topic in the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.
