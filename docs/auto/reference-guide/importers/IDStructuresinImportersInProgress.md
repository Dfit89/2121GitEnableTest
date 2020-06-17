---
description: 'Automotive Solution: Describes the necessary ID structures
  for importers to properly function.'
title: '\[%=Heading.AnyLevel%\]'
---

ID Structures in Importers
==========================

PRODOC note: per KRMA the first question we get from every customer
trying to load application data (they get an error for the part not
being found) and then we have to explain this whole ID structure bit.

Prior to importing part and/or application data, it is imperative to
know the ID structure for the relevant standard. If part and/or
application data is imported into STEP without using the proper ID
structures, then errors will occur.

The AutoCare and TecDoc Object IDs are automatically created with the
required ID structures through use of the respective importers. However,
a NAPA parts importer does not exist within STEP because the NAPA
standard does not offer a standard parts import format, but parts must
still be created with the ID structure as specified below.

This topic addresses the part and application ID structures used for the
AutoCare, NAPA, and TecDoc standards.

Prerequisites
-------------

The ID structures described within this section are dependent upon the
completion of the setup as described in the **2. Run Easy Setup of
Import Flow Process** section ([here]{.mcFormatColor
style="color: Blue;"}) of the **Automotive Quick Start Guide**.

Part ID and Application ID Structure
------------------------------------

The part ID and application ID structures for each of the standards are
described below. In the examples below, the import file information is
displayed (when applicable) above a screenshot of the workbench ID, Name
and Object Type fields.

### AutoCare

-   **PIES ID** = AC\_PIESItem\_\[BrandAAIAID\]\_\[PartNumber\]

![](../../Resources/Images/Importers/PIES%20Part%20Number.png)

![](../../Resources/Images/Importers/PIES%20Part%20in%20STEP.png)

-   **ACES ID** = AC\_ACESApp\_\[hash function\]

![](../../Resources/Images/Importers/ACES%20Part%20Number.png)

![](../../Resources/Images/Importers/ACES%20Part%20in%20STEP.png)

Submitting the above application will search for the above part, with
the ID as shown. If not found, an error will be reported and the
application will not be created.

### NAPA

The Automotive solution does not provide an importer that will
specifically create the NAPA Product hierarchy because the NAPA standard
does not offer a standard parts import format. Therefore, the NAPA
Product hierarchy must be created manually in STEP Workbench before
creating applications using the Application Importer. Before the NAPA
Application Importer can be used, NAPA Product IDs must be created with
the ID structure below.

-   **Part Type ID** = NAPA\_MPCC\_

![](../../Resources/Images/Importers/ID%20Structure%20NAPA%20MPCC%20Part%20Type.png)

-   **Classification ID** = NAPA\_ProductLine\_\[LineAbbrev\]

![](../../Resources/Images/Importers/Classification%20ID%20NAPA.png)

-   **Product ID** = NAPA\_Product\_\[LineAbbrev\]\[PartNumber\]

PRODOC note: MEDU Per NIFE - Product Line (Stibo Term) and Line
Abbreviation (NAPA Term) are the same thing, it\'s interchangeable.

![](../../Resources/Images/Importers/ProductIDNAPA.png)

When the NAPA Product is created, the NAPA\_PartNumber attribute must
also be populated with the Part Number value, as this attribute value is
used to the determine the Part Number in the NAPA Application and
Interchange Exporter.

-   **Application ID** = NAPA\_App\_\[hash function\]

When the NAPA Application importer is used, the application name is
created using fields 18 and 19 from the import file, and the
\'NAPA\_App\_\' prefix is added to the ID hash function.

PRODOC note: MEDU RDCUST-2559

![](../../Resources/Images/Importers/NAPA%20Application%20Part%20Number.png)

![](../../Resources/Images/Importers/NAPA%20Application%20in%20STEP.png)

Submitting the above application will search for the above part, with
the ID as shown. If not found, an error will be reported and the
application will not be created.

### TecDoc

-   **Part ID** = \[Supplier ID\]-\[hash function\]

![](../../Resources/Images/Importers/TecDoc%20import.png)

![](../../Resources/Images/Importers/TecDoc%20Part%20in%20STEP.png)

-   **Application ID** = TD\_L\_\[hash function\]

![](../../Resources/Images/Importers/TecDoc%20Application%20in%20STEP.png)

The part and application data are in the same file, eliminating the
\"product not found\" error.
