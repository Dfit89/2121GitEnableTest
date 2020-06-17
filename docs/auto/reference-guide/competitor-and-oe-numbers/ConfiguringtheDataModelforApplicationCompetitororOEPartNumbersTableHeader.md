---
description: 'Automotive Solution: Describes how to configure the Data
  Model in the workbench before configuring and using the Application
  Competitor or OE Part Number Table Header.'
title: Configuring the Data Model for Application Competitor or OE Part
  Numbers Table Header
---

Configuring the Data Model for Application Competitor or OE Part Numbers Table Header
=====================================================================================

PRODOC note: BOND PRODOC- 1673 and 1519

Refer to PAKA demo video in Zoom

PRODOC note: Per convo with LURE he will be sending me his setup notes.
New object type is \'OE Application AutoCare\' Interchange Application

The Application Competitor or OE Part Numbers Table Header involves two
levels of configuration. The first level of configuration is performed
in the workbench and the part is configured in the Web UI. After the
Easy Setup action, the Application Competitor or OE Part Numbers Table
Header Component requires additional setup in the data model and needs
to be manually modified. The user needs to be aware of the data model
structure of the modifying automotive standard. This document only
describes the procedure to configure / modify the data model in the
workbench. For information on configuring the Web UI portion, see the
**Configuring the Application Competitor or OE Part Numbers Table Header
Component** topic[ here]{.mcFormatColor style="color: Blue;"}.

By the end of this configuration in the workbench, there must be a link
established from Interchange application (competitor or OE number
application) object to Part Type (Part Terminology / MPCC / Generic
Article) and a reference established from Interchange application
(competitor or OE number application) object to Vehicle (Base Vehicle /
NAPA Year / VehicleType(CV or PC)).

Below are the steps to configure in the workbench.

Throughout this topic, all the manually created Object Types / Objects
are provided with example IDs for easier understanding. It is up to the
user to either follow the same ID or their own while creating the Object
Types / Objects.

1.  Log in to the workbench, and access the System Setup tab.

```{=html}
<!-- -->
```
2.  Create a new Interchange application (competitor or OE number
    application) object type under an Interchange product object type.

-   For AutoCare solution this may be creating
    \'AC\_PIESInterchangeApplication\' under \'AC\_PIESInterchangeItem\'
-   For NAPA solution this may be creating
    \'NAPA\_InterchangeApplication\' under \'NAPA\_InterchangeProduct\'
-   For TecDoc solution this may be creating
    \'TD\_DS\_OENumberApplication\' under \'TD\_DS\_OENumber\' and/or
    \'TD\_DS\_CompetitorNumberApplication\' under
    \'TD\_DS\_SupplierCompetitorNumber\'

Below is an example of a created OE Number application for the TecDoc
solution.

![](../../Resources/Images/Competitor%20OE%20Number/71.png)

3.  Define the newly created Interchange application object type as
    valid Product Type in the following Classification Link Type.

-   For AutoCare solution this may be defining
    \'AC\_PIESInterchangeApplication\' as valid Product Type to
    \'AC\_ProductToPartTerminology\' Classification Link Type
-   For NAPA solution this may be defining
    \'NAPA\_InterchangeApplication\' as valid Product Type to
    \'NAPA\_ProductToMPCC\' Classification Link Type
-   For TecDoc solution this may be defining
    \'TD\_DS\_OENumberApplication\' and/or
    \'TD\_DS\_CompetitorNumberApplication\' as valid Product Type to
    \'TD\_SupplierArticleToGenericArticle\' Classification Link Type

Below is an example of OE Number application being defined as the valid
Product Type to \'TD\_SupplierArticleToGenericArticle\' Classification
Link Type.

![](../../Resources/Images/Competitor%20OE%20Number/72.png)

4.  Define the created Interchange application object type as valid
    Source Type in the following Classification Reference Type.

-   For Autocare solution this may be defining
    \'AC\_PIESInterchangeApplication\' as valid Source Type to
    \'AC\_ACESApplicationToBaseVehicle\' Classification Reference Type
-   For NAPA solution this may be defining
    \'NAPA\_InterchangeApplication\' as valid Source Type to
    \'NAPA\_ApplicationToYear\' Classification Reference Type
-   For TecDoc solution this may be defining
    \'TD\_DS\_OENumberApplication\' and/or
    \'TD\_DS\_CompetitorNumberApplication\' as valid Source Type to
    \'TD\_SupplierArticleToVehicleType(CV)\' and/or
    \'TD\_SupplierArticleToVehicleType(PC)\' Classification Reference
    Type

Below is an example of OE Number application object type being defined
as the valid Source Type to \'TD\_SupplierArticleToVehicleType(CV)\'
Classification Reference Type.

![](../../Resources/Images/Competitor%20OE%20Number/73.png)

5.  Define the Interchange (Competitor / OENumber) product object type
    as valid Source Type and valid Target Type in the following Product
    Reference Type.

-   Define \'AC\_PIESInterchangeItem\' object type as valid Source Type
    and valid Target Type to \'AC\_PartRelation\' Product Reference
    Type.
-   Define \'NAPA\_InterchangeProduct\' object type as valid Source Type
    and valid Target Type to \'NAPA\_PartRelation\' Product Reference
    Type.
-   Define \'TD\_DS\_OENumber\' and \'TD\_DS\_SupplierCompetitorNumber\'
    object type as valid Source Type and valid Target Type to
    \'TD\_PartRelation\' Product Reference Type.

Below is an example of OE Number object type being defined as the valid
Source Type and valid Target Type to \'TD\_PartRelation\' Product
Reference Type.

![](../../Resources/Images/Competitor%20OE%20Number/74.png)

6.  Add the Interchange (Competitor / OENumber) product object type to
    \'Part\' aspect in Automotive - Application Model.

-   For the AutoCare solution, this may be \'AC\_PIESInterchangeItem\'
-   For the NAPA solution, this may be \'NAPA\_InterchangeProduct\'
-   For the TecDoc solution, this may be
    \'TD\_DS\_SupplierCompetitorNumber\' or \'TD\_DS\_OENumber\'

Below is an example of OE Number application object type being added to
\'Part\' aspect in Automotive - Application Model.

![](../../Resources/Images/Competitor%20OE%20Number/75.png)

7.  Add the created Interchange application object type to
    \'Application\' aspect in Automotive - Application Model.

-   For the AutoCare solution, this may be
    \'AC\_PIESInterchangeApplication\'
-   For the NAPA solution, this may be \'NAPA\_InterchangeApplication\'
-   For the TecDoc solution, this may be \'TD\_DS\_OENumberApplication\'
    and/or \'TD\_DS\_CompetitorNumberApplication\'

Below is an example of OE Number object type being added to
\'Application\' aspect in Automotive - Application Model.

![](../../Resources/Images/Competitor%20OE%20Number/76.png)
