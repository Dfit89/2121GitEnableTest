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
