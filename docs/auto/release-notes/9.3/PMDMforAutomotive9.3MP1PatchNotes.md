---
description: 'Automotive Solution: PMDM for Automotive 9.3 MP1 March
  2020 Patch Notes'
title: PMDM for Automotive 9.3 MP1 March 2020 Patch Notes
---

PMDM for Automotive 9.3 MP1 Patch Notes {#pmdm-for-automotive-9.3-mp1-patch-notes .MPN}
=======================================

Release Date: March 06, 2020 {#release-date-march-06-2020 style="text-align: center;"}
----------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-3921Updated the Application Manager Screen to
include an option to collapse the search canvas

A new option has been added to collapse the search canvas within the
Application Manager Screen. This provides more screen space to focus on
the search result items.

![](../../Resources/Images/Release%20Notes/9.3MP1/1.jpg)

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/383/issue-383923-HOTFIX-3713.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.3 + Automotive 9.3:**
[to:hotfix/386/issue-386440-HOTFIX-3763.spr]{.commandfont}

New \'Search by Card\' screen

A new Search by Card screen has been added that uses the sync between
search cards functionality to provide an intelligent, easy-to-use search
interface. This makes it possible for the user to narrow down the search
result and see only relevant results. This screen can be configured to
define the most likely used filter groups for the search in the Web UI.
For example, if the user needs to find an object based on the name,
parent hierarchy, or any attribute value, and the search cards are
configured to be available for each of these search criteria in the
Search by Card Screen, then users can refine the list of objects based
on one or more of the available filters.

![](../../Resources/Images/Search%20by%20Card%20Screen/11.png)

The Search by Card screen interface features the following elements:

1.  Configurable title.
2.  Card-based search panel that enables users to narrow down the search
    result and see only relevant nodes.
3.  Saved search tool that enables users to save previously selected
    search criteria with custom names, and then quickly populate
    previously saved search criteria by selecting the name of a saved
    search from the saved search dropdown.
4.  Clear All link that enables users to clear all search criteria and
    all search results.
5.  Search button.
6.  Results table toolbar.
7.  Display Mode that enables users to change the current display mode.

```{=html}
<!-- -->
```
1.  Flip table icon that enables users to change or flip the orientation
    of the table.
2.  Row selection boxes that enables users to select one or more rows
    within the table.

```{=html}
<!-- -->
```
1.  Hyperlinks that, when clicked, navigate users to a specific
    configured screen.

```{=html}
<!-- -->
```
11. A Node List-based results table that displays the search results.
12. Edited items panel containing an expand / collapse arrow, Save, and
    Reset buttons.

```{=html}
<!-- -->
```
1.  Number displaying the total number of search results.

For information about how to configure this screen, see the **Search by
Cards Screen** section within the **Automotive Reference Guide**[
here]{.mcFormatColor style="color: Blue;"}.

New Onboarding Comparison Screen\'

Often in the process of Data Onboarding, a large quantity of data is
imported and onboarded in the system. Sometimes the process requires the
user to preview the changes affecting the Target object before the data
is onboarded. The Onboarding Comparison Screen allows users to preview
the onboarding data, assess each of the changes, and either accept or
reject the changes that will affect the Target object.

The Onboarding Comparison Screen allows users to configure a Mapper
Configuration setup entity and compares the selected Source object with
the Target object in the context of the configured Mapper Configuration
setup entity. With the Source object selected, users can view the
changes affecting the Target object. Also, an option is provided to
partially / fully accept or reject the changes. If the user chooses to
accept full / partial changes, the Mapper Configuration setup entity
will be executed on the Source object and only the selected changes will
be implemented on the Target object.

The Onboarding Comparison Screen features the following elements:

1.  Name of the Source object
2.  Multiple stages for each available Mapping plugin within the
    configured Mapper Configuration setup entity.
3.  An additional stage called Confirm to verify the Onboarding
    selections (detailed in the second screenshot below).
4.  Mapper rows table toolbar.
5.  Number displaying the total number of changes.
6.  Option to select the Mapping plugin containing the Mapper rows.
7.  Permission to auto-update all future changes.
8.  An option to collapse the displayed Mapping plugin.
9.  A column displaying current values in the Target object.
10. A column displaying values in the Source object.
11. A column displaying values that would be populated in the Target
    object when the Onboarding is accepted.
12. Option to select the individual Mapper rows that are to be
    onboarded.
13. An option to abort Onboarding process at any phase.
14. A business action-driven Reject Update button that enables users to
    reject updates.
15. Number displaying the total number of Mapper rows selected in the
    current stage.
16. A preview that enables users to verify the selection.
17. A business action driven Onboard button that executes the selected
    updates.

![](../../Resources/Images/Release%20Notes/9.3MP1/18.png)

![](../../Resources/Images/Release%20Notes/9.3MP1/19.png)

New \'Forward Screen Action\' component

A new Forward Screen Action component has been added that, when
configured as an action button, allows users to reroute an object into
the defined screen. If placed in the Buttons component, the Forward
Screen Action component will route the currently selected product. If
placed in the Actions parameter on a Node List, the Forward Screen
Action component will route the object that is selected in the list.
This component is commonly used within Web UI search screens and the
Node Detail screen.

One common use case of the Forward Screen Action component within the
Automotive solution is to route the selected object to the Onboarding
Comparison Screen. There are no explicit limits on how the component can
be used, but it was created specifically to route the selected object to
the Onboarding Comparison Screen so that the user can compare the
selected Source object with the Target object in the context of the
configured Mapper Configuration setup entity.

![](../../Resources/Images/Data%20Onboarding/183.png)

PRODOC note: RDCUST- 2394Updated Mapping plugins to allow adding
transformations

The Attribute Mapping plugin, Object to Object Mapping plugin,
Concatenator Mapping plugin, and Application Mapping plugin provide
users with an option to create attribute transformations. Previously,
the Create New Transformation
button(![](../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png)),
available within the Mapping plugins, would only create the attribute
transformation, which required the user to configure and define the
functionality of the transformation separately in the workbench. Now, a
New Transformation button is available within the Transformation
Overview dialog that allows users to add transformations for the
existing / newly created attribute transformations.

![](../../Resources/Images/Release%20Notes/9.3MP1/20.png)

PRODOC note: RDCUST- 2394Updated Easy Setup and ACES Importer to handle
AssetItemOrder and AssetItemRef

AssetItemOrder and AssetItemRef tags are available within the AutoCare
ACES file that can be metadata for any asset on an application.
Previously, the ACES Importer did not handle these tags. Now, the ACES
Importer has been updated to handle the information available within the
AssetItemOrder and AssetItemRef tag.

1.  Run step 1 of the **Automotive - AutoCare Model** Easy Setup to:

-   Create two new attributes AC\_PIES\_ASSTAssetItemOrder and
    AC\_PIES\_ASSTAssetItemRef that stores the AssetItemOrder and
    AssetItemRef values respectively. These attributes are made valid
    for the application to asset references so that this can be stored
    as metadata on those references.

2.  The ACES Importer has been updated to:

-   Populate the AC\_PIES\_ASSTAssetItemOrder and
    AC\_PIES\_ASSTAssetItemRef attribute values valid on the application
    to asset reference and displayed when the application record is
    selected.

3.  The ACES Exporter has been updated to include data from
    AC\_PIES\_ASSTAssetItemOrder and AC\_PIES\_ASSTAssetItemRef
    attributes in the exported file.

PRODOC note: RDCUST- 3869Updated Easy Setup and PIES Importer to handle
MarketCopySubCode and MarketCopySubCodeReference

The Market Copy segment is provided in the PIES file and brought into
STEP via the PIES Importer. Previously, the PIES Importer and Exporter
handled the \<MarketingCopy\> segment, but the \'MarketCopySubCode\' and
\'MarketCopySubCodeReference\' XML elements were not handled correctly
within the STEP AutoCare data model. Despite the presence of
MarketCopySubCode and MarketCopySubCodeReference elements within the
PIES import file, the Market Copy was creating all of the Market Copy
objects directly below the Brand level (as shown below).

![](../../Resources/Images/Release%20Notes/9.3MP1/3.png)

To handle the MarketCopySubCode and MarketCopySubCodeReference elements
for the PIES import and export, run step 1 of the **Automotive -
AutoCare Model** Easy Setup to:

-   Create the following new object types:
-   PIES Market Copy Sub Code (ID = AC\_PIESMarketCopySubCode) under
    Parent ID = AC\_PIESMarketCopyReference
-   PIES Market Copy Sub Code Reference (ID =
    AC\_PIESMarketCopySubCodeReference) under Parent ID =
    AC\_PIESMarketCopySubCode

```{=html}
<!-- -->
```
-   Update AC\_PIESMarketCopySubCodeReference object type to be an
    additional parent for AC\_PIESMarketCopy object type (as shown
    below)

![](../../Resources/Images/Release%20Notes/9.3MP1/4.png)

The PIES importer has been updated to:

-   Handle the MarketCopySubCode and MarketCopySubCodeReference elements
    by creating Market Copy Sub Code and Market Copy Sub Code Reference
    objects, then creating PIES Market Copy objects below the Market
    Copy Sub Code Reference objects.

Below is a screenshot displaying the PIES Market Copy object that is
created under the PIES Market Copy Sub Code Reference after importing
the PIES file.

![](../../Resources/Images/Release%20Notes/9.3MP1/6.png)

-   Determine where to create the Market Copy object and where to
    reference it to for MarketCopySubCode.
-   Establish the reference from the Market Copy object to the Asset, if
    there are Digital Assets.
-   Populate the attribute values for the Market Copy object.
-   Establish the reference from the AC\_PIESBrand object to the Market
    Copy object using the AC\_PIEStoMarketCopy reference type.
-   Create the PIES Market Copy object with the ID pattern =
    AC\_MKTC\_\[hash of MarketCopyCode, MarketCopyType,
    MarketCopyReference, MarketCopyCopySubCode,
    MarketCopySubCodeReference, MarketCopyContent\]
-   To include the \'PIES Market Copy Type ID+PIES Market Copy Record
    Sequence\' values as a prefix to the PIES Market Copy object STEP
    Name
-   To handle Market Copy Sub Code with the value \'PTI\' so that if
    MarketCopySubCode=\"PTI\", then the PIES Market Copy object is
    referenced by the Part Terminology object that matches the
    MarketCopySubCodeReference. An example of the Marketing Copy object
    \'GCC3 Brand Power Window Regulator and Motor\' being referenced by
    the part terminology \'Exterior Door Handle\' is shown below.

![](../../Resources/Images/Release%20Notes/9.3MP1/5.png)

PRODOC note: RDCUST- 3844Updated Easy Setup and Qdb Importer to handle
Qualifier grouping

The QualifierGroup and GroupNumber information was introduced by
AutoCare starting with the December 2019 Qdb to provide a way to connect
similar qualifiers. Prior to this update, the Qdb data model and
importer did not support grouping of Qualifiers, thus creating the
Qualifier objects directly below the respective Qualifier Type. Now,
Easy Setup and the Qdb Importer have been updated to handle the
qualifier grouping correctly.

1.  Run step 1 of the **Automotive - AutoCare Model** Easy Setup to:

-   Create a new \'Qualifier Group Number\' object type under
    \'Qualifier Type\' object type and add it as an additional parent to
    the existing AC\_Qualifier object type.

2.  The Qdb Importer has been updated to:

-   Create the Qualifier Group Number in the Qdb classification based on
    the Qualifier Group Number table available within the AutoCare Qdb
    file.
-   Create Qualifier objects below the new Qualifier Group Number based
    on the Qdb file to match the Qualifier ID to the Qualifier Group
    Number ID
-   If the Qualifier Group Number information does not exist for a
    Qualifier, then such Qualifiers will be created directly under the
    respective Qualifier Type.

Below is a screenshot displaying the updated Qualifier classification
that includes Qualifier Group Number after importing the Qdb file.

![](../../Resources/Images/Release%20Notes/9.3MP1/13.png)

PRODOC note: RDCUST- 3849Updated Easy Setup and Brand Importer to handle
BrandOEMFlag

BrandOEMFlag information is available within the AutoCare Brand file
that carries information on an interchange. The Brand Importer has been
updated to handle the BrandOEMFlag information.

1.  Run step 1 of the **Automotive - AutoCare Model** Easy Setup to:

-   Create a new Description attribute called AC\_BrandOEMFlag and make
    it valid for Brand and Sub Brand classification objects
-   Create a new LOV called AC\_Boolean and make it referenced for
    AC\_BrandOEMFlag attribute

2.  The Brand Importer has been updated to:

-   Populate the AC\_BrandOEMFlag attribute value on the Brand and Sub
    Brand objects.

PRODOC note: RDCUST- 3963Added support to PCdb Importer to handle Coded
values for PIES attributes

Previously, step 1 of AutoCare Easy Setup created certain PIES
attributes incorrectly with Text validation. Since certain PIES
attribute data were moved to be coded values that are provided within
the PCdb file, the attributes that were getting created as Text
validation would never get updated with new coded values. Now, Easy
Setup has been updated to no longer create PIES coded value attributes
as Text validation. And PCdb importer has been updated to correctly
populate the LOVs with the coded values that are provided in the PCdb
files.

**Existing Implementations:** For environments that do not have any
attribute values in the PIES coded value attributes, do the following:

1.  Delete these existing PIES attributes

-   AC\_PIES\_ITEMItemQuantitySizeUOM
-   AC\_PIES\_ITEMQuantityPerApplicationUOM
-   AC\_PIES\_ITEMMinimumOrderQuantityUOM
-   AC\_PIES\_PACKInnerQuantityUOM
-   AC\_PIES\_PACKWeightsUOM
-   AC\_PIES\_HAZMHazMatCodeQualifier
-   AC\_PIES\_HAZMWHMISCode
-   AC\_PIES\_HAZMPackingGroupCode
-   AC\_PIES\_PACKDimensionsUOM
-   AC\_PIES\_HAZMShippingScope
-   AC\_PIES\_HAZMBulk
-   AC\_PIES\_HAZMTransportMethod
-   AC\_PIES\_ASSTResolution
-   AC\_PIES\_ASSTBackground
-   AC\_PIES\_ASSTAssetDescriptionCode
-   AC\_PIES\_KITSQuantityUOM
-   AC\_PIES\_KITSSoldSeparately
-   AC\_PIES\_KITSComponentIDQualifier

2.  Delete these existing PIES LOVs

-   AC\_PIESDimensionCodes
-   AC\_PIESShippingScope
-   AC\_PIESBulk
-   AC\_PIESTransportMethod
-   AC\_PIESResolution
-   AC\_PIESBackground
-   AC\_PIESComponentIDQualifier

3.  Rerun **step 1 of AutoCare Easy Setup** to recreate the following
    attributes and LOVs that will be linked to the
    AC\_PIESItemToKitComponentItem product reference. PCdb importer will
    populate the values for the LOVs

-   AC\_PIES\_KITSQuantityUOM (LOV: AC\_PIESQuantityUOM)
-   AC\_PIES\_KITSSoldSeparately (LOV: AC\_PIESSoldSeparately)
-   AC\_PIES\_KITSComponentIDQualifier (LOV:
    AC\_PIESComponentIDQualifier)

3.  Reimport the PCdb file to recreate the attributes from step 1 with
    the correct LOV validation

For environments that do have existing values for the coded value
attributes, export the objects with values for the coded value
attributes before doing step 1 above. Then reimport the attribute values
after step 3.

The following is the Hotfix recipe for handling the coded values for
PIES attributes

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/389/issue-389304-HOTFIX-3823.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/386/issue-386910-HOTFIX-3767.spr]{.commandfont}

PRODOC note: RDCUST- 3874Added option to include / exclude Digital
assets based on their Asset Type, Resolution, Orientation and File Type,
and to filter out the nonessential Digital asset attributes from the
PIES Export

Previously, the \'AutoCare PIES Exporter\' format was hard-coded to
include all Digital assets irrespective of their Asset Type, Resolution,
Orientation and File Type in the exported file. Also, it was hard-coded
to include all attributes related to the Digital assets in the PIES
exported file, which prevented users from selecting attributes from the
Digital assets to be included / excluded in the exported file. The PIES
Exporter has now been updated to include a new parameter called
\'Digital Assets\' to allow users to select the Digital asset types to
be included or excluded in the exported file. The \'Digital Assets\'
parameter is available within the \'Advanced\' tab of the Export
Manager.

![](../../Resources/Images/Release%20Notes/9.3MP1/16.png)

The parameter allows users to filter Digital assets based on their Asset
Type, Resolution, Orientation and File Type, and also provides an option
to filter out the Digital Asset attributes that should be excluded from
being exported. Clicking the ellipses button
(![](../../../../Resources/Images/Buttons/ellipsis.png){.img_intext})
that is available next to the parameter will display the Digital Assets
dialog (as shown below).

![](../../Resources/Images/Release%20Notes/9.3MP1/15.png)

If no asset attribute is deselected in the Include Elements section,
then the export continues to function as before and no attribute will be
excluded from export. Similarly, if no Asset Type, Resolution,
Orientation, and File Type is moved from the Included to the Excluded
column, the export continues to function as before and no Digital assets
will be excluded from export.

For example, if the user wants to specify that certain Asset Types such
as Primary Photo (P04) and User Defined (ZZ1-ZZ9) should be exported,
but exclude all other Asset Types, then the user will be able to do that
by retaining Primary Photo (P04) and User Defined (ZZ1-ZZ9) in the
Included list and moving the other Asset Types to the Excluded list.

This parameter is available in all the versions of the PIES export.

Following are the features of this parameter:

-   The new parameter allows multi attribute selection. If more than one
    attribute needs to be excluded from the export, users can deselect
    more than one attribute within the Digital Assets dialog.
-   The new parameter provides the flexibility to combine multiple
    criteria to include the required Digital Assets in the export. For
    example, criteria to include images of Primary Photo (P04) Asset
    Type, .jpg File Type and of 600 dpi resolution.

PRODOC note: RDCUST-3895Added option to filter Descriptions based on the
Description Types from the PIES Export

Previously, the \'AutoCare PIES Exporter\' format was hard-coded to
include all Descriptions that are included within the Data Container
related to the PIES Item in the PIES exported file, which prevented
users from selecting which Description Type to be included / excluded in
the exported file. The existing \'Description\' parameter within the
PIES Exporter has been updated to allow users to select the Description
Type to be excluded in the exported file. By default, all Description
Types will be included in the exported file.

This parameter is available in all the versions of the PIES export.

Following are the features of this parameter:

-   The new parameter allows multi Description Type selection. If more
    than one Description Type needs to be excluded from the export,
    users can define more than one Description Type in the parameter.
-   This new functionality also handles the values defined in the PIES
    Description Sequence Code (AC\_PIES\_Description\_SequenceCode)
    attribute that is contained within the Data Container. The exported
    Descriptions will be in the order defined within the PIES
    Description Sequence Code attribute.
-   It also handles dimension dependency for the Description
    (AC\_PIES\_Description) as well as the sequence
    (AC\_PIES\_Description\_SequenceCode) in order to have different
    values and sequencing for different receivers.

![](../../Resources/Images/Release%20Notes/9.3MP1/17.png)

PRODOC note: RDCUST-3875Added option to include / exclude PIES
Interchange items based on their Quality Grade Level / Type Code, and to
filter out certain attributes from the PIES Export

Previously, the \'AutoCare PIES Exporter\' format was hard-coded to
include all PIES Interchange items related to the PIES Item irrespective
of their Quality Grade Level / Type Code in the exported file. Also, it
was hard-coded to always include Brand Label, Interchange Note, and the
Internal Note attributes related to the PIES Interchange item in the
PIES exported file, which prevented users from selecting these
attributes from the PIES Interchange item to be included / excluded in
the exported file. The \'Interchange\' parameter of the PIES Exporter is
updated to allow users to select the Quality Grade Level / Type Code
that are to be included in the exported file. The \'Interchange\'
parameter is available within the \'Advanced\' tab of the Export
Manager.

If no Quality Grade Level / Type Code is selected, then the exported
PIES file will not include any PIES Interchange items. It is important
to always select the Quality Grade Level / Type Code after the
\'Interchange\' parameter is checked. Also, selecting the \'Brand
Label\', \'Interchange Note\', and the \'Internal Note\' parameters that
are available within the \'Advanced\' tab of the Export Manager will
include the Brand Label, Interchange Note, and the Internal Note
attribute values in the exported file.

Following are the behavior of this parameter after the update:

-   Users can filter the PIES Interchange items based on their Type Code
    only in the PIES export file version 6.5.
-   Users can filter the PIES Interchange items based on their Quality
    Grade Level only in the PIES export file versions of 6.7 and above.
-   If the \'Interchange\' parameter is selected and no Quality Grade
    Level / Type Code is selected, then no PIES Interchange items will
    be exported.

![](../../Resources/Images/Release%20Notes/9.3MP1/21.png)

PRODOC note: RDCUST- 3870New \'Condition\' parameter in Object to Object
Mapping plugin

A new field called \'Condition\' is available within the Object to
Object Mapping plugin screen that allows the user to define a business
condition, that will run before the target object is created. This is an
optional condition that will not be running on an actual node but can
access details about the node via a new javascript bind called \'Initial
Object.\' This field is created with the intention to be populated with
a business condition that determines whether a Target object will be
created or not.

![](../../Resources/Images/Release%20Notes/9.3MP1/8.png)

PRODOC note: RDCUST- 3870New JavaScript bind \'Initial Object\'

A new \'Initial Object\' bind has been added to the \'Mapping\' menu.
This bind gets access to the details (e.g. name, attributes, references,
etc.) of the Target node that is being created during the execution of
the Object to Object Mapping plugin and assigns it to a JavaScript
variable. This bind can be used within a business condition that is
defined in the Object to Object Mapping plugin screen to decide whether
a Target object will be created or not. The business condition will not
run on any object, instead, it determines if the object related to the
Target needs to be created before the actual object is created.

![](../../Resources/Images/Release%20Notes/9.3MP1/7.png)

PRODOC note: RDCUST- 3689, 3891Updated Easy Setup and VCdb Importer to
handle Equipment VCdb

Previously, the VCdb importer supported only the import of Light Duty,
Medium/Heavy Truck, Powersports, and Complete VCdb (LD, MD, HD,
PS)files, and the AutoCare data model had no support for the Equipment
VCdb file. Now, the VCdb Importer has been updated to handle the
Equipment VCdb file.

In order to use the new functionalities, the following must be done
after the patch has been applied:

1.  Run **Automotive - Import Flow Process** Easy Setup to

-   Create a new Description attribute called Import Source (ID=
    ImportFlowSource) as child of Import Flow Attribute Group

1.  Run step 1 of the **Automotive - AutoCare Model** Easy Setup to

-   Create a new LOV validated Description attribute called VCdb
    Production End (ID= AC\_VCdbProductionEnd) as child of AutoCare VCdb
    Attributes group and make it valid for Equipment classification
    object
-   Create a new LOV validated Description attribute called VCdb
    Production Start (ID= AC\_VCdbProductionStart) as child of AutoCare
    VCdb Attributes group and make it valid for Equipment classification
    object
-   Create a new LOV validated Description attribute called VCdb
    Equipment Mfr (ID= AC\_VCdbEquipmentMfr) as child of AutoCare VCdb
    Attributes group and make it valid for Equipment Base classification
    object
-   Create the AC\_EquipmentModel object type under AC\_VehicleType
-   Create the AC\_BaseEquipment object type under AC\_EquipmentModel
-   Create the AC\_Equipment object type under AC\_BaseEquipment
-   Create a new Classification Reference Type called
    AC\_EquipmentToEngineConfig that is valid from AC\_Equipment object
    type to AC\_EngineConfig target object type

3.  Run step 2 of the **Automotive - AutoCare Model** Easy Setup to make
    the Import Source attribute valid for VCdb classification object
    types.
4.  Run step 3 of the **Automotive - AutoCare Model** Easy Setup to add
    Equipment Base object type to the Assembly aspect in the Application
    Model component so that Application Manager can find applications
    that are linked to Equipment Base objects.

After importing the Equipment VCdb file, the Equipment classification
hierarchy will be created based on Vehicle Type Group \> Vehicle Type \>
Equipment Model \> Equipment Base \> Equipment. For example:

![](../../Resources/Images/Release%20Notes/9.3MP1/22.png)

Also, the VCdb importer is updated so that the delta calculation is
looking at the correct VCdb file to compare to. This ensures that the
new, changed and deleted objects are tracked on the subsequent imports.

If users want to track new / change / delete flags for Vehicle /
Equipment objects, the VCdb importer Delta calculation method parameter
must be set to **\'file\'**.

PRODOC note: RDCUST- 3928Added support to handle Equipment related
application records for ACES Importer and ACES Exporter

Previously the ACES Importer and ACES Exporter did not handle the
Equipment related application records. When such files were imported,
the ACES Importer just created the PIES Item and ignored the Equipment
related elements thereby not creating the related application records.
Now, the ACES Importer has been updated to handle Equipment related
application records.

1.  The ACES Importer has been updated to create an application record
    and link it to the Equipment Base object if the uploaded ACES file
    contains an EquipmentBase ID or the Mfr, EquipmentModel, and
    VehicleType IDs.
2.  The ACES Exporter has been updated to include an application record
    that is linked to an Equipment Base object in the system. Further
    updates are made that if the user selects the \'Export in Make/Year
    format\' parameter (this parameter is available with this release as
    explained below) then the exporter will include the information
    about Manufacturer, Equipment Model and Vehicle Type in the exported
    file.

The handling of the Equipment by the ACES importer / exporter is
available starting with ACES 4.0 version.

PRODOC note: RDCUST- 3897New ACES Exporter parameter allows exporting
ACES file by Make / Model / Year

A new optional parameter (**Export in Make/Year format**) added to the
ACES Exporter that allows the ability to export ACES applications in
Make / Model / Year range format if the application is linked to a
BaseVehicle, or Mfr, EquipmentModel, and VehicleType if the application
is linked to an EquipmentBase.

![](../../Resources/Images/Release%20Notes/9.3MP1/12.png)

If the parameter is unchecked, the exported file will include the
individual application record with the linked Base Vehicle ID
information (as shown in the image on the left below). If the parameter
is selected, the exported file will compress the applications into Year
range, Make, and Model in the exported file (as shown in the image on
the right below).

![](../../Resources/Images/Release%20Notes/9.3MP1/11.png)

For more information, see the **AutoCare ACES Application Exporter**
topic in the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

**Hotfix recipe compatible with STEP baseline 9.2 MP3 + Automotive 9.2
MP2:** [to:hotfix/384/issue-384310-HOTFIX-3725.spr]{.commandfont}

**Hotfix recipe compatible with STEP baseline 9.3 + Automotive 9.3:**
[to:hotfix/384/issue-384310-HOTFIX-3725.spr]{.commandfont}

PRODOC note: RDCUST- 3889New \'Object Type Filter\' parameter in the
Application Editor Screen Properties

A new parameter called **Object Type Filter** has been added to the
Application Editor Screen Properties that allows users to restrict the
Application Editor results by an object type. Previously, when a part /
assembly is selected, all application records listed below the part /
assembly were displayed irrespective of their object types. Now, the
Object Type Filter parameter allows users to add object types so that
only the application records belonging to the listed object type will be
displayed in the Application Editor screen. If left blank, then
application records belonging to all object types will be displayed.

![](../../Resources/Images/Release%20Notes/9.3MP1/14.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST-3830Corrected the Application Part Type component in
the Application Manager to retain the state of the screen when a
hyperlink is clicked and the user returns to the Application Manager
screen through the back navigation button of the browser

The Application Part Type component configured in the Application
Manager screen displays the Part Type information in the form of
hyperlinks. Clicking on the hyperlink would leave the Application
Manager screen and navigate into another defined screen. Previously,
when the user navigates to another screen by clicking on the hyperlink
and then returns to the screen by clicking on the Back navigation button
of the browser, the Application Manager screen was not holding the exact
previous state of the search cards in the screen. Now, the Application
Part Type component configured in the Application Manager screen is
updated to remember the state of the search cards so that the user can
navigate back to the Application Manager from other screens with the
previous state of the search cards retained.

PRODOC note: RDCUST-3955Improved Step Path Editor window and Validation
Path Editor window appearance and ease-of-use

For better user experience, the aesthetics of the Step Path Editor
window that is available within the \'Object to Object Mapping\' plugin
and Target Hierarchy Editor parameter, and Validation Path Editor window
that is available within the \'Application Mapping\' plugin has been
improved.

The improvements include:

-   Margins have been added to the dialog
-   Line wrapping has been added for the Step Path and Keyword fields
-   The Search field now has a clearer icon

PRODOC note: RDCUST-3735Updated the results table of Faceted Search
dialog in Application Editor to adapt with the dialog size

In the Application Editor screen, the results table of Faceted Search
dialog has been updated to adapt to the dialog size if the data to be
displayed is smaller than the dialog size.

PRODOC note: Cardone-205Fixed issue with selecting multiple applications
to run a bulk update on in the Application Editor Screen

Previously, selecting multiple applications to run a bulk update on
would kick off an empty background process that did not perform any
action, therefore, the applications were not updated. The Application
Editor Screen has been updated to support bulk operations when all
applications are selected.

**Hotfix recipe compatible with STEP baseline 9.2 MP3 + Automotive 9.2
MP2:** [to:hotfix/387/issue-387054-HOTFIX-3776.spr]{.commandfont}

PRODOC note: RDCUST-3957Fixed an error when using In-Memory within the
Application Manager Screen

Previously, certain suggestions using the Options Group Search Box in
combination with other search boxes on an environment that has In-Memory
enabled could cause an out-of-memory error. This issue has been fixed so
that the Application Manager performance improvement is disabled on an
environment that is running with In-Memory so that the error will no
longer occur.

**Hotfix recipe compatible with STEP baseline 9.3 + Automotive 9.3:**
[to:hotfix/386/issue-386955-HOTFIX-3771.spr]{.commandfont}

PRODOC note: RDCUST-3776Corrected error when using \'Select all\' button
available within the toolbar of the Part Application Editor component

Previously, when a suggested application is added to the Part
Application Editor component and then deleted, the \'Select all\' button
was not displayed in the toolbar of the Part Application Editor
component. Now, the \'Select all\' button is corrected in the Part
Application Editor component so that users are able to view the \'Select
all\' button when the suggested application is added and then deleted.
For more information on the Application suggestion solution, see the
**Application Suggestion Solution** section of the **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST-3743Improved accuracy when searching for relevant
targets (assembly / vehicle or part) in Faceted Search dialog

Target (assembly / vehicle or part) search accuracy has been improved by
taking both the Condition and Part Type values into consideration.
Previously, when searching for relevant targets (assembly / vehicle or
part) in Faceted Search dialog, conditions for specific part types were
not considered, resulting in the display of invalid targets (assembly /
vehicle or part). For example, when searching for a 2013 Audi A3 vehicle
for a selected spark plug, the results table would list both Gas and
Diesel engines, even though Diesel engines do not use spark plugs, and
are invalid in the search results. Now, we have improved the targets
search by introducing an existing Business Condition plugin (\'Check
path for missing application\') in the Faceted Search dialog where a
validation path can be configured so that the invalid targets for a
specific part type are filtered away, and only valid values are
returned.

 

PRODOC note: RDCUST-3776Corrected the Subcomponent parameter available
within the Application Set Assembly table header component to only allow
the defined Assembly for selection in the typeahead field

When there are multiple Assemblies available in the system, the
Subcomponent parameter of the Application Set Assembly table header
component provides an option to restrict the unwanted Assemblies being
displayed in the typeahead field, and allows only the Assembly of the
required object type to be displayed in the typeahead field of the
Application Set Assembly table header cell. Previously, the Subcomponent
parameter exhibited some error that failed to restrict the unwanted
Assembly being displayed. Now, the Subcomponent parameter is updated so
that it allows users to configure the parent object type of the required
Assemblies thereby filtering out the unwanted Assemblies.

![](../../Resources/Images/Release%20Notes/9.3MP1/9.png)

Also, the parameter is updated to display an error message when the
parent object type id typed in the Subcomponent parameter does not
include the children Assembly object types as defined in the automotive
component model. The error message will be displayed as shown below:

Also, whenever the object type ID typed in the Subcomponent parameter
does not include the Assembly object types as its children, then there
is an error message displayed as shown below. The Assembly object types
are determined in the Automotive component model.

![](../../Resources/Images/Release%20Notes/9.3MP1/10.png)

PRODOC note: RDCUST-3956Updated the messages that are displayed when
users click the Information icon
(![](../../Resources/Images/AppMgr/ResultsTable/2.png)) that is
available within the Approval Status table cell

The description texts that displayed when users click the Information
icon (![](../../Resources/Images/AppMgr/ResultsTable/2.png)) of the
Application Approval Status table cell that is available within the
Application Manager and Application Editor screens have been updated in
Web UI so that the new texts that are displayed are more detailed and
user-friendly to explain why the application can\'t be approved.

PRODOC note: RDCUST-3956Corrected the
[Step]{style="text-transform: uppercase;"} Path Editor window to be able
to select the reference\[type:\'\[id\]\'\] element after selecting the
referencedBy\[type:\'\[id\]\'\] element

Previously, when working in the
[Step]{style="text-transform: uppercase;"} Path Editor window for the
Mapping Validation Path functionality in \'Application Mapping\' and
\'Object to Object Mapping\' plugins, the user was not able to select
the **reference\[type:\'\[id\]\'\]** element after selecting the
**referencedBy\[type:\'\[id\]\'\]** element. Now, the
[Step]{style="text-transform: uppercase;"} Path Editor window has been
corrected so that it is always possible to select the
**reference\[type:\'\[id\]\'\]** element after selecting the
**referencedBy\[type:\'\[id\]\'\]** element. For the \'Application
Mapping\' plugin, the element can be selected as part of the Source
Validation Path Editor and Target Validation Path Editor. For the
\'Object to Object Mapping\' plugin the element can be selected as part
of the STEP Path Editor. For more information, see the **Mapping
Validation Path Functionality** topic of **Automotive Reference Guide**[
here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST- 3910Updated the description texts for some
parameters that are available within the Faceted Search Node Picker
Dialog Properties

The description texts for some parameters that are available within the
Faceted Search Node Picker Dialog Properties have been updated in the
Web UI to avoid confusion for users. The changes are as follows:

  Parameter Name        Existing Description                                                                                                                                                                                                              New Description
  --------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Find attributes       List of node attributes to search for                                                                                                                                                                                             The list of node attributes used to search for in the free text search field.
  Root Nodes            Root nodes to search below                                                                                                                                                                                                        Add root nodes to restrict where to search below.
  Search Fields         Allows one to four search fields to be added to the Search Panel. Only one search box is required, and each search field type can be added only once. The order listed determines the order of display within the search panel.   Allows Attribute, Hierarchy, and/or Name Search Fields to be added to the search panel. Hierarchy Search Field and Name Search Field can be added only once. Attribute Search Field can be added multiple times. The order listed determines the order of display within the search panel.
  Search Placeholders   Set to provide a custom title for the search field placeholder                                                                                                                                                                    The text that is displayed in the free text search field. The default text is Search for names, ids and attributes.
  Title                 Set to provide a custom title for the dialog                                                                                                                                                                                      The text that is displayed as the Title in the Faceted Search dialog. The default text is 'Select node(s)'.

![](../../Resources/Images/Release%20Notes/9.3MP1/2.png)

PRODOC note: RDCUST- 3939Corrected a behavior in the Application Manager
Screen to display the correct number of missing application records with
a single click on the Search button.

Previously, a search for the missing application records by entering
multiple values in any search card, and then, clicking the Search button
was not displaying the correct results. Instead, it required multiple
clicks on the Search button for the same search criteria was displaying
the correct number of application records in the results table. Now, the
Application Manager Screen has been corrected to display the correct
number of missing application records with a single click on the Search
button.

PRODOC note: CARDON- 195Fixed NPE generated in the Application Manager
Screen related to the generation of report

Previously, when the Application Manager Screen was configured as a sub
screen tab page, a null pointer error would be generated if you
attempted to generate a report by clicking the **Report** button. This
has been corrected so that a valid report is generated.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/388/issue-388475-HOTFIX-3802.spr]{.commandfont}

PRODOC note: NGK-734Fixed NPE generated in the Onboarding Mappings
Details screen related to the Target Hierarchy parameter

One of the previous version updates caused a null pointer error to be
generated if the user attempted to select a Mapper Configuration setup
entity in the Web UI. This has been corrected so an exception error is
no longer thrown when users select a Mapper Configuration setup entity.

PRODOC note: NGK-576Updated Application Manager to allow change of Part
or Vehicle for an existing application

The \'Application Set Part\' and \'Application Set Assembly\' table
header components that are configured in the Application Manager result
table displays the Part and Vehicle that are linked to the application
respectively. Previously, an error was thrown if a user tried to change
the Part or Vehicle that was linked to the existing applications in the
Application Manager results table. Now, the \'Application Set Part\' and
\'Application Set Assembly\' table header components have been updated
to allow making changes to the Part / Vehicle linked to an existing
application.

PRODOC note: RDCUST-3961Corrected an issue in Application Manager where
missing applications were not found correctly

Previously, missing applications were not found correctly in the
Application Manager when any attribute condition had been set. This bug
has been resolved and missing applications are now found and displayed
correctly in the Application Manager even when an attribute condition is
set on an application.PRODOC note: BOND NGK-577

**Hotfix recipe compatible with STEP 9.3 + Automotive 9.3:**
[to:hotfix/387/issue-387629-HOTFIX-3785.spr]{.commandfont}

PRODOC note: RDCUST-3108Corrected the Application Manager to completely
refresh the search result for every click on the Search button

Corrected the Application Manager to execute every action on the latest
search result when the user performs any action on the search results.
Previously, when the user performed a second search with different
search criteria, though the Results Table refreshed and displayed the
latest search results, any bulk actions (delete / bulk update / create
collection etc.) on the search results were not executing on the latest
search results. instead, the previous state memory was retained, and the
action was executed on the previous search results. Now, this issue is
corrected so that the Application Manager executes on the latest
selected result list when the user performs any action on the search
results.

PRODOC note: RDCUST-2913Corrected \'Value editor\' window of the \'ACES
Application Qualifiers\' table header component to display Qualifier
root Nodes in alphabetical order

The \'ACES Application Qualifiers\' table header component is allowed to
be configured within the Application Manager and Application Editor
screen, and when the user clicks on a cell, the \'Value editor\' dialog
displays information for the existing Qualifiers along with the \'Add
Qualifier\' link. When the user clicks on the \'Add Qualifier\' link,
the \'Select qualifier\' dialog with a list of available Qualifiers and
Qualifier Types is displayed. Previously, these Qualifiers were not
listed in alphabetical order. Now, the \'Select qualifier\' dialog has
been corrected to display the available Qualifiers in alphabetical
order.

PRODOC note: NGK-570Fixed Application Manager to filter out invalid
application records while searching

Previously, the presence of bad data in the system was causing the
Application Manager to display invalid application records in the result
list. Now, the Application Manager is corrected to filter out invalid
application records while searching.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/382/issue-382862-HOTFIX-3694.spr]{.commandfont}

**Hotfix recipe compatible with STEP baseline 9.3 + Automotive 9.3:**
[to:hotfix/386/issue-386023-HOTFIX-3753.spr]{.commandfont}

**Hotfix recipe compatible with STEP baseline 9.3 + Automotive 9.3:**
[to:hotfix/388/issue-388618-HOTFIX-3808.spr]{.commandfont}

PRODOC note: RDCUST-3960Corrected an issue with the Application Mapping
plugin

Previously, within the Reference type for Vehicle relation parameter
that is available within the Mappings tab of the Application Mapping
plugin, users were not able to select the correct vehicle reference type
that should match the target vehicle object. This issue is now resolved,
and users are able to configure the right vehicle reference type.

**Hotfix recipe compatible with STEP 9.3 + Automotive 9.3:**
[to:hotfix/387/issue-387557-HOTFIX-3781.spr]{.commandfont}

PRODOC note: RDCUST- 3775Updated the Part Application Editor component
to display warnings when the user deletes an application record

\'Part Application Editor\' component display existing application
records and their attribute values when a part number is selected within
the Tree navigator. Previously, when users tried to delete an existing
application record displayed within this component, the application
record was removed without displaying a warning dialog. Now, to avoid
the accidental deletions of the application records, the \'Part
Application Editor\' component is updated to display a warning dialog
that requests users to confirm the deletion when the user clicks the
\'Delete\' button.

PRODOC note: GPC-480Updated the Object to Object Mapping plugin to
retrieve data from unique key attributes

Previously, the Object to Object Mapping plugin had no support for
retrieving data from the unique key attributes. Now, this issue is
resolved so that the Object to Object Mapping plugin will be able to
match on objects on unique keys.

PRODOC note: GPC-481Updated Logger bind to allow writing logs on the
Feedback message

Business rules use the Logger bind to write to the main STEP log file on
the application server (step.\*.log) when the business action runs.
Previously, when the business action configured in the Business Action
Mapping plugin was executed, the execution report was by default written
in the STEP log file and had no chance to be written in the Mapper log /
Feedback message. Now, this has been corrected so that when the business
action that is configured in the Business Action Mapping plugin calls
for a Logger bind, then the execution report is written in the Mapper
Log / Feedback message. For example, if executing the Business Action
Mapping plugin via a business action in the importer, the logs will be
written in the Import BGP report. If the Business Action Mapping plugin
is executed via the Mapper Action button in the Web UI, the log will be
written in the information message that is displayed on the screen.

### AutoCare

PRODOC note: RDCUST- 3689Updated the PIES Exporter to extract brand
value from \'Brand AAIA ID\' attribute

The selection of \'Include BrandAAIAID in Part\' that is available
within the Advanced tab of the ACES Export Manager will insert the Brand
AAIAID value within the \<Part\> tag of the exported file. Previously,
this value was retrieved from the ID value of the PIES Item. Now, the
PIES Exporter is updated so that the Brand AAIAID value will be
retrieved from the \'Brand AAIA ID\' attribute ( ID =
AC\_PIES\_ITEMBrandAAIAID) and not from the ID of the PIES Item. For
more information, see **AutoCare ACES Application Exporter** topic[
here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: GPC- 565Added missing EXPI codes

Previously, the PIES importer was generating \'AC\_PIES\_EXPInull\'
attribute IDs in the Conversion state for certain PIES EXPI attributes.
That was caused by newer EXPI codes that were introduced and were not
accounted for in the Automotive code. PIES importer has been updated to
include all 55 EXPI codes and the EXPI codes will correctly get
populated when the PIES Item is created through PIES importer.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/386/issue-386284-HOTFIX-3757.spr]{.commandfont}

PRODOC note: RDCUST- 3971Updated ID pattern of PIES Market Copy object
to optionally include MarketCopySubCode and MarketCopySubCodeReference

Changed the way the PIES Importer handled the ID pattern of the PIES
Market Copy objects so that it would optionally include the
MarketCopySubCode and MarketCopySubCodeReference information in the ID.
Previously, the PIES Importer was creating IDs with the pattern
AC\_PIESMKTC\_+ hash(MarketCopyCode + MarketCopyType +
MarketCopyReference + MarketCopySubCode + MarketCopySubCodeReference +
MarketCopyContent). As some manufacturers create Market Copy directly in
the system (not through PIES importer), they require an ID format that
they can generate on their own which would match what the PIES importer
would create. Now, the PIES Importer has been updated to no longer use a
hash value in the Market Copy ID.

Since MarketCopySubCode and MarketCopySubCodeReference fields are
optional, if those fields do not exist, then the new ID will be in the
format
AC\_MKTC\_MarketCopyCode\_MarketCopyReference\_MarketCopyType\_RecordSequence.

And if the values for the MarketCopySubCode and
MarketCopySubCodeReference exists, then the new ID will be in the format
AC\_MKTC\_MarketCopyCode\_MarketCopyReference\_MarketCopySubCode\_MarketCopySubCodeReference\_MarketCopyType\_RecordSequence.

If a Market Copy object is first created in the system without the
MarketCopySubCode and SubCodeReference, and then later on the
MarketCopySubCode and SubCodeReference is added on the same object over
subsequent import, then that object will be considered as a new object
because the object ID will differ. If an existing Market Copy object
exists in the system and the Market Copy content is changed, then the
system will rewrite to the existing object because the MarketCopy Code,
Reference, SubCode, SubCodeReference, MarketCopyType, and Record
Sequence will be the same.

PRODOC note: RDCUST-3979Corrected the way the Easy Setup action handles
the existing AutoCare attributes in the system

Step 1 of the AutoCare Easy Setup creates all of the attributes below
the AutoCare Attributes group (ID = AC\_TopLevelAttrGroup). After the
attributes are created by Easy Setup, a user can manually change the
validation and/or Maximum Length of the attributes. Previously, when the
AutoCare Easy Setup was run again, it would revert the changes that were
manually updated. Now, Easy Setup has been updated to no longer
overwrite the updates done by the user.

PRODOC note: RDCUST - 3893Updated PIES Importer to set the delete flag

Previously, the change flag functionality was not handled by PIES
Importer and the importer had no support for the PIES Maintenance Type
codes Add (A), Change (C), and Delete (D). Now, the PIES Importer is
updated so that the PIES Item, PIES Package, and PIES HazMat objects
will get marked for deletion. Also, the PIES Importer is updated to
handle PIES Maintenance Type codes Add (A), Change (C), and Delete (D)
during the import.

For more information on the change flag functionality, see **Update
Delete Status Attribute and Delta Calculation Method in Import
Workflows** topic[ here]{.mcFormatColor style="color: Blue;"}.

If users want to track new / change / delete flags for PIES objects as
well as use replacement rules to update PIES attribute values and data
container values, the PIES importer Delta calculation method parameter
must be set to **\'context\'**. If users want to track only the new or
changed objects but ignore deleted items, and also use replacement
rules, the PIES importer Delta calculation method parameter must be set
to **\'file\'**.

Existing implementations must run **step 1 of the Automotive - AutoCare
Model Easy Setup** to create the Replacement Context attribute \'ID =
AC\_PIESReplacementContext\' under the Metadata attribute group.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/389/issue-389047-HOTFIX-3820.spr]{.commandfont}

PRODOC note: RDCUST- 3853Updated PIES Importer to handle ™, Ł, Ǆ, ©, and
® special characters

Previously, PIES Importer did not handle some special characters like ™,
Ł, Ǆ, ©, and ®, and that caused validation to fail indicating that there
was invalid byte 1 of 1-byte UTF-8 sequence. PIES Importer has been
updated to validate these special characters and not to display any
validation errors.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/387/issue-387670-HOTFIX-3787.spr]{.commandfont}

PRODOC note: RDCUST-3855Corrected an error in the VCdb importer

Make.txt is a file available within the AutoCare VCdb zip file that
contains Make information for a vehicle. Previously, the VCdb Importer
was wrongly trying to write the values from the Make file to the VCdb
Vehicle Type Multi Value attribute (ID = AC\_VCdbVehicleTypeMultiValue
which are Vehicle Type Groups) that resulted in the following type of
error:

\'*Error in this import 02\_Make.xml setting completed with errors -
Error: The value for attribute \'AC\_VCdbVehicleTypeMultiValue\' on
classification \'AC\_VehicleType\_0\' isn\'t valid*\'

Now, the VCdb importer is corrected to not set any values from Make file
for VCdb Vehicle Type Multi Value attribute (ID =
AC\_VCdbVehicleTypeMultiValue).

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/387/issue-387809-HOTFIX-3790.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/388/issue-388707-HOTFIX-3812.spr]{.commandfont}

PRODOC note: RDCUST- 3981Fixed NullPointerException error generated in
the Application Manager related to search with Make/Model and Year
combination

Previously, there was a problem while searching with Make / Model and
Year combination. The search failed with the following error:

*\"Fatal: Unexpected error. Please contact your system administrator.
Internal Server Error\"*

This has been corrected so that an exception error is no longer thrown
when searching

PRODOC note: RDCUST.- 3913Updated PIES Importer to handle PIES EXPI
Codes and PAdb attribute values matching on the LOV Value ID

Certain PIES EXPI and PAdb attributes uses LOV validation, and the LOVs
uses IDs. Previously, when the LOV Value ID was provided in the PIES
import file, the PIES importer was not recognizing the Value ID and
displayed an error indicating that there is a disallowed value with an
\'IllegalLOVValue\' warning. The PIES importer was only recognizing the
Values instead of the Value ID. Now, the PIES Importer has been updated
to also handle the LOV Value ID.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2 and
STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/384/issue-384289-HOTFIX-3724.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.3 + Automotive
9.3:**[to:hotfix/390/issue-390513-HOTFIX-3853.spr]{.commandfont}

PRODOC note: RDCUST-3871Updated ACES import execution report to include
more details when handling application records with invalid vehicle
configurations

The \'Validate Application on import\' business condition that is used
in the Import state of the ACES Import workflow contains a **Check
configuration validity** parameter. When this parameter is selected, the
ACES importer will validate vehicle conditions (such as SubModel or
DriveType) against the vehicle configurations from the VCdb. Any errors
that are encountered are written to the Execution Report in the Import
state Background Process, and the application does not get created in
STEP. Previously, the rejected application record was written with a
generic message that didn\'t include the information for which vehicle
configuration is invalid. For example:

*Error: An application (id=1) for part: 122.48010 had conditions not
matching vehicle*

Now, the error message has been updated to include the information for
the vehicle configuration that had failed. For example:

*!53 Error in this import 02\_Applications.xml setting completed with
errors - Error: An application (id=1) for part: \'222.48010\' had
conditions not matching vehicle. \'2007 Chevrolet HHR\' does not exist
with: \'Sub Model = \'\#PinkBeetle\'\'*

*54 \[com/stibo/importservices/importmessages\|1: The product with ID
\'AC\_ACESApp\_594136376bf06cca17eacd9919ca8\' was skipped \]*

PRODOC note: RDCUST-3981Corrected a Validation error that was exhibited
when the user exported PIES Item with the Kits component

The Kits segment in the exported PIES file contains the information from
the PIES Description attribute and is populated within the
\<DesciptionCode\> tags. Previously, when the Description parameter that
is available within the Advanced tab of the Export Manager was
unchecked, the information in the PIES Description attribute was not
parsed, and the system was throwing a validation error during export.
Now, this issue is resolved so that the system will export the PIES Item
with the Kits component even if the Description parameter is unchecked.

PRODOC note: RDCUST-3935Corrected an issue with ACES importer creating
duplicate application records because of the AssetName is used in the
application ID hash value

Previously, ACES importer created application object IDs by using the
AssetName in the hash value to determine uniqueness. This caused
duplicate application records to be created when the ACES file contains
the same application with references to multiple AssetNames was imported
into the system. Now, a new sharedconfig property called
**Automotive.Aces.UseAssetNameInUniqueness=true/false** has been
introduced so that:

-   Setting the property to
    Automotive.Aces.UseAssetNameInUniqueness=false will not use the
    AssetName in the application ID
-   Setting the property to
    Automotive.Aces.UseAssetNameInUniqueness=true will use the AssetName
    in the application ID

PRODOC note: RDCUST-3936Updated ACES Importer to not create application
records if AssetName is missing from DigitalAsset segment of the
importing ACES file

Previously, if an ACES file contains application records with
\<AssetName\> but did not have a \<DigitalAsset\> segment, the ACES
importer would complete the import and create the applications, but no
assets were created and there were no references to the assets from the
application because the \<DigitalAsset\> segment was missing. Also,
there was no indication of what AssetName is associated with the
application because the AssetName is stored in the Asset ID attribute
(ID = AC\_PIES\_ASSTAssetID) that is stored on the asset object. Now,
the ACES importer conversion state has been updated so that if an
application contains an \<AssetName\> element, and the \<DigitalAsset\>
segment is missing completely, or if the \<DigitalAsset\> segment does
exist but the \<AssetName\> does not exist in the
\<DigitalFileInformation\> element, then such application will be
skipped and not get created on import. Also, the errors will be written
to the log indicating why the applications were skipped.

PRODOC note: RDCUST-3937Updated AutoCare Easy Setup and ACES Importer /
Exporter to handle more asset types

Previously, the AutoCare data model was supporting only the following
four types of ACES assets for applications:

-   Installation Instructions (INS)
-   Owner's Manual (OWN)
-   Photo - out of package (P01)
-   Photo - Primary (P04)

In order to handle many other ACES asset types, AutoCare Easy Setup has
been updated to create a new object type ACES Asset (General) with
ID=AC\_ACESAsset, a new asset reference type ACES To Asset with
ID=AC\_ACESToAsset. Also, the existing attribute with
ID=AC\_PIES\_ASSTAssetType has been made valid to the newly created
reference type ID=AC\_ACESToAsset.

Also, the existing attributes like AC\_PIES\_ASSTAssetDescriptionCode,
AC\_PIES\_ASSTAssetDimensionsUOM, AC\_PIES\_ASSTAssetHeight,
AC\_PIES\_ASSTAssetID, AC\_PIES\_ASSTAssetWidth,
AC\_PIES\_ASSTBackground, AC\_PIES\_ASSTColorMode,
AC\_PIES\_ASSTCountryCode, AC\_PIES\_ASSTEffectiveDate,
AC\_PIES\_ASSTExpirationDate, AC\_PIES\_ASSTFileDateModified,
AC\_PIES\_ASSTFilePath, AC\_PIES\_ASSTFileSize, AC\_PIES\_ASSTFileType,
AC\_PIES\_ASSTLanguageCode, AC\_PIES\_ASSTOrientationView,
AC\_PIES\_ASSTRepresentation, AC\_PIES\_ASSTResolution, and
AC\_PIES\_ASSTURI has been made valid for the newly created object type
AC\_ACESAsset.

This update can be applied by running Easy Setup via **Automotive -
AutoCare Model** \> 1. Configure AutoCare Data Model.

In addition, the ACES Importer has been updated to create all other
assets (aside from INS, OWN, P01, or P04) as object type \'ACES Asset
(General)\' and using the AC\_ACESToAsset reference to link the ACES
Item to the ACES Asset (General) object. And the AC\_PIES\_ASSTAssetType
attribute that is valid on the reference is populated with the value
from the AssetType tag in the input file.

ACES Exporter has been updated to include all asset data in the exported
file.

PRODOC note: RDCUST-3933Updated AutoCare Easy Setup, ACES Importer, and
ACES Exporter to handle some additional asset data

Previously, support for certain ACES Digital Asset elements were missing
in STEP and asset data could not be stored for those missing elements.
Easy setup for AutoCare has been updated to make the FileType, FileSize,
ColorMode, AssetDimensions UOM, AssetHeight, and AssetWidth attributes
valid for AC\_ACESInstallationInstruction, AC\_ACESOwnersManual,
AC\_ACESPrimaryProductImage, AC\_ACESProductImage, and AC\_ACESAsset
object types.

This update can be applied by running **Automotive - AutoCare Model** \>
1. Configure AutoCare Data Model Easy Setup.

In addition, the ACES Importer has been updated to write the asset data
to the attributes mentioned above, and the ACES Exporter has been
updated to include the asset data in the exported file.

PRODOC note: RDCUST-3980Updated the way the Product Attributes / Part
Terminology Attributes parameter handled an error message

Updated the Product Attributes / Part Terminology Attributes parameter
in the PIES Export Manager to instantly notify the user to select an
attribute group if the user selects the Product Attributes parameter and
unchecks the \'Part Terminology Attributes\' checkbox. Previously, this
error dialog was not instantaneously displayed and displayed only when
the user clicked on the Back or Next button after selecting the Product
Attributes parameter and deselecting the \'Part Terminology Attributes\'
checkbox. Now, this issue has been updated so that the error message
\'No attributes selected for export\' is displayed, forcing the user to
select an attribute group or uncheck the Product Attributes parameter
checkbox.

PRODOC note: RDCUST-3826Updated ACES Exporter to include the
\<DigitalAsset\> segment in the exported ACES 4.0 file

Previously, the \<DigitalAsset\> segment missing from the exported ACES
4.0 file. Now, the ACES Exporter is updated to include the
\<DigitalAsset\> segment.

PRODOC note: RDCUST-3883Corrected the Application Manager Report button

Previously, in the Web UI Application Manager screen, when users
generated the coverage report by clicking the \'Report\' button for
search cards with an empty \'Make/Model\' card and set \'Part Type\'
card, the system was generating an empty coverage report. The report was
not generating any content in the delivered Excel file unless a
Make/Model was specified. Now, the Application Manager Report button has
been fixed to generate the correct coverage report.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/383/issue-383928-HOTFIX-3715.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.3 + Automotive 9.3:**
[to:hotfix/386/issue-386556-HOTFIX-3764.spr]{.commandfont}

PRODOC note: ACM-3287Updated PIES Importer to correctly handle \'MTP\'
and \'TLE\' Description Types

Previously, importing the PIES Description Type of \'MTP\' and \'TLE\'
populated the descriptions but failed to write Description Type
information within the PIES Desc Type attribute. This issue has been
corrected so that the \'MTP\' and \'TLE\' Description Type information
are populated within the PIES Desc Type attribute.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/391/issue-391853-HOTFIX-3869.spr]{.commandfont}

PRODOC note:Previously, when the descriptions of \'MTP\' and \'TLE\'
Desc Type was imported in the system, the data container was not
populating the Desc Type values within the PIES Desc Type attribute.
Only the PIES Description attribute was populated but the Desc Type
information was not written on the PIES Desc Type attribute.

PRODOC note: ACM-3287Updated PIES Importer to correctly handle certain
Price Types

Previously, importing prices with the following Price Types populated
the pricing information correctly but failed to write the Price Type
information within the AC\_PIES\_PRCE\_PriceType attribute.

-   CC1
-   CR5
-   CR6
-   CR7
-   CR8
-   CR9
-   CWD
-   PP1
-   PP2
-   PP3
-   PP4
-   PP5
-   PP6
-   PP7
-   PP8
-   QPB
-   WDP
-   WVP

This issue has been corrected so that the Price Types mentioned above
are populated within the AC\_PIES\_PRCE\_PriceType attribute after the
PIES file import.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/391/issue-391853-HOTFIX-3869.spr]{.commandfont}

Please note that the Price Types with four characters in the ID
(CR10-CR15, ZZ10-ZZ15) will generate errors during the Validation state
of the import process and the prices with those Price Types will not get
imported. Auto Care\'s XSD has a restriction on the length of 3
characters for PriceType:

``` {.Code3}
<xs:simpleType name="PriceType">
        <xs:annotation>
            <xs:documentation>
                Ref# D35
            </xs:documentation>
        </xs:annotation>
        <xs:restriction base="xs:string">
            <xs:length value="3"/>
        </xs:restriction>
    </xs:simpleType>
```

And those Price Types will fail validation with the following error if
they are included within the PIES import file:

Value \'CR10\' with length = \'4\' is not facet-valid with respect to
length \'3\' for type \'PriceType\'.

This cannot be resolved until Auto Care updates the XSD to allow length
= 4.

PRODOC note: ACM-3283Added Replacement Rules for PIES Importer to
replace PIES attribute values, PIES Description, and PIES price data
containers when the value is changed in the import file

Previously, the PIES importer did not handle overwriting existing PIES
attribute values, PIES Description data container, or price data
containers that had changed, but instead created new descriptions and /
or prices. Now, PIES importer has been updated to include replacement
rules that check the previously imported file to compare to the current
file being imported. If the current import file has a change to an
existing PIES attribute value, description, or price data container, the
existing data container will get overwritten instead of having a new
data container created.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/390/issue-390916-HOTFIX-3861.spr]{.commandfont}

PRODOC note: ACM-3283Corrected the way the PIES Importer handles
identical Pricing that has same Price Sheet Number

Previously, importing PIES files through the PIES Importer was creating
only one data container if there were multiple prices with the same
Price Sheet Number but different Price Types were encountered. Now, this
has been corrected so that the presence of duplicate Price Sheet Numbers
with different Price Types will create separate data containers for each
Price Type.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/387/issue-387580-HOTFIX-3783.spr]{.commandfont}

PRODOC note: RDCUST-4013Updated PIES Importer to create Marketing Copy
objects with shorter IDs

Previously, for some of the Marketing Copy object IDs, certain
combinations were causing the ID to exceed the maximum length of 40.
Now, the PIES importer has been updated to remove \'PIES\' from the ID
format and also to remove additional letters in SubCodeRef to be like
below:

-   PIES Market Copy Code = AC\_**PIES**MKTCCode\* to be AC\_MKTCCode\*
-   PIES Market Copy Reference = AC\_**PIES**MKTCReference\_\* to be
    AC\_MKTCReference\_\*
-   PIES Market Copy Sub Code = AC\_**PIES**MKTCSubCode\_\* to be
    AC\_MKTCSubCode\_\*
-   PIES Market Copy Sub Code Reference = AC\_**PIES**MKTCSubCodeRef\_\*
    to be AC\_MKTCSCRef\_\*

### TecDoc

PRODOC note: RDCUST-3887Added Replacement Rules for TecDoc Supplier Data
Importer Conversion to remove existing attribute values when the value
no longer exists in the import file

Previously, the TecDoc Supplier Data importer did not handle existing
STEP attribute values that have been deleted in the current TecDoc
Supplier Data import file. The TecDoc Supplier Data importer would
ignore the deleted value in the import file and left the existing
attribute value untouched. Now, the TecDoc Supplier Data importer has
been updated to include replacement rules that check the previously
imported file and compares to the current file being imported. If the
previous import populated an attribute value and the current import does
not contain the same attribute, then the import will remove the existing
attribute value to be null.

PRODOC note: NGK-583Updated the error message displayed in different
cases of Country component to be more descriptive

The error message displayed when the system encountered the following
cases has been updated in Web UI to avoid confusion for users.

-   The created country objects do not have the country attribute
    populated.
-   The LOV used for attribute does not contain a value that is linked
    to a corresponding country object.
-   Duplicate LOV values in the LOV.

PRODOC note: NGK-654Corrected TAF stacktrace that would occur while
importing TecDoc Reference Data file

Corrected an error in Validation state that would occur while importing
TecDoc Reference Data file. Previously, the presence of TAF table 115
would cause a stacktrace error to occur during conversion. TAF table 115
has now been removed from validation, therefore the validation state no
longer displays the \'Wrong file name or missing in code. Code has not
table 115 to file\' message.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/381/issue-381839-HOTFIX-3668.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/381/issue-381839-HOTFIX-3668.spr]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

Reference Delegation Screen topic

The **Reference Delegation Screen** topic addresses using and
configuring the Reference Delegation Screen. The topic has been added to
the **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Initial Object Bind topic

The **Initial Object Bind** topic addresses using and configuring the
Initial Object Bind. The topic has been added to the **Resource
Materials** section of the **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Modifying Mapper Rows on the Onboarding Mapping Details Screen topic

The **Modifying Mapper Rows on the Onboarding Mapping Details Screen**
topic explains a detailed procedure to add, delete, enable, disable, and
many other factors of the Mapper Rows available on the Onboarding
Mapping Details Screen. The topic has been added to the **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

Application Mapping Plugin topic

The **Application Mapping Plugin** topic ([here]{.mcFormatColor
style="color: Blue;"}) has been added to the new **Data Onboarding
Solution** section of the **Automotive Reference Guide**.

Target Hierarchy Editor Dialog topic

The new **Target Hierarchy Editor Dialog** topic addresses using and
configuring the Target Hierarchy Editor parameter. It also includes the
details on creating Target hierarchy and generic use cases to help
understand the area of usage of this solution. The documents can be
found within the **Data Onboarding Solution** section of the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.25.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.3 MP2 baseline
recipe:

[to:step/platform/step-9.3-mp2.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
 
