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
