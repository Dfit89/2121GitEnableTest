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
