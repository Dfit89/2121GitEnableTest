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

---
description: The retailer uses the Web UI to add one or more new
  products in PMDM.
title: '\[%=Heading.AnyLevel%\]'
---

\'Acquire\' Activity - Create Products in Web UI
================================================

The retailer uses the Web UI to add one or more new products in PMDM.

The methods available for adding new product using the Web UI include:

-   Create a single product
-   Create multiple products
-   Create families and variants

Each is defined in the sections below.

Create a Single Product
-----------------------

  -------------------------------------------------------------- ----------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/buyer.png)   The buyer performs all steps to create a single product.
  -------------------------------------------------------------- ----------------------------------------------------------

1.  On the \'Product Creation Workflow\' homepage widget click the
    **Initialize** link and click the **Initiate Product** link.

![](../../../Resources/Images/PMDM%20for%20Retail/singleProductInitiate.png)

**Initiate product - Click to Play**

[ ]{.wistia_embed .wistia_async_z9zluxxuvd .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:300px;position:relative;width:533px"}

1.  Supply the necessary information and click the **Create** button.

![](../../../Resources/Images/PMDM%20for%20Retail/singleProductCreateButton.png)

1.  Choose a method to categorize the product:

-   Manually - Click the **Categorize Manually** button if the product
    is not already categorized in the Product Primary Hierarchy.
-   Automatically - First select an \'ERP Product Category\' from the
    dropdown and then click the **Categorize Automatically** button to
    align ERP Product Categorization and the PMDM Product
    Categorization.

![](../../../Resources/Images/PMDM%20for%20Retail/singleProductCategorizeAutoMan.png)

1.  If desired, continue in the workflow and assign the task by clicking
    the **Assign to Me** or the **Assign to Group** option and then
    clicking the **Proceed** button. The product task can be worked.
2.  Continue with the **Product Content Management \'Manage\' Activity**
    topic[ here]{.mcFormatColor style="color: Blue;"}.

Create Multiple Products
------------------------

  -------------------------------------------------------------- -----------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/buyer.png)   The buyer performs all steps to create multiple products.
  -------------------------------------------------------------- -----------------------------------------------------------

1.  On the homepage \'Mass Creation\' widget, choose a method to
    identify the node under which the products will be created:

-   Type a node into the text box.
-   Click the hierarchy button to display the Select Nodes dialog. Use
    the Browse or Search option, select the node and click the **OK**
    button.

![](../../../Resources/Images/PMDM%20for%20Retail/multipleProductsCreate.png)

1.  Click the **Insert new line** button and add the necessary
    information on the new row inserted.

Repeat this step until all new products are displayed.

![](../../../Resources/Images/PMDM%20for%20Retail/multipleProductsInsert.png)

1.  Click the **Create** button.
2.  Continue with the **Product Content Management \'Manage\' Activity**
    topic[ here]{.mcFormatColor style="color: Blue;"}.

Create Families and Variants
----------------------------

+----------------------------------+----------------------------------+
| ![](../../../Resources/Image     | The buyer performs all steps to  |
| s/PMDM%20for%20Retail/buyer.png) | create families and variants.    |
|                                  |                                  |
|                                  | In PMDM for Retail, a            |
|                                  | \'variant\' is a product which   |
|                                  | has a \'family\' for parent. The |
|                                  | buyer must first create a family |
|                                  | and then create as many variants |
|                                  | as necessary.                    |
|                                  |                                  |
|                                  | PMDM for Retail includes generic |
|                                  | \'Size (PMDM.AT.Size)\' and      |
|                                  | \'Color (PMDM.AT.Color)\'        |
|                                  | attributes for variants. If GS1  |
|                                  | also has \'size\' and \'color\'  |
|                                  | specific data, it can be complex |
|                                  | to implement. The use of generic |
|                                  | \'size\' and \'color\'           |
|                                  | attributes is commonly           |
|                                  | encountered.                     |
+----------------------------------+----------------------------------+

1.  On the homepage \'Product Creation Workflow\' widget, click the
    **Initialize** link and click the **Initiate Product Family** link.

![](../../../Resources/Images/PMDM%20for%20Retail/variantInitiateFamily.png)

1.  Add a name, select a parent node, add a family description, and
    click the **Create** button.

![](../../../Resources/Images/PMDM%20for%20Retail/variantCreateFamily.png)

1.  Create variants using one of the following methods:

-   On the **To Do** tab, click the **Create Variants** button to
    display the Create Variants dialog. This method is similar to the
    steps described above in the **Create a single product** section.

![](../../../Resources/Images/PMDM%20for%20Retail/variantCreateVariants.png)

On the \'Create variants\' dialog, add the variant information and click
the **OK** button.

![](../../../Resources/Images/PMDM%20for%20Retail/variantCreateVariantsDialog.png)

-   Select a family from the Tree, then click the **Create variants**
    button to create the variants.

![](../../../Resources/Images/PMDM%20for%20Retail/variantCreateVariantsTab.png)

On the \'Create variants\' dialog, add the variant information and click
the **OK** button.

![](../../../Resources/Images/PMDM%20for%20Retail/variantCreateVariantsDialog.png)

---
description: ' Excel is often a vital part of an organization. For
  example, the retailer can export an Excel Smartsheet from STEP and
  send it by email to a supplier. The supplier updates the Excel
  Smartsheet and returns it to the retailer. The retailer validates the
  data using the built-in STEP validation feature of the Excel
  Smartsheet format, and imports it into STEP. '
title: '\[%=Heading.AnyLevel%\]'
---

\'Acquire\' Activity - Create Products via Excel Smartsheet
===========================================================

Excel is often a vital part of an organization. For example, the
retailer can export an Excel Smartsheet from STEP and send it by email
to a supplier. The supplier updates the Excel Smartsheet and returns it
to the retailer. The retailer validates the data using the built-in STEP
validation feature of the Excel Smartsheet format, and imports it into
STEP. For more information, see the **Excel Smartsheet Format** topic in
the **Data Exchange** documentation[ here]{.mcFormatColor
style="color: Blue;"}[[.]{style="color: #000000;"}]{style="color: #ff0000;"}

  ----------------------------------------------------------------------- ---------------------------------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/buyer.png)            The buyer performs most of the steps to create products using Excel Smartsheet.
  ![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetuser.png)   The Smartsheet user supplies data for the Excel Smartsheet.
  ----------------------------------------------------------------------- ---------------------------------------------------------------------------------

1.  On the homepage \'Work With Smartsheets\' widget, click the
    **Download Smartsheet** link.[ ]{style="color: #ff0000;"}

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetDownload.png)

1.  Select the appropriate widget to create products or families /
    variants, select a node, and export the Smartsheet.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetWidgets.png)

1.  On the Background Process Details page, click the background process
    link to download the Smartsheet.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetBGP.png)

1.  Send the downloaded Excel Smartsheet to the Smartsheet user to
    complete, validate, and return to the buyer.
2.  On the homepage, click the **Import Smartsheet** link.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetImport.png)

1.  A background process is initiated as shown in a notification like
    the one below.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetBGPNotification.png)

1.  The background process is reported.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetBGPprocess.png)

1.  Products are initiated into the \'Product Creation Workflow\' as
    reported in the notifications panel.

![](../../../Resources/Images/PMDM%20for%20Retail/smartsheetNotificationPanel.png)

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

---
description: The Vendor Data Onboarding configuration includes a
  collaboration workflow which works in the same way as in the Product
  Content Management Module.
title: '\[%=Heading.Level1%\]'
---

Collaboration Workflow
======================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/collabWorkflow.png)

The Vendor Data Onboarding configuration includes a collaboration
workflow which works in the same way as in the Product Content
Management Module.

The workflow uses the objects introduced in this module: Internal Source
Record, External Source Record, Golden Record.

With this workflow, the retailer's team can collaborate around product
data. This is an internal communication feature, which cannot include
external suppliers, using different systems.

For PDS, a communication channel is included in the onboarding workflow
to handle when the retailer accepts a supplier's product, rejects it, or
asks the supplier to have it reworked.

---
description: Configuration of the Product Content Management business
  module is handled using configuration files.
title: '\[%=Heading.AnyLevel%\]'
---

Initial Setup for Product Content Management Module
===================================================

To access the Product Content Management business module, the following
licenses must be enabled. Contact your account manager to enable
licenses for your system.

-   X.App.ProductVariants
-   X.Smartsheet

Contact your Stibo Systems account manager or partner manager for
information on installing PMDM for Retail using configuration files.

Prerequisites and Considerations
--------------------------------

The following prerequisites and considerations apply to using the
Product Content Management business module:

-   The Product Content Management business module deals with sell-side
    products only.
-   Users must be granted the \'Install Business Modules\' setup action
    to install business modules.
-   The module should only be installed on clean systems. If data
    structures already exist in the target system (e.g., product or
    classification hierarchy), or standard STEP base objects have been
    removed, it is not guaranteed that the module can be successfully
    installed.
-   If any of the steps within a business module fail during
    installation, the installation may not fully complete, though as
    much data will be imported as possible.
-   The minimum required baseline for the module is version 9.2-mp3.

---
description: 'Configuration of the Product Content Management business
  module is largely handled automatically upon installation. This topic
  provides high-level information only, including how to access the
  module on your system.'
title: '\[%=Heading.Level1%\]'
---

Module - GDSN Receiver for PMDM for Retail
==========================================

![](../../../Resources/Images/PMDM%20for%20Retail/GDSNReceiver.png)

The GDSN Receiver module is installed on top of the Vendor Data
Onboarding module. With it, the Retailer can receive quality Product
Data from GS1.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/GS1Pallet.png)

GS1 GDSN is an automated, standards-based global environment that
enables secure and continuous data synchronization, allowing all trading
partners to have consistent item data in their systems at the same time.

The GS1 Global Data Synchronization Network connects retailers and
suppliers via their selected GDSN-certified data pools to the GS1 Global
Registry.

To benefit from GS1 GDSN in PMDM for Retail, an external STEP system
with the GDSN Receiver can be set up using a preconfigured solution.

GDSN Receiver Solution
----------------------

The GDSN Receiver solution includes the following elements:

-   Installable solution which is separate from the MDM and on its own
    release cycle
-   Prebuilt GS1 attributes, code lists, Units of Measure (UoMs), and
    GPC hierarchy
-   Full attribute mapping for inbound CINs
-   Web UI for managing GDSN admin tasks
-   Built-in workflows to manage messaging, MDM data flow, and Hierarchy
    Withdrawals
-   Framework for automating the Catalogue Item Confirmation (CIC)
    response
-   Completeness Rules that can be maintained by non-technical users
-   GPC Validations that can be maintained by non-technical users
-   Framework to add custom API calls, custom JavaScript, etc. for more
    complex rules
-   Framework for transforming GDSN data model to match downstream
    systems
-   Transformation tables for attribute IDs, LOVs, object types,
    reference types, and unit descriptors
-   XSLT post-processor

GDSN Receiver Architecture
--------------------------

The following diagram shows the relationship and interaction between
GDSN and PMDM for Retail.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/GDSN%20RECEIVER%20ARCHITECT.png)

---
description: 'As Product Master Data Management (PMDM) multi-domain
  specialists, we have studied customers\'' business processes and
  configurations. We have identified patterns that frequently occur in
  the retail industry. The big picture of \''PMDM for Retail\'' is focused
  on data, and as the \''source of truth\'' for data, MDM is at the heart
  of data governance.'
title: '\[%=Heading.AnyLevel%\]'
---

Module - Product Content Management
===================================

Configuration of the Product Content Management module is handled using
configuration files as defined in the **Initial Setup for Product
Content Management Module**[ here]{.mcFormatColor style="color: Blue;"}.

The following topics explain the activities managed by the \'Product
Content Management\' module included in PMDM for Retail as displayed in
the image above:

-   Product Content Management \'Govern\' Activity[
    ([here]{.mcFormatColor
    style="color: Blue;"})]{style="color: #ff0000;"}
-   Product Content Management \'Acquire\' Activity
    ([here]{.mcFormatColor style="color: Blue;"})
-   Product Content Management \'Manage\' Activity
    ([here]{.mcFormatColor style="color: Blue;"})
-   Product Content Management \'Share\' Activity ([here]{.mcFormatColor
    style="color: Blue;"})

Product Data Lifecycle in PCM
-----------------------------

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PDLinPCM.png)

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

---
description: 'Using PDS, the vendor will onboard and submit their
  product information to the Retailer. The following is a typical
  process followed by the vendor.'
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 1a --The Supplier Manages and Publishes Product Data
==========================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess1A.png)

Using PDS, the vendor will onboard and submit their product information
to the Retailer. The following is a typical process followed by the
vendor.

-   **Import Data**: Vendors can upload product data and assets either
    from Excel or using PDS' APIs to integrate with their internal
    systems.

-   **Master Data**: Vendors can view, and when required, manage
    imported product data and digital assets.

-   **Categorization**: Vendors will manually select or create
    automation rules to map products to retailer categories.

-   **Mapping and Validation**: To ensure they meet the Retailer's
    requirements, the vendor will map their master data attributes to
    the retailer specific attributes, viewing any error messages, and
    using attribute value transformations or data edits to resolve
    errors.

-   **Process Management**: From product onboarding and maintenance to
    viewing and responding to reject and return reasons, vendors can use
    PDS to manage the end-to-end process of syndicating their product
    information to the retailer.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess1A.png)

Using PDS, the vendor will onboard and submit their product information
to the Retailer. The following is a typical process followed by the
vendor.

-   **Import Data**: Vendors can upload product data and assets either
    from Excel or using PDS' APIs to integrate with their internal
    systems.

-   **Master Data**: Vendors can view, and when required, manage
    imported product data and digital assets.

-   **Categorization**: Vendors will manually select or create
    automation rules to map products to retailer categories.

-   **Mapping and Validation**: To ensure they meet the Retailer's
    requirements, the vendor will map their master data attributes to
    the retailer specific attributes, viewing any error messages, and
    using attribute value transformations or data edits to resolve
    errors.

-   **Process Management**: From product onboarding and maintenance to
    viewing and responding to reject and return reasons, vendors can use
    PDS to manage the end-to-end process of syndicating their product
    information to the retailer.

---
description: Product Data can be onboarded from GS1. This ensures a very
  high data quality. GS1 data is collected in a separate STEP instance
  with a GDSN receiver.
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 1b -- The PMDM Onboards External Product Data from GDSN
=============================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/DataFromGS1.png)

Product Data can be onboarded from GS1. This ensures a very high data
quality. GS1 data is collected in a separate STEP instance with a GDSN
receiver.

For more details, see the topic **Module - GDSN Receiver for PMDM for
Retail**[]{.mcFormatColor style="color: Blue;"}here.

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

---
description: 'When a new External Source Record has been created in PMDM
  for Retail and initiated in the External Source Record Handling
  workflow, the workflow checks if the specific Supplier is configured
  to allow for automatic approval of proposed products or if it has to
  go through a manual process where the Buyer has to manually decide if
  we want to onboard the product.'
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 3 -- The Buyer Accepts or Rejects the Supplier's Product Proposal
=======================================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess3.png)

When a new External Source Record has been created in PMDM for Retail
and initiated in the External Source Record Handling workflow, the
workflow checks if the specific Supplier is configured to allow for
automatic approval of proposed products or if it has to go through a
manual process where the Buyer has to manually decide if we want to
onboard the product.

On the homepage, in the "External Record Handling" widget, the buyer
will see the number of External Source Records concerned.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/Homepage.png)

In the manual proposal approval process the buyer has the option to
approve the product data and continue with the onboarding of the
product, send it back to the Supplier for rework in case the supplied
data is wrong or incomplete or reject the product for onboarding in case
the Retailer do not want to onboarding and sell the product.

On the Product Page, the Buyer will make his choice:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PropStatus%20approve.png)

Onboarding Process -- 4 -- The PMDM Aggregates the Data in a Golden Record
==========================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/SourceRecorded.png)

When the External Source Record is approved for further onboarding in
the External Source Record Handling workflow it automatically gets
approved and is send for Matching and Linking.

The Matching and Linking process first creates a match code for the
External Source Record which is used to check if there is already an
existing Product with the same match code in the system. Per default,
the match code is the GTIN of the Product.

It no existing Product with the GTIN is found then the system creates a
new Golden Record and an Internal Source Record for this Product. The
Internal Source Record is used by the Retailer to enrich the Product and
will contain the Retailers own product data like web descriptions, data
from the ERP system etc. If the External Source Record causing the
Matching and Linking process to be executed has corresponding external
packaging objects, then they will be duplicated to internal packaging
objects which will be linked to the created Internal Source Record.

If there is already a Product with the same GTIN then there is a match
and the External Source Record will be linked to the existing Golden
Record.

As part of the process data from all linked sources (External and
Internal Source Records) will be promoted to the Golden Record using a
set of survivorship rules which is defined on the Products matching
algorithm.

---
description: 'The product data for a new Product needs to be enriched
  internally by the Retailer before it will be ready to go out for
  downstream systems and be sold. To support this process, the Internal
  Source Record Creation workflow is initiated when a new Golden Record
  and Internal Source Record are created.'
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 5 -- The Retailer Adds Sell-Side Specific Data
====================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/RetailerExpert.png)

The product data for a new Product needs to be enriched internally by
the Retailer before it will be ready to go out for downstream systems
and be sold. To support this process, the Internal Source Record
Creation workflow is initiated when a new Golden Record and Internal
Source Record are created.

First, a task is assigned to the Buyer Group to allow a Buyer to enrich
and maintain the Buyer relevant part of the product data.

The Buyer Review task is visible on the homepage, in the "Internal
Record Creation" widget:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/InternalRecord.png)

Only the tasks that are relevant to users will be visible to them.

The **Buyer** can also decide if the product should be sent for further
enrichment by the **Marketing Specialists**, the **Image Specialists**
and/or the **Warehouse Specialists** or if it should be sent directly to
final review by the Quality Assurance Experts. If the Product is sent
for further enrichment by Marketing, Image and/or Warehouse they will be
able to do their enrichment in parallel.

The enrichment tasks are visible on the home page, in the "Internal
Record Creation" workflow widget.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCBuyerReview.png)

 

**Alternative**: In smaller organizations, the Enrichment Specialist can
accumulate the work of the Marketing Specialist, the Image Specialist,
the Warehouse Specialist.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/Alternative.png)

This option is visible in the Workflow widget, as the "Enrichment
Review" task.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCBuyerCopy.png)

When all enrichment tasks are done, the Product is assigned to the
Quality Assurance Experts. They have the final saying if all product
data is correct and can be approved. If the Quality Assurance Expert
finds something that needs to be corrected, they have the option to
reject the Product to the Buyer, Marketing, Image, or Warehouse Group
for rework.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCProduct.png)

---
description: When the Product has been approved by the Quality Assurance
  Expert the Internal Source Record Creation workflow is sending the
  Product to the Matching and Linking process again to promote the
  latest set of data from the linked sources to the Golden Record.
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 6 -- The MDM Checks that the Data is Okay to be Presented to Other Systems
================================================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/MDM.png)

When the Product has been approved by the **Quality Assurance Expert**
the Internal Source Record Creation workflow is sending the Product to
the **Matching and Linking** process again to promote the latest set of
data from the linked sources to the Golden Record. When the data has
been promoted, the Product is initiated in the **Golden Record Gating
workflow** which will validate the Golden Record against a set of
validation rules to see if the Golden Record is ready to be Published.

The Golden Record Gating workflow first runs the Product though a common
validation (validation gate) to check for e.g. attribute values that are
mandatory across all channels. If passed, it will continue with channel
specific validation in parallel to check if specific validation rules
for ERP and E-commerce are fulfilled.

If one or more validation errors are found, then the Product will be
sent to a gating specific "Handle Error" state in the **Handle Gating
Error workflow** and a task will be assigned to the **Quality Assurance
Expert**. When the product data has been corrected and the Quality
Assurance Expert has proceeded the task, the process is executed again
to check if the validation is now fulfilled.

If all general validation rules and the ERP specific validation rules
are fulfilled, then Publish to ERP will be set to Yes on the Golden
Record.

If all general validation rules and the E-commerce specific validation
rules are fulfilled, then Publish to E-commerce will be set to Yes on
the Golden Record.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontGate.png)

The tasks related to Gating Errors can be found on the homepage, in the
"Handle Gating Error" widget.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/HandleGatingError.png)

The errors are displayed at the bottom of the Product Page, like this:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontGatErrors.png)

Validation rules for gating process

During the Matching and Linking process the Golden Record is initiated
in the Golden Record Gating workflow which will check if the Product it
is ready to be send out to the ERP system and/or the E-commerce
platform.

First the Golden Record will go to a common validation state (Front
Gate) where it will be checked for mandatory attribute values, mandatory
references etc. This check is being handled by the "Front Gate" business
rule.

Per default, the business rule checks the following:

-   The Golden Record has a value for all attributes linked into the
    "Front Gate: Mandatory Attributes" attribute group.

-   The Golden Record has at least one existing reference per reference
    type linked into the "Front Gate: Mandatory References" attribute
    group.

Each reference type must be linked into a separate sub attribute group
below "Front Gate: Mandatory References".

If attributes are linked into the sub attribute group together with the
reference type, then these attributes will be considered mandatory
meta-data attribute on the reference.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontaGate.png)

If one or more validate errors are found, then the Internal Source
Record will be forwarded to the "Handle Front Gating Error" state in the
Handle Gating Error workflow.

If the Front Gate is passed, then the Golden Record will continue with
the channel specific validation states (ERP Gate and E-commerce Gate).
Each of the two states are similar to the Front Gate.

**ERP Gate**

-   Business rule used: ERP Gate
-   Attribute Group for mandatory attributes: ERP Gate: Mandatory
    Attributes
-   Attribute Group for mandatory references: ERP Gate: Mandatory
    References
-   Attribute containing ERP Gate errors: ERP Gate: Errors
-   State the Internal Source Record will be forwarded to on errors:
    Handle ERP Gating Error

If the ERP Gate is passed, then the "Publish To ERP" attribute is set to
Yes on the Golden Record and the Golden Record is exported to the ERP
system using the "Products Outbound -- ERP\" outbound integration
endpoint.

E-commerce Gate

-   Business rule used: E-commerce Gate
-   Attribute Group for mandatory attributes: E-commerce Gate: Mandatory
    Attributes
-   Attribute Group for mandatory references: E-commerce Gate: Mandatory
    References
-   Attribute containing E-commerce Gate errors: E-commerce Gate: Errors
-   State the Internal Source Record will be forwarded to on errors:
    Handle E-commerce Gating Error

If the E-commerce Gate is passed, then the "Publish To E-commerce"
attribute is set to Yes on the Golden Record and the Golden Record is
exported to the E-commerce system using the "Products Outbound -
E-commerce\" outbound integration endpoint.

---
description: 'When the Golden Record has passed the validation for ERP
  then the Golden Record is sent to the "Products Outbound -- ERP\"
  Outbound Integration Endpoint and the corresponding Internal Source
  Record is initiated in the ERP Communication workflow which is used to
  handle the 2-ways communication with the ERP system.'
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 7 -- The PMDM Communicates with the ERP
=============================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/ERPOnboarding7.png)

When the Golden Record has passed the validation for ERP then the Golden
Record is sent to the "Products Outbound -- ERP\" Outbound Integration
Endpoint and the corresponding Internal Source Record is initiated in
the ERP Communication workflow which is used to handle the 2-ways
communication with the ERP system.

The export will be in STEPXML format and will contain the Golden Record,
all linked Source Records (Internal and External) plus all packaging
objects linked from the sources.

---
description: 'When the Golden Record has passed the validation for
  E-commerce then the Golden Record is sent to the "Products Outbound -
  E-commerce\" Outbound Integration Endpoint. '
title: '\[%=Heading.Level1%\]'
---

Onboarding Process -- 8 -- The PMDM Sends Product Data to the E-commerce Platform E-Commerce
============================================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/GoldenRecord.png)

When the Golden Record has passed the validation for E-commerce then the
Golden Record is sent to the "Products Outbound - E-commerce\" Outbound
Integration Endpoint.

The export will be in STEPXML format and will contain the Golden Record,
the assets referenced from the Golden Record and the Web Hierarchies
where the Golden Record is linked.

---
description: 'PMDM for Retail is a solution that manages product data
  across your company. But who actually creates, enriches, and
  classifies this product data? Even if the answer varies for each
  organization, the following standard actors are typically involved in
  Master Data Management.'
title: '\[%=Heading.AnyLevel%\]'
---

PMDM for Retail Key Concepts
============================

PMDM for Retail is a solution that manages product data across your
company. But who creates, enriches, and classifies this product data?
Even if the answer varies for each organization, the following standard
actors are typically involved in Master Data Management.

PRODOC note: JOPI - using p.Body1 instead of p.Image1 for these to
eliminate the extra space AFTER the images.

                                                                          User                Role
  ----------------------------------------------------------------------- ------------------- -----------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/retailer.png)         Retailer            Buys products from suppliers and sells them to customers.
  ![](../../../Resources/Images/PMDM%20for%20Retail/supplierVendor.png)   Supplier / Vendor   Sells products to retailers.
  ![](../../../Resources/Images/PMDM%20for%20Retail/dataProvider.png)     Data Provider       Produces product data as a service.
  ![](../../../Resources/Images/PMDM%20for%20Retail/customer.png)         Customer            Buys products from the retailer.

The retail\'s actors are discussed below.

Retailer\'s Actors
------------------

From the retailer\'s perspective, the following tables show the users
and roles involved in the PMDM for Retail solution.

Some actors are valid for both modules (PCM and VDO), while some are
specific to VDO only.

PRODOC note: JOPI - using p.Body1 instead of p.Image1 for these to
eliminate the extra space AFTER the images.

+----------------+----------------+----------------+----------------+
|                | User           | Role           | In module      |
+================+================+================+================+
| ![](           | Buyer          | Negotiates and | ![](../        |
| ../../../Resou |                | buys products  | ../../Resource |
| rces/Images/PM |                | from the       | s/Images/Solut |
| DM%20for%20Ret |                | supplier.      | ion%20Enableme |
| ail/buyer.png) |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![](../        | Quality        | Ensures the    | ![](../        |
| ../../Resource | Assurance      | quality of the | ../../Resource |
| s/Images/PMDM% | Expert         | data.          | s/Images/Solut |
| 20for%20Retail |                |                | ion%20Enableme |
| /qaexpert.png) |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![](           | Marketing      | Writes copy    | ![](../        |
| ../../../Resou | Specialist     | and manages    | ../../Resource |
| rces/Images/PM |                | the product\'s | s/Images/Solut |
| DM%20for%20Ret |                | marketing      | ion%20Enableme |
| ail/marketings |                | data.          | nt/PMDM/PMDM%2 |
| pecialist.png) |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![](../../../R | Image          | Maintains the  | ![](../        |
| esources/Image | Specialist     | images and     | ../../Resource |
| s/PMDM%20for%2 |                | assets of the  | s/Images/Solut |
| 0Retail/images |                | product.       | ion%20Enableme |
| pecialist.png) |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![](           | Warehouse      | Manages        | ![](../        |
| ../../../Resou | Specialist     | ware           | ../../Resource |
| rces/Images/PM |                | house-specific | s/Images/Solut |
| DM%20for%20Ret |                | product data.  | ion%20Enableme |
| ail/warehouses |                |                | nt/PMDM/PMDM%2 |
| pecialist.png) |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![](.          | Enrichment     | In smaller     | ![](../        |
| ./../../Resour | Specialist     | organizations, | ../../Resource |
| ces/Images/Sol |                | the Enrichment | s/Images/Solut |
| ution%20Enable |                | Specialist can | ion%20Enableme |
| ment/PMDM/PMDM |                | cumulate the   | nt/PMDM/PMDM%2 |
| %20For%20Retai |                | work of the    | 0For%20Retail/ |
| l/EnrichmentSp |                | Marketing      | PCMButton.png) |
| ecialist2.png) |                | Specialist,    |                |
|                |                | the Image      | ![](../        |
|                |                | Specialist,    | ../../Resource |
|                |                | the Warehouse  | s/Images/Solut |
|                |                | Specialist.    | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                | ![](../..      | 0For%20Retail/ |
|                |                | /../Resources/ | VDOButton.png) |
|                |                | Images/Solutio |                |
|                |                | n%20Enablement |                |
|                |                | /PMDM/PMDM%20F |                |
|                |                | or%20Retail/ES |                |
|                |                | %20_Image.png) |                |
+----------------+----------------+----------------+----------------+
| ![](../../     | Data Steward   | Manages        | ![](../        |
| ../Resources/I |                | cat            | ../../Resource |
| mages/PMDM%20f |                | egory-specific | s/Images/Solut |
| or%20Retail/da |                | attributes,    | ion%20Enableme |
| tasteward.png) |                | LOVs, primary  | nt/PMDM/PMDM%2 |
|                |                | product        | 0For%20Retail/ |
|                |                | hierarchy, and | PCMButton.png) |
|                |                | cl             |                |
|                |                | assifications. | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+

Technically, MDM also involves machine-to-machine (M2M), where exchange
and automation happen between the systems. This means the external
systems must also be considered as actors.

PRODOC note: JOPI - using p.Body1 instead of p.Image1 for these to
eliminate the extra space AFTER the images.

+----------------+----------------+----------------+----------------+
|                | System         | Role           | In module      |
+================+================+================+================+
| ![             | ERP            | Optionally     | ![](../        |
| ](../../../Res |                | sends data to  | ../../Resource |
| ources/Images/ |                | STEP,          | s/Images/Solut |
| PMDM%20for%20R |                | including a    | ion%20Enableme |
| etail/erp.png) |                | unique SKU ID, | nt/PMDM/PMDM%2 |
|                |                | and a value    | 0For%20Retail/ |
|                |                | used to        | PCMButton.png) |
|                |                | classify the   |                |
|                |                | product        | ![](../        |
|                |                | automatically  | ../../Resource |
|                |                | (the \'ERP     | s/Images/Solut |
|                |                | line\'         | ion%20Enableme |
|                |                | attribute).    | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![]            | STEP           | Master Data    | ![](../        |
| (../../../Reso |                | Management     | ../../Resource |
| urces/Images/P |                |                | s/Images/Solut |
| MDM%20for%20Re |                |                | ion%20Enableme |
| tail/step.png) |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| ![             | E-commerce     | Receives the   | ![](../        |
| ](../../../Res | platform       | MDM product    | ../../Resource |
| ources/Images/ |                | data to be     | s/Images/Solut |
| PMDM%20for%20R |                | used on        | ion%20Enableme |
| etail/ecommerc |                | E-commerce     | nt/PMDM/PMDM%2 |
| eplatform.png) |                | channels.      | 0For%20Retail/ |
|                |                |                | PCMButton.png) |
|                |                |                |                |
|                |                |                | ![](../        |
|                |                |                | ../../Resource |
|                |                |                | s/Images/Solut |
|                |                |                | ion%20Enableme |
|                |                |                | nt/PMDM/PMDM%2 |
|                |                |                | 0For%20Retail/ |
|                |                |                | VDOButton.png) |
+----------------+----------------+----------------+----------------+
| !              | PDS            | Product Data   | ![](..         |
| [](../../../Re |                | Syndication is | /../../Resourc |
| sources/Images |                | a simple,      | es/Images/Solu |
| /Solution%20En |                | fast,          | tion%20Enablem |
| ablement/PMDM/ |                | cost-effective | ent/PMDM/PMDM% |
| PMDM%20For%20R |                | way for        | 20For%20Retail |
| etail/PDS.png) |                | manufacturers  | /VDO_Only.png) |
|                |                | and brands to  |                |
|                |                | share and      |                |
|                |                | update product |                |
|                |                | data with      |                |
|                |                | retailers,     |                |
|                |                | data pools and |                |
|                |                | content        |                |
|                |                | service        |                |
|                |                | providers. The |                |
|                |                | suppliers and  |                |
|                |                | manufacturers  |                |
|                |                | use PDS to     |                |
|                |                | publish their  |                |
|                |                | products to    |                |
|                |                | PMDM for       |                |
|                |                | Retail.        |                |
+----------------+----------------+----------------+----------------+

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

---
description: 'Within the Product Content Management module, the
  \''govern\'' activity includes defining and maintaining a mapping
  between the ERP and PMDM. The product is automatically classified in
  the primary product hierarchy using a value (\''ERP line\'') provided by
  the ERP. And it is also possible to classify products directly in
  STEP.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Govern\' Activity
==============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMGovern.png)

Data Steward
------------

+----------------------------------+----------------------------------+
| ![                               | The data steward:                |
| ](../../../Resources/Images/PMDM |                                  |
| %20for%20Retail/datasteward.png) | -   maintains the mapping        |
|                                  |     between the ERP              |
|                                  |     classification and the MDM   |
|                                  |     classification.              |
|                                  | -   performs Data Governance     |
|                                  |     tasks to maintain            |
|                                  |     attributes, attribute        |
|                                  |     groups, and LOVs.            |
+----------------------------------+----------------------------------+

Each of these tasks are defined below.

Maintain the ERP and PMDM Classification Mapping
------------------------------------------------

Within the Product Content Management module, the \'govern\' activity
includes defining and maintaining a mapping between the ERP and PMDM.
This task is usually performed by the data steward.

The product is automatically classified in the primary product hierarchy
using a value (\'ERP line\') provided by the ERP. And it is also
possible to classify products directly in STEP.

Applying automatic classifications requires a mapping between the \'ERP
line\' code, provided by the ERP, and a unique identifier of a node (a
level) in the primary product hierarchy. This identifier is the
attribute \'External Identifier (ExternalIdentifier)\'.

This mapping is served by a Transformation Lookup Table
(PMDM.LUT.ERPToPMDMMapping) and must be maintained in the workbench.

![](../../../Resources/Images/PMDM%20for%20Retail/ERP-MDMClassification.png)

**Mapping between ERP and PMDM - Click to Play**

[ ]{.wistia_embed .wistia_async_zvnegy0isj .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:281px;position:relative;width:533px"}

Attributes and LOV Data Governance
----------------------------------

The data steward manages attributes, attribute groups, and LOVs in the
Web UI. Data Governance features are accessed via a Stack Panel Item on
the \-\--\[MAIN\]\-\-- page of your Web UI.

![](../../../Resources/Images/PMDM%20for%20Retail/attribandLOVGovernance.png)

---
description: 'Within the Product Content Management module, the
  \''manage\'' activity involves user groups for images, marketing copy,
  and warehouse providing the required data for the buyer\''s approval.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Manage\' Activity
==============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMManage.png)

Two actions are included in the \'manage\' activity:

-   Enrich data for a newly created product in the Product Creation
    Workflow.
-   Collaborate about any subject on a product or a family in the
    Product Collaboration Workflow.

Each action is described below.

Enrich Product Data Action
--------------------------

Within the Product Content Management module, the \'enrich\' action
involves user groups for images, marketing copy, and warehouse providing
the required data for the buyer\'s approval.

The business logic in this action is as follows:

-   STEP checks if the product is classified, and if not, the product is
    assigned to the \'Buyer Group\' for manual classification. This is
    repeated until the product is classified.
-   The **Buyer** reviews the data. If the data is not acceptable, the
    task is reassigned to the previous individual user for additional
    data review.
-   The product is reviewed and enriched by these user groups:

The **Marketing Copy Group** handles the \'Copy Writing\' state and
enriches marketing information.

The **Image Group** handles the \'Digital Assets\' state and uploads
digital assets relevant to the product.

The **Warehouse Group** handles the \'Warehouse Data\' state and
enriches warehouse data information.

-   The **QA Expert** reviews all data and either accepts or rejects the
    product.

 

![](../../../Resources/Images/PMDM%20for%20Retail/manageEnrichmentProcess.png)

### Review and enrichment actions by role

  ---------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/buyer.png)                 The Buyer reviews a newly-completed product completely before submitting it to the rest of the team.
  ![](../../../Resources/Images/PMDM%20for%20Retail/marketingspecialist.png)   The Marketing Specialist must assign the product to a Web Category and should also provide additional review as necessary.
  ![](../../../Resources/Images/PMDM%20for%20Retail/imagespecialist.png)       The Image Specialist must attach a Primary Product Image, and should also provide additional review as necessary, and clicks the \'Proceed\' button.
  ![](../../../Resources/Images/PMDM%20for%20Retail/warehousespecialist.png)   The Warehouse Specialist has no required actions, as this role can vary per customer. This review can include attribute information for Base Unit Information (the package of the \'each\' dimensions and weight), Country of Origin, Regulatory Information, and Packaging Hierarchy (in this module, Packaging Hierarchy are modeled as a Data Container).
  ![](../../../Resources/Images/PMDM%20for%20Retail/qaexpert.png)              The QA Expert performs the final review and validation, and then approves or rejects the product.
  ---------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Review and enrichment action process

1.  On the homepage in the Product Creation Workflow widget, specialists
    see the number of products ready for review and enrichment based on
    role. In this example, the Marketing Specialist clicks the link to
    display the \'To do\' tab and the tasks in the Copywriting Review
    state.

![](../../../Resources/Images/PMDM%20for%20Retail/enrichWorkflow.png)

1.  On the To Do tab, the specialist reviews the product, focusing on
    the data listed, and clicks the **Assign To Me** button if editing
    is required. In this example, the Marketing Specialist clicks the
    \'Assign to me\' button before providing the data for the
    Copywriting Review task.

![](../../../Resources/Images/PMDM%20for%20Retail/enrichToDoAssign.png)

1.  After each team completes the review and enrichment, the QA Expert
    validates the data quality and takes one of these actions:

-   Accepts the product, which is then automatically approved and
    exported, as defined in the **Product Content Management \'Share\'
    Activity** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   Rejects the product and returns it to the Buyer, Copy Writing,
    Digital Assets, and/or Warehouse group, adding a message for the
    group(s).

![](../../../Resources/Images/PMDM%20for%20Retail/enrichQASpecialist.png)

Collaboration Action
--------------------

PMDM for retail integrates a Collaboration feature based on a workflow.
When browsing a product page, a member of the team can forward the
product to a user group with a message. Collaboration can be used to
raise a question, request action from a team member, etc.

For example, consider the following process to conduct a conversation
between Rachel, the buyer, and Imogen, the image specialist.

1.  Buyer Rachel clicks the Collaboration button.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationButton.png)

1.  Buyer Rachel selects the Image Group as recipient and adds a
    message.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationImgGrpMessage.png)

1.  Image specialist Imogen sees there is a message for the Image Group
    on the homepage Collaboration Workflow widget and clicks the link.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationLink.png)

1.  Image specialist Imogen reviews the latest message in the task list.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationMessage.png)

1.  Image specialist Imogen uses the \'Assigned to me\' header to claim
    the task.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationMessageAssigned.png)

1.  Image specialist Imogen views the conversation thread on the product
    page.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationConvoThread.png)

1.  Image specialist Imogen can perform the following actions:

-   Continue the conversation by adding a new message and clicking the
    **Collaboration** button.
-   Click the **Release Task** button to remove the current assignment
    so that someone else in the group can work the task.
-   Click the **End Collaboration** button to finish the conversation.

---
description: 'Within the Product Content Management module, the
  \''share\'' activity includes an OIEP (outbound integration endpoint)
  exports data in STEPXML format to a hotfolder. The targeted system
  then imports the data and process it.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Share\' Activity
=============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMShare.png)

Within the Product Content Management module, the \'share\' activity
includes an outbound integration endpoint (OIEP) that exports data in
the STEPXML format to a hotfolder. The targeted system then imports the
data and processes it.

The OIEP \'Products Outbound (PMDM.OIEP.ProductOutbound)\' is triggered
on each approval.

![](../../../Resources/Images/PMDM%20for%20Retail/shareOIEP.png)

For more information, see the **Outbound Integration Endpoints** topic
in the **Data Exchange** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

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

---
description: 'As Product Master Data Management (PMDM) multi-domain
  specialists, we have studied customers\'' business processes and
  configurations. We have identified patterns that frequently occur in
  the retail industry. The big picture of \''PMDM for Retail\'' is focused
  on data, and as the \''source of truth\'' for data, MDM is at the heart
  of data governance.'
title: '\[%=Heading.AnyLevel%\]'
---

Product MDM for Retail
======================

\'PMDM for Retail\' are starter packs or "modules" that allow you to
bootstrap your PMDM project. These are ready-to-use solutions, based on
the most commonly observed features in the market, and they can be
customized to meet your requirements.

Each pack contains:

-   A workable configuration (data model, WebUI, workflows, business
    rules, IEP, etc.)
-   Documentation

There are several packs or "modules", each covering different use cases:

-   Product Content Management (PCM) module
-   Vendor Data Onboarding (VDO) module
-   GDSN module, working in conjunction with VDO module

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PMDMForRetailModules.png)

Each business is different---your processes, your products, your
organization. Implementing a PMDM (Stibo Systems' Product Master Data
Management solution) raises a lot of questions and can seem challenging.

As PMDM multi-domain specialists, Stibo Systems has studied customers\'
business processes and configurations and has identified patterns that
frequently occur in the retail industry.

[![](../../../Resources/Images/PMDM%20for%20Retail/RetailOverview.png)]{style="color: #ff0000;"}

PMDM for Retail Getting Started
-------------------------------

PMDM for Retail is organized as modules. This allows you to start with
just a few modules / components, and as your PMDM solution grows,
additional modules / components can be added. PMDM for Retail modules
are off-the-shelf, ready-to-use, yet customizable configurations.

The following topics are the first that you should read to understand
the basics of PMDM for Retail:

-   Product MDM Modules ([here]{.mcFormatColor style="color: Blue;"})
-   PMDM for Retail Key Concepts ([here]{.mcFormatColor
    style="color: Blue;"})
-   PMDM for Retail Products and Product Data ([here]{.mcFormatColor
    style="color: Blue;"})
-   Product Data Lifecycle ([here]{.mcFormatColor style="color: Blue;"})

Module - Product Content Management
-----------------------------------

The following topics explain the setup of and activities managed by the
\'Product Content Management\' module included in PMDM for Retail as
displayed in the image above:

-   General Presentation of the Product Content Management Module
    ([here]{.mcFormatColor style="color: Blue;"})
-   Initial Setup for Product Content Management Module
    ([here]{.mcFormatColor style="color: Blue;"})
-   Product Content Management \'Govern\' Activity[
    ([here]{.mcFormatColor
    style="color: Blue;"})]{style="color: #ff0000;"}
-   Product Content Management \'Acquire\' Activity
    ([here]{.mcFormatColor style="color: Blue;"})
-   Product Content Management \'Manage\' Activity
    ([here]{.mcFormatColor style="color: Blue;"})
-   Product Content Management \'Share\' Activity ([here]{.mcFormatColor
    style="color: Blue;"})

Module - Vendor Data Onboarding
-------------------------------

The following topics explain the setup of and activities managed by the
\'Vendor Data Onboarding\' module:

-   General Presentation of the Vendor Data Onboarding Module
    ([here]{.mcFormatColor style="color: Blue;"})
-   Vendor Data Onboarding Data Model ([here]{.mcFormatColor
    style="color: Blue;"})
-   Vendor Data Onboarding - Processes ([here]{.mcFormatColor
    style="color: Blue;"})

Module - GDSN Receiver for Vendor Data Onboarding
-------------------------------------------------

-   Module - GDSN Receiver for PMDM for Retail ([here]{.mcFormatColor
    style="color: Blue;"})

---
description: 'As Product Master Data Management (PMDM) multi-domain
  specialists, we have studied customers\'' business processes and
  configurations. We have identified patterns that frequently occur in
  the retail industry. The big picture of \''PMDM for Retail\'' is focused
  on data, and as the \''source of truth\'' for data, MDM is at the heart
  of data governance.'
title: '\[%=Heading.AnyLevel%\]'
---

Product MDM Modules
===================

The following modules are available in PMDM for Retail:

-   **Product Content Management** is a 1:1 product data flow where the
    purchased product is exactly the same as the sold product. There are
    no separate objects and no supplier data onboarding.
-   **Vendor Data Management** is an n:1 product data flow where there
    can be multiple supplier-side products for one retailer-side product
    (buy-side / sell-side).

+----------------------+----------------------+----------------------+
|                      | Product Content      | Vendor Data          |
|                      | Management           | Onboarding           |
+======================+======================+======================+
| Product data model   | 1:1                  | n:1                  |
|                      |                      |                      |
|                      | Sell-side only, what | Multiple             |
|                      | you buy is what you  | supplier-side        |
|                      | sell.                | products for 1       |
|                      |                      | retailer-side        |
|                      | ![](                 | product.             |
|                      | ../../../Resources/I |                      |
|                      | mages/PMDM%20for%20R | ![](..               |
|                      | etail/sameProductBou | /../../Resources/Ima |
|                      | ghtAndSoldsmall.png) | ges/PMDM%20for%20Ret |
|                      |                      | ail/multipleProducts |
|                      |                      | SoldAsSamesmall.png) |
+----------------------+----------------------+----------------------+
| Onboarding workflow  | ![](../../../Resour  | ![](../../../Resour  |
| - pre-defined tasks  | ces/Images/Buttons/g | ces/Images/Buttons/g |
| and logic for        | reen_checkmark1.png) | reen_checkmark1.png) |
| product data         |                      |                      |
| creation             | Product Data is      | Product Data is      |
|                      | onboarded by the     | onboarded by the     |
|                      | Retailer             | Suppliers            |
+----------------------+----------------------+----------------------+
| Collaboration        | ![](../../../Resour  | ![](../../../Resour  |
| workflow -           | ces/Images/Buttons/g | ces/Images/Buttons/g |
| pre-defined tasks    | reen_checkmark1.png) | reen_checkmark1.png) |
| and logic for        |                      |                      |
| collaboration inside |                      |                      |
| the retailer\'s team |                      |                      |
+----------------------+----------------------+----------------------+
| Product data         | ![](../../../Resour  | ![](../..            |
| onboarding via       | ces/Images/Buttons/g | /../Resources/Images |
| Smartsheet - using   | reen_checkmark1.png) | /Buttons/red_x1.png) |
| Smartsheet to create |                      |                      |
| / update product     |                      |                      |
| data                 |                      |                      |
+----------------------+----------------------+----------------------+
| Product data         | ![](../..            | ![](../../../Resour  |
| onboarding via PDS - | /../Resources/Images | ces/Images/Buttons/g |
| the Supplier uses    | /Buttons/red_x1.png) | reen_checkmark1.png) |
| PDS to manage its    |                      |                      |
| products and         |                      |                      |
| syndicates them to a |                      |                      |
| dedicated            |                      |                      |
| retailer\'s channel  |                      |                      |
+----------------------+----------------------+----------------------+
| Product data         | ![](../..            | ![](../../../Resour  |
| onboarding via GDSN  | /../Resources/Images | ces/Images/Buttons/g |
| - get quality        | /Buttons/red_x1.png) | reen_checkmark1.png) |
| product data from    |                      |                      |
| GS1 standard, GDSN.  |                      |                      |
| GS1 is not a         |                      |                      |
| supplier, therefore  |                      |                      |
| there is no pricing  |                      |                      |
| information          |                      |                      |
+----------------------+----------------------+----------------------+
| Variant handling     | ![](../../../Resour  | ![](../..            |
|                      | ces/Images/Buttons/g | /../Resources/Images |
|                      | reen_checkmark1.png) | /Buttons/red_x1.png) |
+----------------------+----------------------+----------------------+

---
description: 'If the product data received from PDS or GDSN contains
  packaging information, then it will be created as a separate packaging
  object per packaging hierarchy level. PMDM for Retail is
  pre-configured with support for Pack, Case and Pallet which will be
  linked from the largest unit to the smallest unit with the quantity of
  next lower package stored as meta-data on the reference. The Each is
  represented by the External Source Record.'
title: '\[%=Heading.AnyLevel%\]'
---

Vendor Data Onboarding - Packaging Hierarchy
============================================

If the product data received from PDS or GDSN contains packaging
information, then it will be created as a separate packaging object per
packaging hierarchy level. PMDM for Retail is pre-configured with
support for Pack, Case and Pallet which will be linked from the largest
unit to the smallest unit with the quantity of next lower package stored
as meta-data on the reference. The Each is represented by the External
Source Record.

The packaging objects are modeled as products in PMDM for Retail. They
will be categorized directly under either External Packaging or Internal
Packaging in the separate Packaging Hierarchy without further
categorization.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/Packaging_Objects.png)

The Packaging Hierarchy can be viewed in a Product details page, in the
"Packaging Hierarchy" tab.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PackagingHierarchy.png)

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PackagingHierarchy.png)

 ---
description: 'Configuration of the Product Content Management business
  module is largely handled automatically upon installation. This topic
  provides high-level information only, including how to access the
  module on your system.'
title: '\[%=Heading.AnyLevel%\]'
---

Vendor Data Onboarding - Processes
==================================

Onboarding Process
------------------

Below is the full story about onboarding vendor data. Each number is
detailed in its own section.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess.png)

---
description: 'For the Suppliers to be able to onboard Products via PDS,
  the schema used for the PDS channel needs knowledge about the Supplier
  facing product hierarchy, the set of Supplier relevant attributes and
  asset references etc., as defined in PMDM for Retail. This section
  contains information about how this can be controlled in PMDM for
  Retail.'
title: '\[%=Heading.AnyLevel%\]'
---

Vendor Data Onboarding - Setup
==============================

Initial Setup for Vendor Data Onboarding Module
-----------------------------------------------

Contact your Stibo Systems account manager or partner manager for
information on activating the PMDM for Retail solution:

-   PMDM: STEP 10.0 (or greater)
-   Service activation (license, PDS channel)
-   Install and configure the module

Some of the key setup activities are described in the next paragraphs.

More tasks must be performed to make the configuration fully
operational, which will not be handled by your dedicated consultants or
partners.

-   PDS-related data (see below)
-   Suppliers (see below)
-   Matching & linking
-   Users and groups
-   Contexts
-   Asset push
-   OIEP
-   Configure profiling for KPIs

Configuration of the data model for the PDS channel
---------------------------------------------------

For the Suppliers to be able to onboard Products via PDS, the schema
used for the PDS channel needs knowledge about the Supplier facing
product hierarchy, the set of Supplier relevant attributes and asset
references etc., as defined in PMDM for Retail. This section contains
information about how this can be controlled in PMDM for Retail.

When there has been a change to the data model in PMDM for Retail which
is relevant for the PDS channel then it is necessary to make a schema
update in PDS to reflect the change. This can be done as a weekly
scheduled process or on request.

### Supplier facing Product Hierarchy

The selectable product categories in the PDS channel include all nodes
of the object types External Level1 - External Level 6 defined below the
"External Product Hierarchy" node.

The product hierarchy allows for creation of External Source Records
starting at External Level 3.

Packaging Objects (Pallet, Case, Pack) will be created directly below
the "External Packaging" node.

### Attributes

There are three attribute groups where all viewable attribute groups
will be stored: Product Maintenance, Packaging Maintenance and Category
Specific Attributes.

All attributes in the mentioned groups will per default be shown to the
Suppliers in PDS.

If specific attributes in the mentioned attribute groups should not be
shown in PDS then the attributes have to be linked to the "PDS: Hide
From Supplier" attribute group.

### Asset references

The set of asset reference types to display in PDS can be controlled by
setting the "PDS: Relevance" attribute to Yes on the asset reference
type definition for the PDS relevant asset reference types.

### Display sequence of Attributes and Attribute Groups

The "Display Sequence" attribute valid on attribute definitions,
attribute group definitions and on attribute links can be used to
control the display order of attribute groups and attributes within
those groups in PDS.

### Required for Initiate

It might not be necessary that the Supplier fills out the full set of
mandatory attributes before he submits a new Product to PMDM for Retail.
A short description and the GTIN of the Product might be enough for the
Retailer to determine if this is a product they would like to onboard.

The set of attributes being mandatory for initiate is defined by linking
the attributes to the "PDS: Mandatory For Proposal" attribute group.

### Mandatory Attributes

The set of attributes being mandatory for submit after initiate is
defined by linking the attribute to the "PDS: Mandatory For Submit"
attribute group.

Category specific mandatory attributes are controlled using the standard
Mandatory option on the attribute link.

### Category Specific Mandatory Asset References

Category specific asset references that are mandatory will sit on the
product category node itself. The multi-valued "PDS: Mandatory
References" attribute will hold the list of references that are
mandatory on that category.

### Locked Down Attribution

It might be beneficial to be able to lock certain attributes after a
product has been initially onboarded into PMDM for Retail to prevent the
value of these attribute gets changed by the Supplier. To enable this,
the relevant attributes must be linked to the "PDS: Locked After
Proposal" attribute group.

### Attribute Help Text

It is possible to show description of attributes and asset references to
the Suppliers in PDS by using the "PDS: Description" attribute being
valid for attribute definitions and asset reference definition.

Setup of new Suppliers
----------------------

Before a Supplier can submit product data from PDS the Supplier has to
be created in PMDM for Retail.

A few objects must be created per supplier and a few configuration
options needs to be defined per Supplier.

To setup a new Supplier the following steps are needed:

1.  Create a new Supplier User Group below the Suppliers user group.

As part of this process, the Supplier Classification is created by
selecting the parent for the Supplier Classification below the
"Suppliers" classification node.

1.  Create a User below the new Supplier User Group.

This user is used by PDS to authenticate against PMDM for Retail.

1.  Set the value of the "PDS: Is Service Account?" attribute to "Yes"
    on the new User.

This will start a process which will link the user to the "PDS: Service
Accounts" user group and add the User ID to the "PDS: Service Account"
attribute on the Supplier Classification.

1.  On the Supplier Classification the following attributes should be
    maintained:

-   **Supplier ID and Supplier Name** - Used to identify the Supplier
    and to ensure uniqueness.
-   **Type of Supplier** - Used for information purpose when comparing
    sources for a Golden Record.
-   **General Handling of New Source Records** - Controls if new
    External Source Records from this Supplier should be automatically
    approved in PMDM for Retail or if the Buyer needs to manually
    approve the product data before onboarding the Product.
-   **General Handling of Updated Source Records** - Controls if a
    change to an existing External Source Records from this Supplier
    should be automatically approved in PMDM for Retail or if the Buyer
    needs to manually approve a change before it is considered for
    promotion by the Matching and Linking process.
-   **General Rank For Supplier and General Rank Type Of Supplier** -
    Used by the Matching and Linking survivorship rules to control the
    preferred order of source when promoting product data to the Golden
    Record.

**Rank Type Of Supplier has the following options**: "Approved Content
Source" (AC) and "Non-Approved Content Source" (NA).

**Rank For Supplier has the following options**: 1, 2, 3, 4, 5.

The values of the two attributes are concatenated into a single Source
Rank For Promotion value which is used by the survivorship rules when
promoting product data to the Golden Record.

The preferred order of sources configured in the survivorship rules in
PMDM for Retail is:

MDM, AC1, AC2, AC3, AC4, AC5, NA1, NA2, NA3, NA4, NA5, NA99

where:

MDM: Internal Source Record

AC1-5: Approved Content Source

NA1-5: Non-Approved Content Source

NA99: Used if no Rank Type or Rank is defined for the supplier.

**Example**:

Attribute A has the value "Yes" on a source having AC2 as Source Rank
For Promotion.

The survivorship rules check the sources in the defined preferred order.
First it checks the Internal Source Record which doesn't have a value
for Attribute A. It continues to look for a source with AC1 but that
External Source Record does not have a value for Attribute A either. So
it continues by looking for a source with AC2. Finally, a value for
Attribute A is found so this value will be promoted to the Golden Record
and it will skip looking for values on lower ranked sources.

For some Suppliers it might be required to be able to overwrite the
general source record handling and product data ranking on all Products
below specific Product Hierarchy nodes. This can be done by linking a
node from the External Product Hierarchy to the Supplier Classification
using the Category Ranking For Supplier link type. The link will have
the following meta-data attributes: Category Handling of New Source
Records, Category Handling of Updated Source Records, Category Rank for
Supplier and Category Rank Type of Supplier.

5.  The Supplier Classification must be approved.

This will start a process which will generate a unique supplier
identifier in the "PDS: Supplier Identifier" attribute on the Supplier
Classification.

6.  The "PDS: Supplier Identifier" value generated within a minute of
    the initial approval of the Supplier Classification is what the
    Supplier needs for authentication when adding the channel in PDS.

---
description: 'Configuration of the Product Content Management business
  module is largely handled automatically upon installation. This topic
  provides high-level information only, including how to access the
  module on your system.'
title: '\[%=Heading.AnyLevel%\]'
---

Vendor Data Onboarding Data Model
=================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/VDO%20-%20Data%20Model.png)

The Vendor Data Onboarding data model includes External Source Records,
an Internal Source Record, and a Golden Record. The following diagram
illustrates how the different objects are articulated:

-   The Golden Record aggregates data coming from the External Source
    records and the Internal Source records (aka \'Silver Record\').

-   The packaging hierarchy objects are attached to each record.

-   The \'each\' is the source record itself.

-   Each Source Record has a 'rank'. This rank can be thought of as a
    \'weight\' or \'trust index\' used during the Matching & Linking
    process to prioritize data and chose which record to \'promote\'
    from the different sources to the Golden Record.

Primary Product Hierarchy
-------------------------

In the Vendor Data Onboarding configuration, the Primary Product
Hierarchy is organized as follows:

-   External Data Sources
-   Internal Data Sources
-   Packaging hierarchy

The structures of the \'External Data Sources\' and \'Internal Data
Sources\' are identical, as shown below.

![](../../../Resources/Images/PMDM%20for%20Retail/VDOdataModel2.png)

-   In the External Data Sources classification, the External Source
    Records are stored.
-   In the Internal Data Sources, the Internal Source Record and the
    Golden Records are stored.

+----------------------------------+----------------------------------+
| A populated External Data        | A populated Internal Data        |
| Sources hierarchy                | Sources hierarchy                |
|                                  |                                  |
| !                                | ![](../../../Resources/Images    |
| [](../../../Resources/Images/Sol | /Solution%20Enablement/PMDM/PMDM |
| ution%20Enablement/PMDM/PMDM%20F | %20For%20Retail/PopInternal.png) |
| or%20Retail/PopExDataSource.png) |                                  |
+----------------------------------+----------------------------------+

The Packaging hierarchy is a flat structure, used to store the packaging
objects.

![](../../../Resources/Images/PMDM%20for%20Retail/VDOdataModel3.png)

Supplier classification
-----------------------

Suppliers are classified in a classic way:

![](../../../Resources/Images/PMDM%20for%20Retail/VDOdataModel4.png)

Assets
------

Assets are linked as follows:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/VDO%20-%20Data%20Model%20-%20Assets.png)

Vendor Data Onboarding - Processes
==================================

Onboarding Process
------------------

Below is the full story about onboarding vendor data. Each number is
detailed in its own section.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess.png)

### Onboarding process -- 1a --The Supplier manages and publishes Product Data

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess1A.png)

Using PDS, the vendor will onboard and submit their product information
to the Retailer. The following is a typical process followed by the
vendor.

-   **Import Data**: Vendors can upload product data and assets either
    from Excel or using PDS' APIs to integrate with their internal
    systems.

-   **Master Data**: Vendors can view, and when required, manage
    imported product data and digital assets.

-   **Categorization**: Vendors will manually select or create
    automation rules to map products to retailer categories.

-   **Mapping and Validation**: To ensure they meet the Retailer's
    requirements, the vendor will map their master data attributes to
    the retailer specific attributes, viewing any error messages, and
    using attribute value transformations or data edits to resolve
    errors.

-   **Process Management**: From product onboarding and maintenance to
    viewing and responding to reject and return reasons, vendors can use
    PDS to manage the end-to-end process of syndicating their product
    information to the retailer.

### Onboarding process -- 1b -- The PMDM onboards External Product Data from GDSN

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/DataFromGS1.png)

Product Data can be onboarded from GS1. This ensures a very high data
quality. GS1 data is collected in a separate STEP instance with a GDSN
receiver.

For more details, see the topic **Module - GDSN Receiver for PMDM for
Retail**[]{.mcFormatColor style="color: Blue;"}here.

### Onboarding process -- 2 -- The PMDM onboards External Product Data from Suppliers

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

### Onboarding process -- 3 -- The buyer accepts or rejects the Supplier's Product proposal

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/OnboardingProcess3.png)

When a new External Source Record has been created in PMDM for Retail
and initiated in the External Source Record Handling workflow, the
workflow checks if the specific Supplier is configured to allow for
automatic approval of proposed products or if it has to go through a
manual process where the Buyer has to manually decide if we want to
onboard the product.

On the homepage, in the "External Record Handling" widget, the buyer
will see the number of External Source Records concerned.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/Homepage.png)

In the manual proposal approval process the buyer has the option to
approve the product data and continue with the onboarding of the
product, send it back to the Supplier for rework in case the supplied
data is wrong or incomplete or reject the product for onboarding in case
the Retailer do not want to onboarding and sell the product.

On the Product Page, the Buyer will make his choice:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/PropStatus%20approve.png)

### Onboarding process -- 4 -- The PMDM aggregates the data in a Golden Record

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/SourceRecorded.png)

When the External Source Record is approved for further onboarding in
the External Source Record Handling workflow it automatically gets
approved and is send for Matching and Linking.

The Matching and Linking process first creates a match code for the
External Source Record which is used to check if there is already an
existing Product with the same match code in the system. Per default,
the match code is the GTIN of the Product.

It no existing Product with the GTIN is found then the system creates a
new Golden Record and an Internal Source Record for this Product. The
Internal Source Record is used by the Retailer to enrich the Product and
will contain the Retailers own product data like web descriptions, data
from the ERP system etc. If the External Source Record causing the
Matching and Linking process to be executed has corresponding external
packaging objects, then they will be duplicated to internal packaging
objects which will be linked to the created Internal Source Record.

If there is already a Product with the same GTIN then there is a match
and the External Source Record will be linked to the existing Golden
Record.

As part of the process data from all linked sources (External and
Internal Source Records) will be promoted to the Golden Record using a
set of survivorship rules which is defined on the Products matching
algorithm.

### Onboarding process -- 5 -- The Retailer adds sell-side specific data

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/RetailerExpert.png)

The product data for a new Product needs to be enriched internally by
the Retailer before it will be ready to go out for downstream systems
and be sold. To support this process, the Internal Source Record
Creation workflow is initiated when a new Golden Record and Internal
Source Record are created.

First, a task is assigned to the Buyer Group to allow a Buyer to enrich
and maintain the Buyer relevant part of the product data.

The Buyer Review task is visible on the homepage, in the "Internal
Record Creation" widget:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/InternalRecord.png)

Only the tasks that are relevant to users will be visible to them.

The **Buyer** can also decide if the product should be sent for further
enrichment by the **Marketing Specialists**, the **Image Specialists**
and/or the **Warehouse Specialists** or if it should be sent directly to
final review by the Quality Assurance Experts. If the Product is sent
for further enrichment by Marketing, Image and/or Warehouse they will be
able to do their enrichment in parallel.

The enrichment tasks are visible on the home page, in the "Internal
Record Creation" workflow widget.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCBuyerReview.png)

 

**Alternative**: In smaller organizations, the Enrichment Specialist can
accumulate the work of the Marketing Specialist, the Image Specialist,
the Warehouse Specialist.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/Alternative.png)

This option is visible in the Workflow widget, as the "Enrichment
Review" task.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCBuyerCopy.png)

When all enrichment tasks are done, the Product is assigned to the
Quality Assurance Experts. They have the final saying if all product
data is correct and can be approved. If the Quality Assurance Expert
finds something that needs to be corrected, they have the option to
reject the Product to the Buyer, Marketing, Image, or Warehouse Group
for rework.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/IRCProduct.png)

### Onboarding process -- 6 -- The MDM checks that the data is ok to be presented to other systems

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/MDM.png)

When the Product has been approved by the **Quality Assurance Expert**
the Internal Source Record Creation workflow is sending the Product to
the **Matching and Linking** process again to promote the latest set of
data from the linked sources to the Golden Record. When the data has
been promoted, the Product is initiated in the **Golden Record Gating
workflow** which will validate the Golden Record against a set of
validation rules to see if the Golden Record is ready to be Published.

The Golden Record Gating workflow first runs the Product though a common
validation (validation gate) to check for e.g. attribute values that are
mandatory across all channels. If passed, it will continue with channel
specific validation in parallel to check if specific validation rules
for ERP and E-commerce are fulfilled.

If one or more validation errors are found, then the Product will be
sent to a gating specific "Handle Error" state in the **Handle Gating
Error workflow** and a task will be assigned to the **Quality Assurance
Expert**. When the product data has been corrected and the Quality
Assurance Expert has proceeded the task, the process is executed again
to check if the validation is now fulfilled.

If all general validation rules and the ERP specific validation rules
are fulfilled, then Publish to ERP will be set to Yes on the Golden
Record.

If all general validation rules and the E-commerce specific validation
rules are fulfilled, then Publish to E-commerce will be set to Yes on
the Golden Record.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontGate.png)

The tasks related to Gating Errors can be found on the homepage, in the
"Handle Gating Error" widget.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/HandleGatingError.png)

The errors are displayed at the bottom of the Product Page, like this:

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontGatErrors.png)

Validation rules for gating process

During the Matching and Linking process the Golden Record is initiated
in the Golden Record Gating workflow which will check if the Product it
is ready to be send out to the ERP system and/or the E-commerce
platform.

First the Golden Record will go to a common validation state (Front
Gate) where it will be checked for mandatory attribute values, mandatory
references etc. This check is being handled by the "Front Gate" business
rule.

Per default, the business rule checks the following:

-   The Golden Record has a value for all attributes linked into the
    "Front Gate: Mandatory Attributes" attribute group.

-   The Golden Record has at least one existing reference per reference
    type linked into the "Front Gate: Mandatory References" attribute
    group.

Each reference type must be linked into a separate sub attribute group
below "Front Gate: Mandatory References".

If attributes are linked into the sub attribute group together with the
reference type, then these attributes will be considered mandatory
meta-data attribute on the reference.

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/FrontaGate.png)

If one or more validate errors are found, then the Internal Source
Record will be forwarded to the "Handle Front Gating Error" state in the
Handle Gating Error workflow.

If the Front Gate is passed, then the Golden Record will continue with
the channel specific validation states (ERP Gate and E-commerce Gate).
Each of the two states are similar to the Front Gate.

**ERP Gate**

-   Business rule used: ERP Gate
-   Attribute Group for mandatory attributes: ERP Gate: Mandatory
    Attributes
-   Attribute Group for mandatory references: ERP Gate: Mandatory
    References
-   Attribute containing ERP Gate errors: ERP Gate: Errors
-   State the Internal Source Record will be forwarded to on errors:
    Handle ERP Gating Error

If the ERP Gate is passed, then the "Publish To ERP" attribute is set to
Yes on the Golden Record and the Golden Record is exported to the ERP
system using the "Products Outbound -- ERP\" outbound integration
endpoint.

E-commerce Gate

-   Business rule used: E-commerce Gate
-   Attribute Group for mandatory attributes: E-commerce Gate: Mandatory
    Attributes
-   Attribute Group for mandatory references: E-commerce Gate: Mandatory
    References
-   Attribute containing E-commerce Gate errors: E-commerce Gate: Errors
-   State the Internal Source Record will be forwarded to on errors:
    Handle E-commerce Gating Error

If the E-commerce Gate is passed, then the "Publish To E-commerce"
attribute is set to Yes on the Golden Record and the Golden Record is
exported to the E-commerce system using the "Products Outbound -
E-commerce\" outbound integration endpoint.

### Onboarding process -- 7 -- The PMDM communicates with the ERP

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/ERPOnboarding7.png)

When the Golden Record has passed the validation for ERP then the Golden
Record is sent to the "Products Outbound -- ERP\" Outbound Integration
Endpoint and the corresponding Internal Source Record is initiated in
the ERP Communication workflow which is used to handle the 2-ways
communication with the ERP system.

The export will be in STEPXML format and will contain the Golden Record,
all linked Source Records (Internal and External) plus all packaging
objects linked from the sources.

### Onboarding process -- 8 -- The PMDM sends Product Data to the E-commerce platform E-commerce

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/GoldenRecord.png)

When the Golden Record has passed the validation for E-commerce then the
Golden Record is sent to the "Products Outbound - E-commerce\" Outbound
Integration Endpoint.

The export will be in STEPXML format and will contain the Golden Record,
the assets referenced from the Golden Record and the Web Hierarchies
where the Golden Record is linked.

Collaboration Workflow
----------------------

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/collabWorkflow.png)

The Vendor Data Onboarding configuration includes a collaboration
workflow which works in the same way as in the Product Content
Management Module.

The workflow uses the objects introduced in this module: Internal Source
Record, External Source Record, Golden Record.

With this workflow, the retailer's team can collaborate around product
data. This is an internal communication feature, which cannot include
external suppliers, using different systems.

For PDS, a communication channel is included in the onboarding workflow
to handle when the retailer accepts a supplier's product, rejects it, or
asks the supplier to have it reworked.

 


