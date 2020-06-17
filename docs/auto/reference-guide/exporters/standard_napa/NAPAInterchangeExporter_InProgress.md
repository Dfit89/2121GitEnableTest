---
description: 'Automotive Solution: Describes how to '
title: '\[%=Heading.AnyLevel%\]'
---

NAPA Interchange Exporter
=========================

PRODOC note: MEDU RDUCST-2678, 2681

The NAPA Interchange Exporter is used to export interchange data that
resides in a NAPA product hierarchy. Users can select an object from the
NAPA product hierarchy, and the NAPA Interchange objects beneath the
selected object (both child objects and linked objects) will be
exported. The export file is then available in the NAPA Interchange
format.

A new \'NAPA Interchange Exporter\' format has been implemented,
allowing for the export of Interchanges. The NAPA Interchange Exporter
will export interchanges that are referenced by a NAPA Product using the
\'Product To Interchange Product\' reference. The exporter uses a
parameter to indicate which Product Line to export. This way when a
Product is linked to multiple MPCCs, an interchange export is possible.
If a Product Line is not specified, then all Product Lines will be
included in the exported file with a row for each Product Line for the
same Part Number. If a Product Line is specified in the parameter, then
the exported file will only contain part numbers and interchanges
relevant for the chosen Product Line.

Prerequisites
-------------

NAPA Data Model Requirements

The exporter requires applications be stored in the standard NAPA data
model.

NAPA Product Requirements

The NAPA Product MPCC is expected to have an ID structure prefixed with
NAPA\_MPCC\_, and the NAPA Product is expected to have the following ID
structure: NAPA\_Product\_\[Line Abbrev\]\[PartNumber\] (i.e.,
NAPA\_Product\_FIL1515). When a NAPA Product is created, the NAPA Part
Number attribute (NAPA\_PartNumber) must be populated with the Part
Number value, as this attribute value is used to the determine the Part
Number in the NAPA Interchange Exporter.

Because some Product Lines only have two characters, the NAPA Product
Number, if used without the overlying ID structure, might create an
inconsistent pattern when trying to use the Product Number for the ID.

Object Type Requirements

The following object types must exist within STEP: ExportBaselineRoot
(Alternate Classification) and ExportBaselineAsset (Assets). As of the
Automotive 8.3 release, these object types are created automatically
when Easy Setup is run via System Setup \> Component Models \>
Automotive - NAPA Model \> Right-click Automotive - NAPA Model \> 1.
Configure NAPA Data Model.

 

MEDU: Per PAKA we moved interchanges from the classification hierarchy
to the product hierarchy. Do not have to have an application\... just a
product. We create a reference from the product to the (Product to
Interchange Product) also (Product to MPCC references)

 
