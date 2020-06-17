---
description: PMDM for Automotive 9.1 MP1 April 2019 Patch Notes
title: PMDM for Automotive 9.1 MP1 April 2019 Patch Notes
---

PMDM for Automotive 9.1 MP1 Patch Notes {#pmdm-for-automotive-9.1-mp1-patch-notes .MPN}
=======================================

Release Date: April 11, 2019 {#release-date-april-11-2019 style="text-align: center;"}
----------------------------

Announcement {#announcement .MPNDocumentation}
------------

Known Issue with the PAdb importer

With this maintenance patch, there is a limitation where users may
encounter a STACKTRACE error when importing the latest version of the
PAdb files. This error would be encountered only in a situation when the
legacy PAdb LOVs are made to replace with new values during import and
those LOVs are used in a PAdb attribute referenced to a Classification
with an existing LOV filter. If there are no such filters set, the PAdb
file will be imported without any errors. We suggest that users refrain
from importing the PAdb file in this release. We plan on releasing the
next automotive 9.1 MP2 patch in May. If there is a fix for the PAdb
importer prior to that release, then we will backport and create a
hotfix for the automotive 9.1 MP1 release.

STEP Automotive solution will hereafter be referred as PMDM for
Automotive solution

With this maintenance patch, 'STEP Automotive' instances in online help
have been updated to 'Product MDM for Automotive' and 'PMDM for
Automotive' throughout to more accurately refer to the automotive
solution.

New Features {#new-features .MPNNewFeatures}
------------

PMDM for Automotive print table transformation enhancements

PRODOC note: KIHE PDO-3365

One new table transformation, an enhancement of an existing table
transformation, and three new text transformations have been introduced
to the PMDM for Automotive print solution. See the **Automotive 9.1 MP1
Print Table Enhancements** topic[ here]{.mcFormatColor
style="color: Blue;"} for more information.

PRODOC note: BOND PDO-3079 and 3225PMDM for Automotive solution supports
the latest versions of AutoCare supplier data

PMDM for Automotive solution now also supports import and export of PIES
6.7, PIES 7.0 and ACES 4.0 versions.

The AutoCare ACES Application Exporter now provides an option to select
between ACES 3.0, 3.2, and 4.0 versions in the \'Version\' parameter
within \'Select Format\' dialog as displayed below. For more
information, see the **AutoCare ACES Application Exporter** topic of
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/Aces%204.0.png)

The AutoCare PIES 6.5 Exporter will hereafter be called **AutoCare PIES
Exporter** with an option to select amongst PIES 6.5, 6.7 and 7.0
versions in the \'Version\' parameter within \'Select Format\' dialog as
shown below. For more information, see the **AutoCare PIES Exporter**
topic of **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/PIES%20Exporter.png)

PRODOC note: BOND RDCUST-3348The PIES files exported in the format PIES
6.7 and 7.0 now includes data from attributes \'AC\_PAdb\_VersionDate\'
and \'AC\_PCdbVersionDate\'. These data are displayed within the Header
segment of the exported file.

Existing implementations must run step 1 of the Automotive - AutoCare
Model Easy Setup in order to create the following:

-   PRODOC note: BOND RDCUST-3369Two VCdb description attributes (ID:
    AC\_VCdbEngineBlockID and AC\_VCdbEngineBoreStrokeID) under
    \'AutoCare VCdb Attributes\' attribute group (ID:
    AC\_VCdbAttributes).
-   PRODOC note: BOND RDCUST-3369Two ACES specification attributes (ID:
    AC\_ACESEngineBlockID and AC\_ACESEngineBoreStrokeID) under
    \'AutoCare ACES Attributes\' attribute group (ID:
    AC\_ACESAttributes).
-   PRODOC note: BOND RDCUST-3318A data container (ID:
    AC\_PIES\_Item\_Description) under \'PIES Description Segment DESC\'
    attribute group (ID: AC\_PIESDescriptionSegmentDESC) with three new
    description attributes linked to it: PIES Description, PIES
    Description Sequence Code, and PIES Desc Type.
-   PRODOC note: BOND RDCUST-3478Eight new attributes under \'PIES
    Digital Assets Segment ASST\' attribute group (ID:
    AC\_PIESDigitalAssetsSegmentASST) valid for \'PIES\_ Asset\' object
    types. The eight new attributes that gets created are: Duration,
    Duration UOM, Frame, Hemisphere, Plane, Plunge, Total Frames, and
    Total Planes.
-   PRODOC note: BOND RDCUST-3476Six new attributes under \'PIES Part
    Interchange Segment INTE\' attribute group (ID:
    AC\_PIESPartInterchangeSegmentINTE). These attributes can be
    exported in PIES 6.7 and PIES 7.0. The six new attributes that gets
    created are: Interchange Quantity, Interchange Quantity UOM, Item
    Equivalent UOM, Reference Item, SubBrand AAIAID, and SubBrand Label.
-   PRODOC note: BOND RDCUST-3456Two data containers to handle multiple
    PriceType entries. Data container ID: AC\_PIES\_PRCS will be valid
    on the PIES Products node to hold Prices Sheet data. While data
    container ID: AC\_PIES\_PRCE will be valid for PIES Items to hold
    item pricing data.
-   PRODOC note: BOND RDCUST-3468A new LOV (ID:
    AC\_PIESHazardousMaterialLabelCode) valid to a new attribute (ID:
    AC\_PIES\_HAZMHazardousMaterialLabelCode). This attribute value can
    be exported within the PIES 6.7 and PIES 7.0 files upon selection of
    the \'Packaging\' and \'Hazardous Material\' parameters within the
    \'Advanced\' tab of the Export Manager wizard (as shown below). For
    more information, see the **AutoCare PIES Exporter** topic of
    **Automotive Reference Guide**[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/Advanced%20Tab.png){.Inch6}

PRODOC note: BOND RDCUST-3455 and 3520All PIES related LOVs shall
hereafter be created by importing the PCdb file

All PIES related LOVs shall hereafter be created by importing the PCdb
file and not by the Easy Setup action. Previously, all PIES related LOVs
were hardcoded into STEP by the Easy Setup action.

PRODOC note: BOND RDCUST-3456Changed the Data Model structure for
handling of PIES Price segment

All PIES Price segment information imported through the PIES file will
hereafter be created as Data Container Type in the system. Previously,
each PIES Pricing segment were stored in the system as attribute groups.
Users can add multiple price sheet information as data container
instances standing on PIES Products object in Data Containers tab. With
this structure of data model, user gets an option to export a case where
the PIES Item has different prices with the same price sheet. For more
information, see the **AutoCare PIES Exporter** topic of **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST- 3261, 3268, 3267, 3266Improved the ability of STEP
to suggest more potential Part Numbers in \'Part Number Suggestions\'
and \'Advanced Part Number Suggestions\' component

Now, with the addition of four new plugins (Referenced By, Referenced
Chain, Common number, and Common applications), STEP can suggest more
number of potential Part Numbers in the \'Part Number Suggestions\' and
\'Advanced Part Number Suggestions\' component. For more information,
see the **Configuring the Part Number Suggestions Component** section of
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: BOND RDCUST-3430New search and add feature in the Part
Number References component

Part Number References and Advanced Part Number References components
now includes a feature to add an existing competitor and/or OE part
number reference by manually searching through its *attribute* value and
manufacturer name. Previously, the typeahead field was limited to add an
existing competitor and/or OE part number reference by allowing to
search only through the manufacturer name. To enable this feature, a
search attribute needs to be configured in the Part Number References
Properties dialog. For information about how to use this component, and
prerequisites, see the **Competitor and OE Numbers Solution** topic
within the **Automotive Reference Guide** found within the **Solution
Enablement** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: BOND RDCUST- 3525Improved the ability of ACES Importer to
create applications even if the part number (PIES Item) is missing in
the system

Changed the way the ACES importer handles the applications when part
number (PIES Item) information is missing in the STEP. Previously,
importing an ACES file requires that the associating part number (PIES
Item) must already exist before the application can be created. Now, a
new parameter called \'Create PIES items\' is available in the
Conversion state of ACES Import workflow as displayed in the screenshot
below. Selecting this parameter allows an ACES file to be imported even
if the part number does not already exist. The Part Terminology product
hierarchy and part numbers are created by the ACES import, and
applications are created below the part number.

![](../../Resources/Images/Release%20Notes/91mp13.png){.Inch6}

PRODOC note: BOND RDCUST- 2428Extended the ability of ACES importer to
create application records based on Year-Ranges

ACES importer now supports creation of application records based on the
Make, Model, and Year-Range combination. Previously, creation of
application records were created only based on the BaseVehicle ID. Now,
when the Year-Range, Make, and Model information is supplied in the ACES
file, an application record is created for each year that is within the
range, and the application is linked to the Base Vehicle that matches
the Year / Make / Model combination.

PRODOC note: BOND RDCUST- 3365New Automotive specific plugin \'Validate
Application conditions and start in workflow\' to initiate applications
with invalid vehicle configuration to the workflow

A new plugin \'Validate Application conditions and start in workflow\'
is available which when used within a business action can be used while
importing ACES file to create applications with invalid configurations
and initiate them into a workflow. The configured business action will
have a parameter to define which workflow to initiate the invalid
applications into. This Business action needs to be configured into the
Import action parameter in the ACES workflow Import state. After
configuration, when the ACES file is imported, all the invalid
applications will be initiated into the workflow defined in the Workflow
parameter (as shown below).

![](../../Resources/Images/Release%20Notes/91MP17.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST- 3398Updated ImportFlowExtension to be created as
plugins

Previously, ImportFlowExtensions were created as singletons. Now it is
changed to be created as plugins.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/335/issue-335228-HOTFIX-2914.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3431 Corrected Application Manager display of
saved search criteria in Vehicle Type Search Panel

Previously, when using the Application Manager to search for Make/Model
criteria, running the search, and then saving the search criteria within
the Vehicle Type Search Panel, the same saved search criteria would be
displayed in the adjacent Vehicle Type Search Panel too. Now, this is
corrected so that the search criteria saved in one particular Vehicle
Type Search Panel will not be displayed in other Vehicle Type Search
Panel.

PRODOC note: BOND RDCUST- 3010 Corrected display of the \'Manufacturer
References\' header in the Part Number Suggestions Properties dialog

Previously, when adding the Part Number Suggestions component in Node
Editor Properties, Part Number Suggestions Properties dialog displayed
the \'Manufacturer References\' header as \'Reference Numbers Make\'
(terminology error), and then saving the Part Number Suggestions
Properties dialog, the same header would be displayed as \'Manufacturer
References\' in the Part Number Suggestions Properties. Now, this is
corrected so that the term \'Manufacturer References\' will be displayed
as the default header name both in the case of dialog and Part Number
Suggestions Properties.

PRODOC note: BOND RDCUST- 3428 Improved the search time performance of
Application Manager screen

Previously, Application Manager search performance was delayed when
Business Conditions (Missing Application Conditions) were applied to the
Part Types. Now, there is a significant improvement in the search time
performance.

PRODOC note: BOND RDCUST-3430Corrected the inexactness while creating
part in \'Part Number References\' and \'Advanced Part Number
References\' components

Added a new parameter \'Reference Types to create\' in the Part Number
References and Advanced Part Number References components to define the
exact reference type while creating a part through the typeahead field.
Previously, when more than two reference types were present in the
\'Reference Types\' parameter, creating the part via the typeahead field
would create the part as a target object of any of the reference type
listed in the parameter. Now, whenever the part is created, the part
will be the target object of the reference type listed in the
\'Reference Types to create\' parameter.

PRODOC note: RDCUST-3513Fixed the Bulk Updates parameter in the Bulk
Applications Updates Properties dialog

Previously, a user was not able to add a Business Action to the Bulk
Updates parameter within the Bulk Applications Updates Properties dialog
within the Application Editor Screen (Parts) and Application Editor
Screen (Vehicles) screens. Now, the Bulk Applications Updates component
has been fixed to allow adding Business Actions to the Bulk Updates
parameter within the Application Editor Screens.

### AutoCare

PRODOC note: BOND RDCUST-3232Corrected PIES Exporter to include
inherited attribute values in the exported file

Previously, the PIES Exporter did not include some of the inherited
attribute values while exporting PIES Item. Now, the export mechanism is
refactored in the Conversion phase and includes the inherited attribute
values in the exported file.

PRODOC note: BOND RDCUST- 3453 Updated PAdb importer to check and warn
against mismatch in PAdb Version Date during Validation state

Previously, the PAdb importer did not check and compare the version date
in the imported file. Hereafter, importing the PAdb file will validate
the version date against the version date stored on the
\'AC\_PAdb\_VersionDate\' attribute which is valid on the PCdb root
classification object, and displays an error in the Validation state if
the imported file is older than the version date that exists in STEP.

In addition, the error message has been updated to say \"than\" instead
of \"that\". For example: Existing version \'2018-11-16\' is newer than
provided \'2018-10-26\'

PRODOC note: BOND RDCUST- 3452Fixed VCdb Importer to indicate correct
deletion data in \'Delete status\' attribute

Previously, when importing VCdb data file, if an object already exists
in the VCdb hierarchy with delete status flag = true and the same object
is imported again with the most current VCdb data file without any
changes, the importer was not clearing out the delete status flag. Now,
the delete flag is cleared for existing objects that are marked for
deletion when it is imported again through the VCdb import file with no
changes to the object.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/340/issue-340275-HOTFIX-2984.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3510Corrected the way the PIES Importer
creates ID for the Package objects

Changed the way the PIES Importer handles the ID of the Package objects,
the new ID pattern will be AC\_PIESPackage+hash. Previously, PIES
Importer was requiring that the PackageLevelGTIN field is populated when
a \<PackageUOM\> information is provided in the file. The absence of the
PackageLevelGTIN information would skip the Package UOM information
during the Conversion state and prevented the Package objects from
getting created. Now, with the new unique ID pattern, PIES Importer is
updated to create the Package UOM irrespective of the presence of
PackageLevelGTIN value. The parameters to generate the hash value are
BrandAAIAID, PartNumber, PackageUOM, QuantityofEaches, and if it exists
PackageLevelGTIN.

PRODOC note: BOND RDCUST- 3574Changed the way of handling ID pattern for
PIES HAZMat objects

Changed the way the PIES Importer handles the ID of the PIES HAZMat
objects. The change in the ID pattern for Packages had an adverse impact
of overshooting the character limits in the ID generation for PIES
HAZMat objects. Now, the new ID pattern is restructured to have a
pattern AC\_PIESHazMat\_Hash\[hashofPackageID+HazMatparameters\]. The
included Hazmat parameters for the hash value are Shipping Scope, Bulk,
Regulating Country of Origin, Transport Method, and Regulated.

PRODOC note: BOND RDCUST- 3564Updated the PIES Importer to create PIES
Item under \'Unknown\' hierarchy when PartTerminologyID information is
missing in imported file

Changed the way the PIES Importer handles the PIES Items when
PartTerminologyID is missing in the imported file. Previously, when
importing the PIES file without the PartTerminologyID, the file would
import successfully without any warnings or errors, but the PIES Items
were not created in the system. Now, when such files are imported, the
following three level hierarchy is created in the system and the PIES
Item is stored under this \'Unknown\' PCdb Part Terminology object

-   Object name \'Unknown\' with object ID
    AC\_PIESPCdbCategory\_U\_\[BrandAAIAID\] and object type PIES PCdb
    Category
-   Object name \'Unknown\' with object ID
    AC\_PIESPCdbSubCategory\_U\_U\_\[BrandAAIAID\] and object type PIES
    PCdb Sub Category
-   Object name \'Unknown\' with object ID
    AC\_PIESPCdbPartTerminology\_U\_\[BrandAAIAID\] and object type PIES
    PCdb Part Terminology

PRODOC note: RDCUST- 3365Updated the business condition \'Validate
Application on import\' to provide an option to validate conditions
against vehicle configurations

Changed the way the ACES importer handles the applications when
applications with invalid vehicle configurations are loaded in the
system. Previously, importing an ACES file with applications holding
invalid vehicle configurations was imported flawless without validating
the conditions against vehicle configurations. Now, a new parameter
called \'Check configuration validity\' is available in the business
condition \'Validate Application on import\' which in turn is configured
in the Import state of ACES Import workflow as displayed in the
screenshot below. This parameter provides an option to either allow or
reject invalid applications. Selecting this parameter checkbox will fail
the import when any application record with invalid vehicle
configuration is present.

![](../../Resources/Images/Release%20Notes/91MP16.png)

The Business condition is configured in the Import state of ACES Import
workflow as displayed in the screenshot below.

![](../../Resources/Images/Release%20Notes/91MP15.png){.Inch6}

PRODOC note: RDCUST- 3596Fixed problem with delete flags being wrongly
cleared

Previously, if a delete flag (for example, attribute Delete Status =
true) was set on an object, importing a file that does not contain that
object would remove the delete flag even though the object is expected
to still remain flagged as deleted. Now, when an object is marked for
deletion, the delete value of \'true\' on the delete attribute remains
as \'true\' unless that object is resurrected in a later imported file.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/352/issue-352163-HOTFIX-3146.spr]{.commandfont}

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/352/issue-352163-HOTFIX-3164.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.0 MP5 + Automotive 9.0 MP3:**[
to:hotfix/352/issue-352163-HOTFIX-3164.spr]{.commandfont}

PRODOC note: BOND RDCUST- 2580Corrected PIES import error

Previously, using a business rule in a PIES Importer would cause it to
fail with a 'Failed during import of files with following exception:
com.stibo.core.domain.importer.FatalImportException: Import encountered
node data after node children while using Business Rules in node' error.
This has been fixed to change the order of PIES item components so that
the children comes last to allow a business rule to run on the objects.
For more information, see the **Business Action: Set Import Status
Attributes** topic in the **Automotive Reference Guide**[
here]{.mcFormatColor style="color: Blue;"}.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/341/issue-341808-HOTFIX-3011.spr]{.commandfont}

### NAPA

PRODOC note: RDCUST- 3382Fixed the way the NAPA vehicle importer
generates sister vehicles

The Vehicle Importer now establishes multiple references for each of the
vehicles that are grouped with the same Sister identifier to one
another. Previously, the NAPA\_SisterVehicle Classification Reference
Type would not allow multiple references and the reference that is
created on the NAPA\_Year object through the NAPA Vehicle Importer was
creating the wrong reference. The issue is fixed now.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/335/issue-335665-HOTFIX-2924.spr]{.commandfont}

**Existing Implementations:** After applying the hotfix, users should
follow the steps below:

1.  Run step 1 of Easy Setup to change Classification Reference Type ID
    = NAPA\_SisterVehicle to have Allow multiple references = Yes, or
    just go to the reference type and manually change the parameter.
2.  Import the valid Vehicles file again to establish the new Sister
    Vehicle references.

PRODOC note: BOND RDCUST-3512Updated NAPA Application Exporter to
contain only 24 fields

The NAPA Application Exporter contains 24 fields instead of 27 fields.
Field 25 (Axles), Field 26 (Chassis), and Field 27 (Vehicle Country) are
omitted.

**Hotfix recipe compatible with STEP 9.0 MP5 + Automotive 9.0 MP3:**[
to:hotfix/343/issue-343489-HOTFIX-3046.spr]{.commandfont}

PRODOC note: RDCUST- 3516 Corrected exception error in Delta Calculation
state during NAPA Vehicle import

Corrected an exception method error (NoSuchFile) that displayed in Delta
Calculation state when importing NAPA ValidVehicle file.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/343/issue-343642-HOTFIX-3052.spr]{.commandfont}

### TecDoc {#tecdoc conditions="Primary.Under Construction"}

PRODOC note: BOND RDCUST- 2580Corrected TAF import error

Corrected an error that would occur while importing TecDoc Reference
Data file (Error: Import encountered node data after node children while
using Business Rules in node \'TD\_SEARCH\_0300002\': \<MetaData\>) if
\'SetChangeFlags\' business action is set in the Import state. Now, with
the \'SetChangeFlags\' business action set in the Import state, STEP
continues the import without displaying the error. For more information,
see the **Business Action: Set Import Status Attributes** topic in the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/341/issue-341808-HOTFIX-3011.spr]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC- 1244New AutoCare ACES Importer documentation

The new **AutoCare ACES Importer** section addresses using and
configuring the AutoCare ACES Importer and can be found within the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: PRODOC- 1742 New set of Use Cases on Business Action: Set
Import Status Attributes

The business action \'Set Import Status Attributes\' when configured
with valid attributes provides many use cases which the user can use to
track the deleted, changed, and newly added objects during the import.
The **Use Case Appendix** section under Business Action: Set Import
Status Attributes topic addresses various use cases on business action
\'Set Import Status Attributes\' and can be found within the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: PRODOC- 1664, 1395, 1519, 1517New Competitor and OE Numbers
Solution documentation

The new **Competitor and OE Numbers Solution** section addresses using
and configuring the Part Number References and Part Number Suggestions
components and can be found within the **Automotive Reference Guide**[
here]{.mcFormatColor style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.16.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.1 MP3
baseline recipe:

[to:step/trailblazer/step-9.1-mp3.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system cannot be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
