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

 
