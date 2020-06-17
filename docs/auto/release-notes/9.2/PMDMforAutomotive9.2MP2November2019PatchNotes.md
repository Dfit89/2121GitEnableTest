---
description: 'Automotive Solution: PMDM for Automotive 9.2 MP2 November
  2019 Patch Notes'
title: PMDM for Automotive 9.2 MP2 November 2019 Patch Notes
---

PMDM for Automotive 9.2 MP2 Patch Notes {#pmdm-for-automotive-9.2-mp2-patch-notes .MPN}
=======================================

Release Date: November 22, 2019 {#release-date-november-22-2019 style="text-align: center;"}
-------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST- 3843Added support to handle Class and
VehicleToClass tables for VCdb import and Easy Setup

Class.txt and VehicleToClass.txt are files available within the AutoCare
VCdb zip file. These txt files contain Class information for a vehicle.
With this Class information, the user can distinguish whether the
vehicle is a Light-Duty, Medium-Duty, or Heavy-Duty vehicle. Previously,
the VCdb Importer did not handle Class.txt and VehicleToClass.txt files,
and the AutoCare data model had no support for them. Now, the AutoCare
Easy Setup and VCdb Importer has been updated to handle Class.txt and
VehicleToClass.txt files.

1.  Run step 1 of the Automotive - AutoCare Model Easy Setup to:

-   Create a new Description attribute called AC\_VCdbClass and make it
    valid for Vehicle classification object
-   Create a new LOV called AC\_Class and make it referenced for
    AC\_VCdbClass attribute

2.  The VCdb Importer has been updated to do the following when a VCdb
    file is imported:

-   Create LOV values for Class LOV using the values provided in the
    Class.txt file
-   Populate the AC\_VCdbClass attribute on the Vehicle object by
    getting the Vehicle ID to match the Class ID in the
    VehicleToClass.txt file

PRODOC note: RDCUST- 3844Updated Easy Setup and VCdb Importer to handle
VehicleTypeGroup.txt file

VehicleTypeGroup.txt is a file available within the AutoCare VCdb zip
file that carries information on a grouping of vehicle types.
Previously, the VCdb Importer did not handle VehicleTypeGroup.txt file
and the AutoCare data model had no support for grouping the vehicle
types, thus creating many vehicle type objects below the Vehicles root
node. Now, the VCdb Importer has been updated to handle the
VehicleTypeGroup.txt file that allows grouping of the vehicle types.

1.  Run step 1 of the Automotive - AutoCare Model Easy Setup to:

-   Create a new \'Vehicle Type Group\' object type and move the
    existing AC\_VehicleType object type to be a child of the new
    \'Vehicle Type Group.\'

2.  The VCdb Importer has been updated to:

-   Create the Vehicle Type Group in the VCdb classification based on
    the VehicleTypeGroup.txt file
-   Create Vehicle Type objects below the new Vehicle Type Groups based
    on the VehicleType.txt file to match the VehicleTypeID to the
    VehicleTypeGroupID

Below is a screenshot displaying the updated Vehicles classification
that includes vehicle type groups after importing the VCdb file.

![](../../Resources/Images/Release%20Notes/9.2mp2/8.png)

PRODOC note: RDCUST- 3353A new solution that allows users to define
vehicle object type ID that the attribute should be valid for in order
to display the attributes only for the Vehicles / Targets that are
defined

A new conditional attribute called VehicleTypes is introduced on the
reference between the attribute and the Part Type structure to indicate
for which Target Type the attribute is applicable. With this, a new
Vehicle Types column is available on the classification attribute link
that allows a user to type in one or more vehicle object type ID that
the attribute should be valid for to display the attributes only for the
vehicles / targets that are defined. If this field is left empty, then
the attribute is valid for all vehicles / targets.

To create the VehicleTypes conditional attribute and make it valid for
\'Classification attribute validation\' link type, run step 1 for one of
the standards\' (AutoCare/NAPA/TecDoc) Automotive Model Easy Setup.

PRODOC note: RDCUST- 3607Added support to handle Style and PartTypeStyle
tables for PAdb import, PIES import, and PIES export

PartTypeStyle.txt and Style.txt are files available within the AutoCare
PAdb zip file that holds Style data. Previously, the PAdb Importer did
not handle PartTypeStyle.txt and Style.txt files, and the AutoCare data
model had no support for them. Now, the PAdb importer has been updated
to handle PartTypeStyle.txt and Style.txt files.

1.  The PAdb Importer has been updated to:

-   Create a new Specification attribute called Style (ID=
    AC\_PAdb\_Style) and make it valid for PIES Item
-   Create a new List Of Values called AC\_PAdb\_Style\_LOV, make it
    used by AC\_PAdb\_Style attribute, and populate the LOV with values
    based on the Style.txt file

```{=html}
<!-- -->
```
-   Evaluate the PartTypeStyle.txt file to determine which Part Type to
    link the AC\_PAdb\_Style attribute to, and also filter the LOV
    values depending on which Part Type the attribute is linked to

2.  The PIES Importer has been updated to retrieve the StyleID value
    available within the \<ProductAttribute\> element and populate the
    AC\_PAdb\_Style attribute on the PIES Item with this value.
3.  The PIES Exporter has been updated to retrieve the ID of the LOV
    value populated in the AC\_PAdb\_Style attribute available within
    the PIES Item and include it in the StyleID field in the
    \<ProductAttribute\> element of the exported PIES file.

PRODOC note: RDCUST- 3773, 3771, 3776, 3767, 3770, 3772Added support for
import and export of PIES 7.1 file

Updated AutoCare Easy Setup, PIES Importer, and PIES Exporter to handle
import and export of PIES 7.1 version.

The AutoCare PIES Exporter now provides an option to select between PIES
6.5, 6.7, 7.0, and 7.1 versions in the \'Version\' parameter within the
\'Select Format\' dialog as shown below. For more information, see the
AutoCare PIES Exporter topic of the Automotive Reference Guide[
here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/9.2mp2/1.png)

Existing implementations must run step 1 of the Automotive - AutoCare
Model Easy Setup to implement the following changes:

-   PRODOC note: BOND RDCUST-3773Create three new Packaging Segment
    attributes under the \'PIES Packaging Segment PACK\' attribute group
    (ID: AC\_PIESPackagingSegmentPACK) valid for \'AC\_PIESPackage\'
    object types.

```{=html}
<!-- -->
```
-   ID: AC\_PIES\_PACKShippingHeight with STEP Name \'Shipping Height\'
-   ID: AC\_PIES\_PACKShippingLength with STEP Name \'Shipping Length\'
-   ID: AC\_PIES\_PACKShippingWidth with STEP Name \'Shipping Width\'

```{=html}
<!-- -->
```
-   PRODOC note: BOND RDCUST-3773Change the STEP Name of the following
    three existing Packaging Segment attributes available under the
    \'PIES Packaging Segment PACK\' attribute group (ID:
    AC\_PIESPackagingSegmentPACK).

```{=html}
<!-- -->
```
-   ID: AC\_PIES\_PACKHeight is changed from the old STEP Name
    \'Height\' to the new STEP Name \'Merchandising Height\'
-   ID: AC\_PIES\_PACKWidth is changed from the old STEP Name \'Width\'
    to the new STEP Name \'Merchandising Width\'
-   ID: AC\_PIES\_PACKLength is changed from the old STEP Name
    \'Length\' to the new STEP Name \'Merchandising Length\'

```{=html}
<!-- -->
```
-   PRODOC note: BOND RDCUST-3771Change attribute with
    ID=AC\_PIES\_ITEMQuantityPerApplication to use Text validation
    instead of Number validation.
-   PRODOC note: BOND RDCUST-3770A new attribute (ID:
    AC\_PIES\_INTEVMRSBrandID) for PIES Interchange under \'PIES Part
    Interchange Segment INTE\' attribute group (ID:
    AC\_PIESPartInterchangeSegmentINTE) valid for PIES Interchange Item
    object type (ID: AC\_PIESInterchangeItem).
-   PRODOC note: BOND RDCUST-3770A new attribute (ID:
    AC\_PIES\_ITEMVMRSBrandID) for PIES Item created under \'PIES Item
    Segment ITEM\' attribute group (ID: AC\_PIESItemSegmentITEM) valid
    for PIES Item object type (ID: AC\_PIESItem).
-   PRODOC note: BOND RDCUST-3772A new attribute (ID:
    AC\_PIES\_PRCE\_PriceMultiplier) for Price Segment created under
    \'PIES Price Segment PRCS\' attribute group (ID:
    AC\_PIESPriceSegmentPRCS). The attribute is added to the
    AC\_PIES\_PRCE data container type that is valid to PIES Item.
-   PRODOC note: BOND RDCUST-3774A new Sold Separately (ID =
    AC\_PIES\_KITSSoldSeparately) attribute for Kits Segment created
    under the \'PIES Kit Segment KITS\' attribute group (ID:
    AC\_PIESKitSegmentKITS). The attribute is made valid to the
    \'AC\_PIESItemToKitComponentItem\' product reference type and is
    visible for PIES Item as metadata attribute.

```{=html}
<!-- -->
```
-   PRODOC note: BOND RDCUST-3836Create four new attributes for PIES
    Item under the \'PIES Part Interchange Segment INTE\' attribute
    group (ID: AC\_PIESPartInterchangeSegmentINTE). The attributes are
    made valid to the \'AC\_PIESInterchange\' product reference types
    and are visible for PIES Item as metadata attributes.

```{=html}
<!-- -->
```
-   ID: AC\_PIES\_INTEInterchangeQuantity with STEP Name \'Interchange
    Quantity\'
-   ID: AC\_PIES\_INTEInterchangeQuantityUOM
-   ID: AC\_PIES\_INTEItemEquivalentUOM
-   ID: AC\_PIES\_INTEReferenceItem with STEP Name \'Reference Item\'

PRODOC note: RDCUST- 3867Added a new field called \'Validator max
length\' in the Detailed Information dialog

Previously, it was not possible in the Mapping Web UI to see the length
of an attribute, thus there is no warning when a value that may be too
long is mapped to an attribute with a shorter maximum length. Now, a new
field called \'Validator max length\' has been added in the Detailed
Information dialog that gets displayed when the user clicks to check the
detailed validity match information in any of the mapping plugins. This
newly added line validates whether the source input exceeds the target
input length.

![](../../Resources/Images/Release%20Notes/9.2mp2/5.png)

PRODOC note: RDCUST- XXXXAdded support to view the reverse of the
configured reference type direction within the Reference Delegation
Screen

When the Reference Delegation Screen is configured with a reference type
and a screen ID, it will follow the reference from the source object to
its target, and display the children objects of the target in the
configured screen. In other words, it allows the user to select an
object, follow a reference on that object, and display any screen
configured for the target\'s children objects of the reference.
Previously, this feature required the Reference Type to have the source
object as the valid source type, and the target object as the valid
target type. Now, a new parameter called **Reverse Reference** is
introduced within the Reference Delegation Screen Properties window
(accessed in the design mode). Checking this parameter will follow the
reference on the selected object, and display any screen configured for
the children objects of the target that is referenced by the source
object. This feature is useful to view objects that are available in the
Referenced By tab of the workbench.

![](../../Resources/Images/Release%20Notes/9.2mp2/6.png)

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**[
to:hotfix/379/issue-379814-HOTFIX-3605.spr]{.commandfont}

PRODOC note: RDCUST- xxxxAdded support to AutoCare data model to handle
Qualifier with multiple parameters

In an ACES file, an application can have the same qualifier ID with
multiple qualifier parameters. Previously, the ACES importer would only
store one of the qualifier parameters in the \'ACES Application To
Qualifier\' classification reference and ignore the other parameters.
Now, the following changes have been implemented:

-   Updated ACES Importer to handle qualifiers with multiple parameters
    listed with the same qualifier ID for the same application.
-   Easy Setup creates a new Qdb Order (ID = AC\_QdbOrder) attribute
    that is valid for ACES Application To Qualifier classification
    reference type. The value of this attribute gets populated by a
    numeric value in accordance with the order in which the qualifiers
    are listed in the import file.
-   Updated ACES Exporter to take into consideration the new Qdb Order
    attribute for the qualifier with multiple parameters within the same
    application.
-   Updated ACES Application Qualifiers table header component (usually
    configured in the Application Manager screen and Application Editor
    Screen) to display the same qualifier with multiple parameters
    correctly.

**Run step 1 & 2 of the Automotive - AutoCare Model Easy Setup to create
the Qdb Order (ID = AC\_QdbOrder) attribute.**

PRODOC note: RDCUST- XXXXA new feature added in the Data Onboarding
solution to create new parent target objects

The earlier versions of the Data Onboarding solution allowed the user
create a new Target object. But this was restricted in a way that the
new Target objects had to have an existing parent object, as well as
have an existing reference established from the source parent object to
the target parent object.

A new Mapper Setup parameter has been added, that lets the user define
an automatic creation of the Target object, parent to the Target object,
and if required, a whole new hierarchy where the Target object should be
created below. The new parameter called **Target Hierarchy** (shown
below) is available within the Setup tab of Onboarding Mappings Details
Screen (displayed when the Mapper Configuration setup entity is
selected). that allows the user to define certain criteria that will, in
turn, create Target object hierarchy when the Mapper Configuration setup
entity is executed. This feature becomes more useful when users are
importing a large number of objects (Source Objects), and the created
Target objects are to be assorted in various folders.

The Target Hierarchy parameter has been designed to check for an
existing object in the system, and a new object is created only if there
are no similar object available in the system. The system would place
the Target object in the suitable existing object if the object is
already existing in the system. This ensures that there is no duplicate
object created. The way the name and ID structure of the newly created
object is to be populated can be well defined within this parameter.

![](../../Resources/Images/Release%20Notes/9.2mp2/7.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST- 3847Updated the Faceted Search Node Picker Dialog
Node List to have Multi Edit Display Mode as default Display Mode

Previously, the Faceted Search Node Picker Dialog Node List had Table
Display Mode as default display mode and users were not able to access
checkboxes to select from the result list to create applications. Now,
the Faceted Search Node Picker Dialog Node List is changed to include
Multi Edit Display Mode as the default display mode that displays the
checkbox thereby letting users select from the search list.

PRODOC note: RDCUST- 3083Updated the Part Number References and Part
Number Suggestions component to display warnings when the user deletes a
Part Number

\'Part Number References,\' \'Part Number Suggestions,\' \'Advanced Part
Number References,\' and \'Advanced Part Number Suggestions\' are the
components that let the user add / delete the part numbers from the
referenced list or suggestion list. Previously, when users tried to
remove a part number from the reference list or suggestions list, the
part number was removed without displaying a warning dialog. Now, to
avoid the accidental deletions of the part numbers, the \'Part Number
References,\' \'Part Number Suggestions,\' \'Advanced Part Number
References,\' and \'Advanced Part Number Suggestions\' components are
updated to display a warning dialog, that requests users to confirm the
deletion when the user clicks the Remove button.

![](../../Resources/Images/Release%20Notes/9.2mp2/2.png)

PRODOC note: RDCUST- 3841Updated Bulk Application Updates component
names and its description texts for Application Editor and Application
Manager

The Bulk Application Updates component names and its description texts
have been updated in the Application Editor screen and Application
Manager screen for Web UI to avoid confusion for users. The changes are
as follows:

  Old Name                          New Name                                     Description
  --------------------------------- -------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Bulk Applications Updates         (no change)                                  This action can be added to an Application Editor screen and Application Manager screen. It lets the user configure multiple Business Actions within this action button. Further configuration is required to add Business Actions.
  Bulk updates                      Business action(s) for Bulk Update(s)        This parameter lets users add multiple Business Actions that gets displayed as radio buttons to select when the user clicks the Bulk Applications Updates button.
  Bulk Application Update           Initiate Business Action on Application(s)   This component when configured with a Business Action will start a background process, which will call a Business Action for each selected application.
  Parameters                        Node Selector Dialog                         Select a dialog that needs to display when the user clicks on the action button.
  Node Picker Parameter             (no change)                                  Node Picker for selecting Assembly or Part.
  Faceted Search Dialog parameter   (no change)                                  Faceted search for selecting Assembly or Part.
  String Parameter                  (no change)                                  String for selecting Assembly or Part.

PRODOC note: NGK- 560Corrected an issue in the Object to Object Mapping
plugin for the Parent Node parameter

Previously, the Object to Object Mapping plugin did not allow a user to
add and save a classification folder within the Parent Node parameter
when the Mapping type = Reference is used. Now, the Object to Object
Mapping plugin is corrected to allow users to configure any
classification folder within the Parent Node parameter.

![](../../Resources/Images/Release%20Notes/9.2mp2/4.png)

PRODOC note: RDCUST- xxxxFixed Unexpected error generated in the
Application Comment table header component when configured in the Table
Display Mode

Previously, when working in the Application Comment table header
component, an Unexpected error (java.lang.ClassCastException) would be
generated if the user attempted to edit fields in Table Display Mode.
This has been corrected so that now there is a possibility to edit
fields in Table Display Mode as well as in Multi Edit Display Mode.

PRODOC note: RDCUST- XXXXUpdated the Object to Object Mapping plugin and
the Application Mapping plugin to allow Reference Link Types to be
selected

Previously, the mapper rows created within the Object to Object Mapping
plugin and the Application Mapping plugin only allowed Reference Types
to be selected as the Source and/or Target, but not Reference Link
Types. Now, the plugins have been updated to also allow selecting
Reference Link Types that are available within the system.

PRODOC note: RDCUST- XXXXCorrected an issue that would occur if multiple
Suggested Part Number table header components were configured in the
Application Manager results table

Previously, if one Suggested Part Number table header component was
configured in the Application Manager search results table, then the
header component would work properly. But if multiple Suggested Part
Number table header components were added, then none of the part number
suggestions would work. Now, a new UUID parameter has been added to the
Suggested Part Number table header component to support multiple
instances for headers of the same type.

![](../../Resources/Images/Release%20Notes/9.2mp2/9.png)

PRODOC note: NGK-396Updated \'Value editor\' dialog to correctly
function in the \'Application Condition Header - Group\' table header
component

With the \'Application Condition Header - Group\' table header component
configured within the Application Manager screen, when the user clicks
on the condition attributes cell, the \'Value editor\' dialog opens up
displaying the condition attributes and/or references. Within this
dialog the user can add new condition attributes and/or references
field, add values in the field, or even edit the existing values
populated in the field. Previously, the Cancel button available within
the dialog did not directly close the dialog but rather exhibited
strange behavior that required the user to click the Cancel button
multiple times to close the dialog. Now, the cancel button available
within this editor is corrected to facilitate the closing of this
dialog.

### AutoCare

PRODOC note: RDCUST- 3817Updated PIES Exporter to handle ™, Ł, Ǆ, ©, and
® special characters

Previously, PIES Exporter did not handle some special characters like ™,
Ł, Ǆ, ©, and ®, and that caused validation to fail indicating that there
was invalid byte 1 of 1-byte UTF-8 sequence. PIES Exporter has been
updated to validate these special characters and not to display any
validation errors.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**[
to:hotfix/378/issue-378786-HOTFIX-3555.spr]{.commandfont}

PRODOC note: RDCUST- 3328Updated Part Type Search card in Application
Manager screen to no longer display any irrelevant part type when the
user types in the typeahead field

The Root Nodes parameter available within the Part Type Search Box
Properties allows for the restriction of root nodes to be used within
the Part Type search box when searching / filtering for a Part Type.
Previously, despite the root node(s) being defined in the Root Node
parameter, the typeahead field in the Part Type search box would suggest
part types that would exist even outside the root node. This was
intentionally designed to perform this way considering the performance
factor of the Application Manager screen. Now, considering the factors
like the user\'s need and system performance, a new parameter \'Use Root
Nodes In Typeahead\' is introduced within the Part Type Search Box
Properties to provide an option that suggests the part types in the
typeahead field either within or beyond the defined root node.

![](../../Resources/Images/Release%20Notes/9.2MP1/6.png)

PRODOC note: CARDON-184Corrected the problem with exporting PIES Items
with Description Segment attributes

Previously, when a PIES Item with Description Segment attributes were
included in the PIES 6.5 version export, the export would generate a
STEPXML file instead of a zipped PIES file. Now, this issue is corrected
to generate a zipped PIES file in every PIES export.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/378/issue-378584-HOTFIX-3550.spr]{.commandfont}

PRODOC note: RDCUST-3823Corrected the Application Suggestion Info icon
(![](../../Resources/Images/Release%20Notes/92RN4.png)) configured
within the Application Suggestions component to display the suggestion
information only once

Previously, the info icon
(![](../../Resources/Images/Release%20Notes/92RN4.png)) configured
within the Application Suggestions component was wrongly displaying the
same suggestion information twice. Now, this issue has been resolved to
correctly display the suggestion information only once.

PRODOC note: RDCUST- 3658Corrected the way the Easy Setup action handles
the existing AutoCare LOVs in the system

Step 1 of the AutoCare Easy Setup creates all of the LOVs below the
AutoCare LOV Group (ID = AC\_LOV). After the LOVs are created by Easy
Setup, most of the LOV Name and/or Maximum Length will get updated by
VCdb import, PCdb import, or a user can manually change the name or
validation of the LOV. Previously, when the AutoCare Easy Setup was run
again, it would revert the changes that were updated by VCdb import,
PCdb import, or the user changes. Now, Easy Setup has been updated to no
longer overwrite the updates done by the reference data importer or
manual user changes.

PRODOC note: Cardone-186Corrected the way the PIES Importer handles
identical Market Copy that are referenced by the same Brand

Previously, importing PIES files through the PIES Importer was failing
at the Conversion state with a stacktrace error if the identical Market
Copy that should be referenced by the same Brand was encountered. Now,
this has been corrected so that the presence of duplicate MarketCopyType
with different MarketCopySubCodeReference will create separate objects
for each MarketCopyType.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**[
to:hotfix/379/issue-379025-HOTFIX-3569.spr]{.commandfont}

PRODOC note: RDCUST- 3866Updated PIES Exporter to include correct
RecordSequence value that is retrieved from the
AC\_PIES\_MKTC\_RecordSequence attribute stored on the PIES Market Copy
object

A Record Sequence element is available within the Market Copy Segment to
enable a sender of data to convey the order in which a sequence of
content should be published. The record sequence identifies the order in
which a record should appear if multiple Content records are being sent
for a Market Copy Code or Sub Code. The RecordSequence value is stored
in the AC\_PIES\_MKTC\_RecordSequence attribute on the PIES Market Copy
object. Previously, the PIES Exporter was setting the wrong
RecordSequence number for Market Copy. Now, the PIES Exporter is updated
to retrieve the correct RecordSequence value from the
AC\_PIES\_MKTC\_RecordSequence attribute that is stored on the Market
Copy object.

PRODOC note: RDCUST- XXXXUpdated ID pattern of PIES Interchange object
to only be based on brand and part number

Changed the way the PIES Importer handled the ID pattern of the PIES
Interchange objects so that it would no longer include the Source Part
Number information in the ID hash value. Previously, the PIES Importer
was creating IDs with the pattern AC\_PIESInterchangeItem\_+
hash(Interchange Type Code + Brand AAIAID + Interchange Part Number +
Quality Grade Level + Interchange Notes + Internal Notes + Language Code
+ Source Part Number). Inclusion of the Source Part Number (the part
that can replace the interchange) in the uniqueness of the ID was
causing the interchange part to not be useable by any other parts. This
caused a new interchange to be created for every part that it can be
replaced by (one-one relationship) while it should be that an
interchange part should be interchangeable with many part numbers
(one-many relationship). Now, the PIES Importer is updated to generate a
unique ID pattern with the absence of source Part Number information.

PRODOC note: RDCUST- XXXXCorrected the anomalies within the UOMs that
were provided by AutoCare

The AutoCare Easy Setup has been updated to rectify some incorrect PAdb
UOM Codes that were provided by AutoCare and that were contrary to the
information provided by ANSI or UNECE. Previously, step 1 of the
AutoCare Easy Setup was creating the initial PAdb UOMs (if they did not
already exist in STEP) and was populating the PAdb UOM Code, PAdb UOM
Description, and PAdb UOM Label attributes. After the UOMs were
initially created by Easy Setup, the PAdb importer looked for existing
UOMs and updated the existing units, PAdb UOM Code, Description, and
Label.

After the PAdb importer updated the PAdb UOM, Description, or Label, any
subsequent running of Easy Setup was updating some units once again.
This caused some anomalies to occur.

Now, the Easy Setup has been modified so that it does not not update
PAdb UOMs if changes have been made after their initial creation. Also,
if new UOMs are introduced in the PAdb files in the future, then Easy
Setup will be updated to create those new UOMs.

**Existing Implementations:** The following manual changes should be
done before running Easy Setup

1.  Go to the following Unit IDs and remove the values for PAdb UOM
    Code, PAdb UOM Description, and PAdb UOM Label:

-   unece.unit.MAW
-   unece.unit.FS
-   unece.unit.IU
-   unece.unit.MLT
-   unece.unit.MTS
-   unece.unit.C45
-   unece.unit.AMH
-   unece.unit.IA
-   unece.unit.HJ
-   unece.unit.CMK
-   unece.unit.ANN
-   unece.unit.4K
-   unece.unit.40
-   unece.unit.41
-   unece.unit.4O

2.  If there are no attribute values using the following units, then
    Force Delete these units:

-   Under Computer Storage and Memory \> delete unit ID = GB (Easy Setup
    will create a unit with ID = unece.unit.E34)
-   Under Computer Storage and Memory \> delete unit ID = TB (Easy Setup
    will create a unit with ID = unece.unit.E35)
-   Under Mass \> delete unit ID = lbs (Easy Setup will update existing
    unit with ID = unece.unit.LBR)
-   Under Mass \> delete unit ID = ton (Easy Setup will create a unit
    with ID = unece.unit.STN)
-   Under Volume Flow Rate \> delete unit ID = CFS (Easy Setup will
    create a unit with ID = unece.unit.E17)
-   Under Volume Flow Rate \> delete unit ID = CMM (Easy Setup will
    create a unit with ID = unece.unit.G53)
-   Under Volume Flow Rate \> delete unit ID = GPHI (Easy Setup will
    create a unit with ID = unece.unit.K27)
-   Under Density and Thickness \> delete unit ID = mil (Easy Setup will
    create a unit with ID = unece.unit.77)
-   Under Density and Thickness \> delete unit ID = thou (Easy Setup
    will create a unit with ID = unece.unit.MIL)
-   Under Power \> delete unit ID = INHG (Easy Setup will create a unit
    with ID = unece.unit.F79 below new Mechanics unit group)
-   Under Power \> delete unit ID = MAH (Easy Setup will create a unit
    with ID = unece.unit.E09 below Electricity and Magnetism unit group)

**Run step 1 of AutoCare Easy Setup to update or recreate these units.**

Corrected PIES export of Packaging Segment

Previously, if more than one PIES Item with Packaging information were
getting exported, the Packaging information would incorrectly get
grouped within the first PIES Item in the export. Now, the PIES Exporter
has been updated to correctly export the Packaging information within
the PIES Item that it belongs to.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**[
to:hotfix/376/issue-376277-HOTFIX-3511.spr]{.commandfont}

Corrected PIES export of Interchange parts

Corrected an issue where Interchange parts that were included in the
PIES export were wrongly exported and displayed more than once within
the export results. Now, the PIES Exporter has been corrected to
properly handle the Interchange parts and are displayed correctly in the
exported PIES file.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**[
to:hotfix/376/issue-376215-HOTFIX-3509.spr]{.commandfont}

### NAPA

PRODOC note: RDCUST- 3658Corrected the way the Easy Setup action handles
the existing NAPA LOVs in the system

Step 1 of the NAPA Easy Setup creates all of the LOVs below the NAPA LOV
Group (ID = NAPA\_LOVGroup). After the LOVs are created by Easy Setup,
most of the LOV Name and/or Maximum Length will get updated by NAPA
Vehicle import or NAPA Translation import, or a user can manually change
the name or validation of the LOV. Previously, when the NAPA Easy Setup
is run again, it was reverting the changes that were done by NAPA
Vehicle import, NAPA Translation import, or when a user makes changes.
Now, the Easy Setup is updated to no longer overwrite the updates done
by the NAPA Vehicle import or NAPA Translation import, or any user
changes on the LOV.

### TecDoc

PRODOC note: RDCUST- 3658Corrected the way the Easy Setup action handles
the existing TecDoc LOVs in the system

Step 1 of the TecDoc Easy Setup creates all of the LOVs below the TecDoc
LOV Group (ID = TD\_Top\_Level\_Lov\_Group). After the LOVs are created
by Easy Setup, most of the LOV Name and/or Maximum Length will get
updated by TecDoc Reference Data import, or a user can manually change
the name or validation of the LOV. Previously, when the TecDoc Easy
Setup was run again, it was reverting the changes that were done by
TecDoc Reference Data, or when a user makes changes. Now, the Easy Setup
is updated to no longer overwrite the updates done by the TecDoc
Reference Data or any user changes on the LOV.

PRODOC note: NGK- 582Corrected \'Part Number References\' and \'Advanced
Part Number References\' components to allow the creation of new
competitor and/or OE part numbers when there are multiple manufacturers
with the same name in the system

One of the many features of \'Part Number References\' and \'Advanced
Part Number References\' components is to allow users to create a new
competitor and/or OE part number for existing manufacturers and
simultaneously reference them to a selected part. Previously, when users
tried to create a new competitor and/or OE part number, the presence of
the same manufacturer name that exists below multiple Product Lines
would display an error (as shown below) and prevented the new competitor
or OE number to get created. Now, this limitation has been corrected so
that the new competitor or OE number will still get created even though
the same manufacturer name exists below different Product Lines.

![](../../Resources/Images/Release%20Notes/9.2mp2/3.png)

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**[
to:hotfix/377/issue-377768-HOTFIX-3531.spr]{.commandfont}

PRODOC note: NGK- 582Corrected an issue in Application Manager where
missing applications were not found correctly

Previously, missing linkages (applications) were not found correctly in
the linking (application) manager when an Engine Code condition had been
set. This bug has been resolved and missing linkages are now found and
displayed correctly in the linking manager when conditions have been set
on a linkage.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: RDCUST- XXXXApplication Mapping Plugin topic

The **Application Mapping Plugin** topic has been added to the new
**Data Onboarding Solution** section of the Automotive Reference Guide.

PRODOC note: RDCUST- XXXXNew Application Editor Screen documentation

The new **Application Editor Screen** section addresses using and
configuring the Application Editor Screen. It also includes the details
on Faceted Search window and couple of PMDM for Automotive specific
action buttons to help understand the area of usage of these action
buttons. The documents can be found within the Automotive Reference
Guide[ here]{.mcFormatColor style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.23.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.2 MP3
baseline recipe:

[to:step/trailblazer/step-9.2-mp3.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system cannot be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
