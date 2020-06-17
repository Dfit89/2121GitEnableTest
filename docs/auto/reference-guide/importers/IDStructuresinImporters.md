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

The part ID and application ID structures for each of the standards
(i.e., AutoCare, NAPA, and TecDoc) are described below. In the examples
below, the import file information is displayed (when applicable) above
a screenshot of the workbench ID, Name, and Object Type fields.

Prerequisites

The ID structures described within this section are dependent upon the
completion of the setup as described in the **2. Run Easy Setup of
Import Flow Process** section ([here]{.mcFormatColor
style="color: Blue;"}) of the **Automotive Quick Start Guide**.

AutoCare Part ID and Application ID Structures

-   **PIES ID** = AC\_PIESItem\_\[BrandAAIAID\]\_\[PartNumber\]

![](../../Resources/Images/Importers/PIES%20Part%20Number.png)

![](../../Resources/Images/Importers/PIES%20Part%20in%20STEP.png)

-   **ACES ID** = AC\_ACESApp\_\[hash function\]

![](../../Resources/Images/Importers/ACES%20Part%20Number.png)

![](../../Resources/Images/Importers/ACES%20Part%20in%20STEP.png)

Submitting the above application will search for the above part, with
the ID as shown. If not found, an error will be reported and the
application will not be created.

NAPA Part ID and Application ID Structures

-   **Part ID** = NAPA\_Product\_\[ProductLine\]\[PartNumber\]

![](../../Resources/Images/Importers/ProductIDNAPA.png)

A NAPA parts importer does not exist within STEP because the NAPA
standard does not offer a standard parts import format, but parts must
still be created with this ID structure.

PRODOC note: MEDU RDCUST-2559

-   **Application ID** = NAPA\_App\_\[hash function\]

![](../../Resources/Images/Importers/NAPA%20Application%20Part%20Number.png)

![](../../Resources/Images/Importers/NAPA%20Application%20in%20STEP.png)

Submitting the above application will search for the above part, with
the ID as shown. If not found, an error will be reported and the
application will not be created.

TecDoc Part ID and Application ID Structures

-   **Part ID** = \[Supplier ID\]-\[hash function\]

![](../../Resources/Images/Importers/TecDoc%20import.png)

![](../../Resources/Images/Importers/TecDoc%20Part%20in%20STEP.png)

-   **Application ID** = TD\_L\_\[hash function\]

![](../../Resources/Images/Importers/TecDoc%20Application%20in%20STEP.png)

The part and application data are in the same file, eliminating the
\'product not found\' error.
