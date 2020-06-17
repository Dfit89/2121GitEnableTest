---
description: 'Automotive Solution: PMDM for Automotive 8.3 Release
  Notes'
title: PMDM for Automotive 8.3 Release Notes
---

PMDM for Automotive 8.3 Release Notes {#pmdm-for-automotive-8.3-release-notes .MPN}
=====================================

Release Date: February 2, 2018 {#release-date-february-2-2018 .MPN}
------------------------------

**Stibo Systems is excited to share the Automotive 8.3 solution, built
using the recently released STEP 8.3 platform.**

Announcement {#announcement .MPNDocumentation}
------------

The NAPA standard is now complete. Including recent NAPA data model
changes handled with Easy Setup, and production-readiness initiatives
conducted through the development cycle to ensure a high quality
release.

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-2147Easy Setup now creates new File Loading Widgets
for each standard\'s importers

Previously, in order for users to process an import that involved a
hotfolder, they would need to access the application server, find the
hotfolder, drop the file into the hotfolder, and then wait for the
scheduled IIEP to pick up the file (or access Workbench and invoke the
IIEP). Now users can login to the Web UI and from the homepage easily
drag and drop a file onto a File Loading Widget. Additionally, Easy
Setup functionality for all three standards has been updated to
automatically create and configure File Loading Widgets for each
standards commonly used reference and supplier data imports.

This update is part of Easy Setup via **Automotive - \[Standard\] Model
\> 2. Configure \[Standard\] Import Process**.

**Existing Implementations**: Please manually update existing Web UI\'s
with the new File Loading Widgets, because the Easy Setup functionality
does not currently update existing Web UI configurations with the File
Loading Widgets. For more information on how to configure a File Loading
Widget, see the Homepage Widgets section ([here]{.mcFormatColor
style="color: Blue;"}) of Online Help.

PRODOC note: RDCUST-2488NAPA Easy Setup and Application Exporter now
support exporting delta files

In order for the NAPA Application Exporter to offer the option to handle
exporting delta files, the Easy Setup via Automotive - NAPA Model \> 1.
Configure NAPA Data Model has been updated to create: two new object
types (ExportBaselineRoot and ExportBaselineAsset), a new attribute (ID
= NAPA\_PartNumber), new parameters for the NAPA Application Exporter
format to export either in \'Full\' or \'Delta\' mode, and to select
which baseline to run the delta export on. For more information, see the
NAPA Application Export section ([here]{.mcFormatColor
style="color: Blue;"}) of the Automotive Reference Guide.

The Automotive solution does not provide an importer that will
specifically create the NAPA Product hierarchy. Therefore, the NAPA
Product hierarchy must be created manually in STEP Workbench before
creating applications using the Application Importer. The NAPA Product
MPCC is expected to have an ID structure prefixed with **NAPA\_MPCC\_**,
and the NAPA Product is expected to have the following ID structure:
**NAPA\_Product\_\[Line Abbrev\]\[PartNumber\]** (i.e.,
NAPA\_Product\_FIL1515). It is important to note that when the user
creates the NAPA Product, that the **NAPA\_PartNumber** attribute must
also be populated with the Part Number value, as this attribute value is
used to the determine the Part Number in the NAPA Application and
Interchange Exporter.

PRODOC note: RDCUST-2681NAPA Interchange Importer now creates new
NAPA Interchange Product objects

Previously, the NAPA Interchange Importer did not create new Interchange
Product objects, it only makes references from a NAPA Product to an
existing Interchange Product object. The interchange import file
contains all the data that is needed in order to create Interchange
Product objects on import, so NAPA Interchange Importer has been updated
to create new Interchange Product objects if they don\'t already exist
in STEP.

The following must exist in STEP for new Interchange Products to be
created successfully:

-   The data in field 3 of the import file must be NAPA Interchange
    Manufacturer product objects that are created from the Translation
    Importer with data coming from the manufacturer.txt file.

```{=html}
<!-- -->
```
-   The data in field 6 of the import file comes from the iccomments.txt
    file that is imported into STEP as values for LOV ID =
    NAPA\_InterchangeComment through the Translation Importer.
-   The NAPA Product objects must be created with the NAPA standard ID
    format and the NAPA\_PartNumber attribute must be populated with the
    Part Number as the value.

When an interchange file is imported through the Interchange Importer,
the following will occur:

-   If the interchange object doesn\'t already exist in STEP, the
    Interchange Importer will create a new NAPA Interchange Product
    *(the name comes from field 3 of the import file)* object below the
    Interchange Manufacturer:

![](../../Resources/Images/MPNotes/New%20Interchange%20Product%20object.png)

-   A reference will be established between the NAPA Product to
    Interchange Product:

![](../../Resources/Images/MPNotes/NAPA1.png)

-   Set the value for the Interchange Comment on the reference if an ID
    is provided in field 6:

![](../../Resources/Images/MPNotes/Interchange%20Comment.png)

PRODOC note: RDCUST-2678NAPA Interchange Exporter

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

![](../../Resources/Images/MPNotes/NAPA%20Interchange%20Exporter.png)

PRODOC note: RDCUST-2535/2711Updated NAPA Easy Setup and Vehicle
Importer to remove data model redundancies

To remove vehicle data model redundancies, NAPA Easy Setup will no
longer create Year Engine, Year Submodel, and All Valid Vehicles object
types. Instead, two new objects (NAPA\_EngineRoot and NAPA\_Years) will
be created, NAPA Engine is moved below NAPA Vehicle Option Root node,
and NAPA Valid Vehicle is created below NAPA Year. The new Vehicle
classification will display as shown in the screenshot below:

![](../../Resources/Images/MPNotes/Vehicle%20data%20model.png)

Also, a new Classification Reference Type has been created
(NAPA\_ValidVehicleToSubmodel) to reference Valid Vehicle to Submodel.

The Vehicle Importer has been updated to do the following:

-   No longer create Year Engine, Year Submodel, and All Valid Vehicle
    objects based on data from the NapaValidVehicleMaster.txt file.

```{=html}
<!-- -->
```
-   No longer create a reference from Year Engine to Engine objects, and
    Year Submodel to Submodel objects.
-   Create the new NAPA Engine, NAPA Model, NAPA Years, and NAPA Valid
    Vehicle objects in the new data model structure.
-   Create a reference from Valid Vehicle to Submodel.

The new data model objects and reference can be created by running Easy
Setup via Automotive - NAPA Model \> 1. Configure NAPA Data Model.

**Existing Implementations**: please make the following changes
manually. The steps below will only need to be done once, and are
applicable for all bugfixes that involve the Vehicle Importer.

1.  Delete the NAPA Reference Data root Classification.
2.  Delete all references using Vehicle object types as source or target
    references. (NAPA\_ApplicationToEngine, NAPA\_ApplicationToSubmodel,
    NAPA\_ApplicationToYear, NAPA\_SisterVehicle,
    NAPA\_ValidVehicleToEngine, NAPA\_ValidVehicleToAxle,
    NAPA\_ValidVehicleToSubmodel, NAPA\_ValidVehicleToTransmissionType)
3.  Delete the NAPA\_VehicleTableRoot object type structure.
4.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to create the new vehicle data model and references.
5.  Re-import the NAPA Valid Vehicle file.

PRODOC note: RDCUST-2704Updated AutoCare ACES Import workflow Conversion
state to have a new parameter to omit application names in delta files

The ACES Importer creates application objects and sets the STEP Name to
be the same value as the Part Number. After the applications have been
created, users have the option to change the STEP Name to be something
other than the Part Number (i.e., Acura TSX 2010). An issue is
encountered when the next time that an ACES file is imported, the STEP
Name will get reverted to the Part Number again because the Conversion
is checking the name in the file against the name in the database, and
sees it as an update and is including those records in the delta file
even though nothing has changed in the record. To resolve this issue,
AutoCare ACES Import workflow has been updated to include a new
parameter called \'Omit application names\' in the Conversion state.
When this option is selected, the name of applications would be omitted
in the conversion process so that the record will not be included in the
delta file.

This fix has been backported to STEP 8.2. The recipe to patch with 8.2
is: to:hotfix/300/issue-300893-HOTFIX-2176.spr

![](../../Resources/Images/MPNotes/Omit%20application%20names%20parameter.png)

![](../../Resources/Images/MPNotes/Omit%20application%20names%20parameter.png)

PRODOC note: RDCUST-2508New parameter to support delete status in change
flag functionality

Previously, the change flag functionality was not handled ideally and
resulted in New records having a \'true\' change flag written for both a
new record and an updated record. To handle this functionality properly,
the logic has been improved and a new \'Deleted object attribute\'
parameter has been added to support Delete status as well. (The
attribute that is used in the new parameter should be the same attribute
that is configured in the delta calculation.)

![](../../Resources/Images/MPNotes/New%20Delete%20Status%20parameter%20for%20change%20flags.png)

The result will be that only a new record will get a new flag (i.e., New
Object = true), only an existing record that is getting updated will get
an updated flag (i.e., Changed Object = true), and only an existing
record that is marked for deletion will get a delete flag (i.e., Delete
Status = true).

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: RDCUST-2595Fixed \'Offending stack trace\' warning in log
for workflow Import state

Previously, an \'Offending stack trace\' warning would be displayed in
the log in the workflow \'Import\' state to indicate that the import is
handling parallel threads in an unsafe way. The importer has been fixed
to no longer use the wrong threads for reporting and status so that the
\'Offending stack trace\' warning will no longer appear in the log.

PRODOC note: RDCUST-2612Fixed NumberFormatException error in PIES and
ACES Exporter

Previously, if a PIES or ACES attribute has a non-numeric value where
the code is expecting a numeric value, then the PIES or ACES export
would fail with a java.lang.NumberFormatException error. PIES and ACES
Exporter has been updated to handle NumberFormatException to no longer
throw an error if these attributes have non-numeric values and the
exporter will continue to run successfully.

PRODOC note: RDCUST-2316/2157Add XSD validation for PIES and ACES
Exporters

Previously, PIES and ACES exporters did not validate against the XSD,
which lead to all parts and applications being exported, even though
required data was missing for those records. PIES and ACES exporters
have been updated to validate against the XSD, and any errors that are
encountered are written to the Background Process Execution Report.

PRODOC note: RDCUST-2656Updated ACES Importer to allow more than 100
objects in Delta Calculation delete xml file

Previously, ACES Complete Replacement using \'context\' delta
calculation method only included a maximum of 100 objects in the Delta
Calculation deleteFile.xml file even though there are \>100 objects that
should be included. The ACES Importer Delta Calculation has been fixed
so that there is no longer a limit on how many objects the delete file
can contain.

PRODOC note: RDCUST-2579Updated Asset Exporter to use a
Business Condition for filtering

Step 3 of the Asset Exporter wizard has an option to use a Business
Condition to filter out assets from the exported file. Previously, using
a Business Condition did not work with this option and that has now been
resolved.

PRODOC note: RDCUST-2577Updated Asset Exporter to no longer display
duplicate Delta Baselines

Step 4 of the Asset Exporter wizard has an option to use a saved asset
export configuration as a Delta Baseline. Previously, the Delta Baseline
dropdown list would display duplicate options with the same date and
timestamp to select from. This has been fixed so that only one unique
option is listed per date and timestamp.

PRODOC note: RDCUST-2524Updated parameter label for Change part, Copy
application to other part, and Copy application to other assembly
Business Actions

Previously, the parameter label was incorrect for three Business
Actions. The parameter label has been updated for:

-   \'Change part\' business action to be \'Part parameter key.\'

```{=html}
<!-- -->
```
-   \'Copy application to other part\' business action to be \'Copy
    application to other part parameter key.\'
-   \'Copy application to other assembly\' business action to be \'Copy
    application to other assembly parameter key.\'

PRODOC note: RDCUST-2427Updated Delta Calculation to include or filter
away setup objects

Previously, the delta calculation process across all importers looks
only at products and classifications to include in the delta calculation
file. Everything else is ignored by the calculation, meaning that the
data is always written to the delta calculation files whether it has
changed or not. For example, LOVs in an import file will have all LOVs
with all values written every time to the delta calculation file, even
when nothing has changed on any of the LOVs.

The delta calculation service has been updated to take setup objects
into account, where setup objects (LOVs, attributes, reference types,
etc.) that have not changed will be filtered away and not be included in
the delta calculation file. Only changed setup objects will be included
in the delta calculation file. This is done by comparing what is in the
import file to what\'s in the database whether \'context\' or \'file\'
delta calculation method is used.

The importers will not handle deleted setup objects, this will instead
be reported as a warning in the delta calculation background process
Execution Report. For example, if there are LOV values that are in the
database but are no longer in the import file, then there will be a
warning in the delta calculation background process Execution Report
listing the LOV and values that are missing in the import file. In this
case, the user will need to check the delta calculation report and
manually carry out the deletion of the LOV values.

PRODOC note: RDCUST-2600Updated Delta Calculation \'file\' method to
ignore files that have never been imported

Previously in the Delta Calculation state in any importer, using the
\'file\' method would incorrectly compare the file that\'s getting
imported against the most recent file in the workflow, even if the most
recent file wasn\'t imported successfully. The delta calculation should
instead compare against the most recent file in the workflow that has
exited the \'Import\' state via the bgp.succeeded or
bgp.completedwitherrors transitions. The \'file\' method for Delta
Calculation has been updated to ignore files that was never imported
when doing the delta calculation.

PRODOC note: RDCUST-2382Updated Root Node for NodePicker in Application
Set Assembly Header component in Application Editor

Previously when clicking on a NodePicker to select a new vehicle in
Application Editor, all root classifications for all standards would be
displayed rather than just the vehicle root classification. Application
Set Assembly Header component has been updated to only display the
vehicle root classification that applies for each standard. The title in
the component has also been updated so that AutoCare and NAPA will show
\'Select Vehicle\' while TecDoc will show \'Select Assembly.\'

PRODOC note: RDCUST-2599Updated Application Condition Header - Group
component to have the same width for both LOV and Text fields in Value
Editor

The width of the fields in the conditions Value Editor window has been
updated to be aligned on both the left and right side. Previously, the
width of LOV fields were shorter than the width of Text fields.

PRODOC note: RDCUST-2603Updated Application Editor to no longer create
multiple applications when a part is added to a missing application

Previously, when a user adds a part to a missing application in
Application Editor and the autosave option is enabled, the system would
create three new applications with the same data. This has been fixed so
that after adding a part to a missing application and autosave is
enabled, only one new application will be created.

PRODOC note: RDCUST-2635Updated alignment of click targets in
Application Editor

Previously in Application Editor, if a user resize a column that
contains a click target that would cause the content in the column to
wrap, the click target would be misaligned. For example, the Vehicle
column would have the click target as top aligned, while the Part Number
column would be middle aligned. Application Editor has been updated to
always place the click target to be top aligned.

PRODOC note: RDCUST-2520Fixed filtering in Application Editor table
column heading

Previously, filtering in Application Editor didn\'t display any of the
cell contents in the filter. Application Editor has been fixed to
properly display filtered column values. For values that have been added
or deleted, the change must be saved first before it is reflected in the
filtered list. For consolidated conditions in the Options column
(Application Condition Header - Group), if a record has multiple options
defined, setting the filter to include only one option will still show
the record. The only way for the filter to exclude something is to have
a situation where ALL options populated for the record are unchecked in
the filter.

PRODOC note: RDCUST-2590Fixed filtering in Application Editor table
column heading for missing applications

Previously, filtering in Application Editor didn\'t display the cell
contents in the filter from missing applications. Application Editor has
been fixed to include values from missing applications in the filtered
list.

PRODOC note: RDCUST-2507Updated Application Condition Header - Group
component in Application Editor to be able to tab through condition
fields

The Application Condition Header - Group component in Application Editor
has been improved so that users can use the Tab and Shift+Tab to
navigate through all conditions. When the user changes at least one of
the field value the \'OK\' button will be enabled.

**Limitations:**

1.  Once the focus is on the \'OK\' or \'Cancel\' button, Tab and
    Shift+Tab will no longer work in the conditions area because the
    buttons do not belong to the body of the component that holds the
    conditions.
2.  If the last field in the conditions area is a Text field and that is
    the only value that the user populates, the user will need to hit
    \'Enter\' before the \'OK\' button becomes enabled.

PRODOC note: RDCUST-2130Updated Application Condition to display
suggestion list for part number

Previously in Application Editor, when a user enters a new value for a
part number, no suggestion list is provided. This has now been updated
where a suggestion list is provided when the user starts entering a part
number. Note that in order for the suggestion list to be displayed, the
reference between the part and part type must be established first.
Also, it has been updated to no longer support inherited part type
links.

PRODOC note: RDCUST-2370Add new parameter to Application Set Part header
component in Application Editor to allow part type on application to
differ from part type on part

Previously in Application Editor, when a user tries to select a part for
the application that is different than the part type populated for the
application, an error would be displayed and the user is unable to
select the part. In order to support the option to allow an application
to be applicated for a different part type than the part, a new
parameter has been introduced in the Application Set Part header
component called \'Allow Applications Outside Part Type.\' This
parameter is defaulted to be unchecked so that existing functionality is
not affected.

But if a user should be able to select a part for the application that
has a different part type than the part itself, then the box should be
checked.

Add this new parameter by running Automotive - \[Standard\] Model \> 4.
Configure \[Standard\] WebUI Easy Setup.

![](../../Resources/Images/MPNotes/2.png)

![](../../Resources/Images/MPNotes/2.png)

PRODOC note: RDCUST-2506Updated Easy Setup for all three standards to
only show valid configuration changes

Previously, running step 3 of Easy Setup for all three standards would
always show that there were updates to the component model even though
the aspects of the component model have already been updated or created.
Step 3 of Easy Setup has been fixed to only show valid configuration
changes that need to be updated. If there aren\'t any updates, then
running step 3 of Easy Setup will show \'No changes.\'

This update is part of Automotive - \[Standard\] Model \> 3. Configure
\[Standard\] Types for Application Editor Easy Setup.

PRODOC note: RDCUST-2597Updated AutoCare Easy Setup to combine values
from ANSI X.12 Element 355 and 639 tables in AC\_PIESPriceUOM LOV

Previously, importing a PIES file with a price break value of \'EA\'
would cause the PIES import to fail because the \'EA\' value didn\'t
exist in the AC\_PIESPriceUOM LOV which had values from ANSI X.12
Element 639 table. In order to resolve the error, Easy Setup has been
updated to create the AC\_PIESPriceUOM LOV with values that are combined
from both the 355 and 639 tables.

This update can be applied by running Automotive - AutoCare Model \> 1.
Configure AutoCare Data Model Easy Setup.

PRODOC note: RDCUST-2010Updated AutoCare Easy Setup to no longer create
AC\_PIESAssetMaintenanceTypes LOV

Previously AutoCare Easy Setup created an LOV with
ID=AC\_PIESAssetMaintenanceTypes that didn\'t have an attribute
reference and wasn\'t used for anything. AutoCare Easy Setup has been
updated to no longer create this LOV.

**Existing implementations:** Please make this change manually by
deleting the AC\_PIESAssetMaintenanceTypes LOV.

PRODOC note: RDCUST-2049Updated AutoCare Easy Setup to create Part
Terminology To Application Note reference to allow multiple links

Previously the Part Terminology to Application Note reference did not
allow for more than one Part Type to be linked to an ACES Application
Note. AutoCare Easy Setup has been updated to create the Part
Terminology to Application Note reference with Allow multiple links=Yes.
When a user adds a Note reference to an application in Application
Editor, it will also create a reference between the Part Type that is
linked to the application to the Application Note.

This update is part of Automotive - AutoCare Model \> 3. Configure
AutoCare Types for Application Editor Easy Setup.

**Existing implementations:** Please make this change manually by going
to AC\_PartTerminologyToApplicationNote reference and setting Allow
multiple links=Yes.

PRODOC note: RDCUST-2354Updated AutoCare Easy Setup to create Product to
Part Terminology reference to not allow multiple links

The Product to Part Terminology reference is used to link parts and
applications to part types. Each part and each application can have only
one part type, but previously the Product to Part Terminology reference
allowed links to be made to multiple part types from the same part or
application. To prevent a part or application to reference multiple part
types, AutoCare Easy Setup has been updated to create the Product to
Part Terminology reference with Allow multiple links=No.

This update is part of Easy Setup via Automotive - AutoCare Model \> 1.
Configure AutoCare Data Model.

**Existing implementations:** Please make this change manually by going
to the AC\_ProductToPartTerminology reference and setting Allow multiple
links=No.

PRODOC note: RDCUST-1992Updated AutoCare Easy Setup to create the
AC\_PIESContainerType LOV with the correct values and ID and Updated
PIES Importer to use IDs with the LOV

Previously, errors were encountered during PIES Import because certain
values were missing from the PIESContainerType LOV. Easy setup for
AutoCare has been updated to create the AC\_PIESContainerType LOV to use
IDs and Names with all of the allowable values defined in the PIES Field
Definition Document in table: ANSI X.12 Element 355.

This update can be applied by running Automotive - AutoCare Model \> 1.
Configure AutoCare Data Model Easy Setup.

In addition, the PIES Importer has been updated to looks at value IDs
rather than just at the values.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete attribute with ID=AC\_PIES\_ITEMContainerType.
2.  Delete LOV with ID=AC\_PIESContainerType.
3.  Run Automotive - AutoCare Model \> 1. Configure AutoCare Data Model
    Easy Setup to recreate the attribute and LOV with the correct values
    and IDs.

PRODOC note: RDCUST-1959Updated AutoCare Easy Setup and PIES Importer to
handle many asset types

In order to handle many PIES asset types, AutoCare Easy Setup has been
updated to create a new object type with ID=AC\_PIESAsset, a new asset
reference type with ID=AC\_PIESToAsset, and a new attribute with
ID=AC\_PIES\_ASSTAssetType.

This update can be applied by running Easy Setup via Automotive -
AutoCare Model \> 1. Configure AutoCare Data Model.

In addition, the PIES Importer has been updated to create all other
assets (aside from HMS, LGO, MSD, OWN, or P04) as object type \'PIES
Asset (General)\' and using the AC\_PIESToAsset reference to link the
PIES Item to the PIES Asset (General) object. And the
AC\_PIES\_ASSTAssetType attribute that is valid on the reference is
populated with the value from the AssetType tag in the input file.

PRODOC note: RDCUST-1962Updated AutoCare Easy Setup, PIES Importer, and
PIES Exporter to handle asset data

Previously certain PIES asset elements were missing in STEP and asset
data couldn\'t be stored for those missing elements. Easy setup for
AutoCare has been updated to create attributes and LOVs to store
FileType, FileSize, ColorMode, AssetDimensions UOM, AssetHeight,
AssetWidth, and AdditionalInformation.

This update can be applied by running Automotive - AutoCare Model \> 1.
Configure AutoCare Data Model Easy Setup.

In addition, the PIES Importer has been updated to write the asset data
to the new attributes. And the PIES Exporter has been updated to include
the asset data in the exported file.

PRODOC note: RDCUST-1956Updated PIES Importer to store PriceSheetName
and PriceSheetNumber data

PIES Importer has been updated to now create Price Sheet Name and Price
Sheet Number attributes if they don\'t already exist, and store the data
from the imported file in those attributes in STEP.

PRODOC note: RDCUST-1957Updated PIES Importer to store Price Break and
Price Break UOM data

PIES Importer has been updated to now create Price Break and Price Break
UOM attributes if they don\'t already exist, and store the data from the
imported file in those attributes in STEP.

PRODOC note: RDCUST-2040/2433Updated ACES and PIES Importers to validate
BrandAAIAID against Brand Table

Previously when importing a PIES or ACES file that had an invalid
BrandAAIAID, the file would complete processing successfully without any
errors and the PIES Item or application would still get created in STEP.
PIES and ACES Importers have been updated so that if an invalid Brand is
provided in the import file, an error would be written in the Background
Process Execution Report in the Conversion state indicating that the
part or application was not imported or updated because an invalid Brand
was supplied in the file. If the file contains other records with a
valid Brand, then the file will continue to process and create the
records with a valid Brand successfully.

PRODOC note: RDCUST-2644/2685Updated PIES and ACES Importer to handle
zip files

PIES and ACES xml files can contain many records that make the file size
large and users therefore zip the file. Previously, attempting to import
a PIES or ACES zip file would generate a stacktrace error and the file
would fail to import. PIES and ACES Importer have been updated to handle
zip files containing PIES or ACES xml files. If the zip file contains
multiple xml files, the importer will unzip the file and process each
xml file individually. Users still have the option to import just the
xml files without zipping it.

PRODOC note: RDCUST-2567Updated NAPA Easy Setup to update Import
workflow parameters

Previously, all NAPA import workflows have the STEPXML attachment ID in
the Conversion workflow state indicated as \'convertVehicleTable,\'
which only makes sense for the Vehicle Importer. NAPA Easy Setup has
been updated to change the STEPXML attachment ID to be called
\'convert\' instead so that it is applicable to all importers.

This update can be applied by running Automotive - NAPA Model \> 2.
Configure NAPA Import Process Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Go to System Setup tab \> Workflows \> right-click on each NAPA
    Import workflow \> select \'Edit STEP Workflow.\'
2.  Double-click on the \'Conversion\' state \> go to the \[On Entry\]
    tab and click on the Business Action to edit it.
3.  Change the \'STEP XML attachment ID\' parameter from
    \'convertVehicleTable\' to \'convert.\'
4.  Save and Exit the workflow.

PRODOC note: RDCUST-2563Updated NAPA Conversion service to include
\'Product lines\' parameter only for Translation Importer

Previously, the NAPA Conversion Background Process Service that is used
by all NAPA Importers included a \'Product lines\' parameter, even
though the parameter is only applicable for the Translation Importer.

The \[NAPAToStepXMLConvertService\] Background Process Service has been
updated to no longer include the \'Product lines\' parameter. A new
Background Process Service has been introduced called
\[NAPATransToStepXMLConvertService\] that contains the \'Product lines\'
parameter and is applied only to the NAPA Translation Import workflow.

This update can be applied by running Automotive - NAPA Model \> 2.
Configure NAPA Import Process Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Go to System Setup tab \> Workflows \> right-click on the NAPA
    Translation Import workflow \> select \'Edit STEP Workflow.\'
2.  Double-click on the \'Conversion\' state \> go to the \[On Entry\]
    tab and click on the Business Action to edit it.
3.  Change the \'Background Process Service\' parameter to
    \[NAPATransToStepXMLConvertService\].
4.  Save and Exit the workflow.

PRODOC note: RDCUST-2558Updated NAPA Translation Importer to handle
Product Lines parameter correctly if the Product Line already exists in
STEP

A \'Product Lines\' parameter exists in the NAPA Translation Importer in
the Conversion state. Previously, if a user adds a Product Line
Abbreviation to the parameter and the Product Line already exists in
STEP, the object would incorrectly get marked for deletion even though
the object is included in the import file. Translation Importer has been
updated so that if one or more Product Line Abbreviations are indicated
in the parameter, then those Product Line Abbreviations and all child
MPCCs should be added to STEP and **not** get marked for deletion unless
they are excluded from the import file.

This requires that the Delete Status attribute has been created, made
valid on the Product Line and MPCC objects, and indicated for use in the
correct workflow state.

PRODOC note: RDCUST-2689Updated NAPA Easy Setup to have new IDs for
Interchange Comment LOV and attribute

In order to make the ID naming be more consistent with the new
interchange data model, the attribute and LOV ID for \'NAPA\_ICComment\'
has been changed to \'NAPA\_InterchangeComment.\' The LOV maximum length
has also been increased from \'100\' to \'500\' to support interchange
comments that have more than 100 characters.

This update is part of Automotive - NAPA Model \> 1. Configure NAPA Data
Model Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete attribute with ID=NAPA\_ICComment.
2.  Delete LOV with ID=NAPA\_ICComment.
3.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to recreate the attribute and LOV with the correct IDs.

PRODOC note: RDCUST-2642Updated NAPA Easy Setup and Translation Importer
to handle Revision Date

Previously, Easy Setup created the NAPA\_RevisionDate to be valid for
unnecessary classification objects that do not need to have Revision
Date populated. Easy setup has been updated to make the attribute valid
only for NAPA\_ProductLineRoot and NAPA\_VehicleTableRoot classification
type.

This update is part of Automotive - NAPA Model \> 1. Configure NAPA Data
Model Easy Setup.

Translation Importer has been updated to populate the Revision Date
attribute on the NAPA\_ProductLineRoot node from the date that is
provided in the Translation import file name.

**Existing implementations:** Please make this change manually by going
to the attribute (ID=NAPA\_RevisionDate) and removing all Classification
Type validity except for: NAPA\_ProductLineRoot and
NAPA\_VehicleTableRoot.

PRODOC note: RDCUST-1612Updated NAPA Translation Importer to import
interchange comments as LOV values instead of Classification objects

The interchange comments found in the iccomments.txt file were
originally being imported into STEP as classification objects. The
decision was later made to create the interchange comments as LOV values
so that the values can be populated on the \'Product to Interchange
Product\' reference. Therefore, NAPA Translation Importer has been
updated to no longer create interchange comments as classification
objects, but as LOV values in LOV ID = NAPA\_InterchangeComment instead.
NAPA Easy Setup has also been updated to no longer create the
classification object types for the Interchange Comment root node.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the NAPA\_InterchangeCommentRoot and NAPA\_InterchangeComment
    classification hierarchy.
2.  Delete the NAPA\_InterchangeComment then
    NAPA\_InterchangeCommentRoot object types.

PRODOC note: RDCUST-2684Updated NAPA Easy Setup and Translation Importer
to import interchange manufacturer as Product instead of Classification
objects

Previously, the Translation Importer imports the manufacturer.txt file
and creates classification objects below the
NAPA\_InterchangeManufacturerRoot node.

In order to implement the change to now be able to create Interchange
Products in STEP, the same Interchange Manufacturer hierarchy needs to
exist in the Product Hierarchy. In order to prevent repetitive data
models, the NAPA Translation Importer has been updated to create
interchange manufacturers as product objects below the
NAPA\_InterchangeProductHierarchyRoot node and no longer create
interchange manufacturer classification objects.

NAPA Easy Setup has also been updated to no longer create the object
types for the Interchange Manufacturer classification objects, and
classification reference types that are no longer needed.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the NAPA\_InterchangeManufacturerRoot classification
    hierarchy.
2.  Delete the NAPA\_ICManufacturerToInterchangeMfr and
    NAPA\_InterchangeProductToICManufacturer Classification Reference
    Types.
3.  Delete the NAPA\_ProductToInterchangeProduct Product Reference type.
4.  Delete Classification and Product Object Types:
    NAPA\_InterchangeManufacturer, NAPA\_InterchangeManufacturerRoot,
    NAPA\_InterchangeProduct, and NAPA\_ICManufacturer.
5.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to recreate some objects with new IDs.

PRODOC note: RDCUST-2072Updated NAPA Easy Setup to add Application
Importer to Homepage Widget Grid in Web UI

Previously, the Application Import workflow was not included in the Web
UI. NAPA Easy Setup has been updated to add the Application Importer to
the home page widget grid in Web UI.

This update can be applied by running Automotive - NAPA Model \> 2.
Configure NAPA Import Process Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Go to System Setup tab \> Web UIs \> delete the existing \'NAPA Web
    UI.\'
2.  Run Automotive - NAPA Model \> 2. Configure NAPA Import Process Easy
    Setup to recreate the NAPA Web UI to include the Application
    Importer widget.

PRODOC note: RDCUST-2682Updated NAPA Easy Setup and Application Importer
to handle User Optional Field data

NAPA application files can contain data in field 24. This is an optional
numeric field called 'User Optional Field' that can be used by the
Supplier for miscellaneous data (Suppliers provide an ID to reference
back to the data in their database). Previously, NAPA Application
Importer ignored the field and did not store the data that was provided
in field 24 on the application. Automotive - NAPA Model \> 1. Configure
NAPA Data Model Easy Setup has been updated to create a new attribute
with ID=NAPA\_ApplicationUserOptionalField to hold the data for that
field. And NAPA Application Importer has been updated to populate the
attribute with a value if data is provided in field 24.

PRODOC note: RDCUST-2566Updated NAPA Application Importer to handle
Axle, Chassis, and Country data

Previously, NAPA Application Importer did not handle the data that was
provided in fields 25-27 and caused validation to fail indicating that
there were too many columns provided in the imported file.
NAPA Application Importer has been updated to create a reference to the
Axle object if data is provided in field 25 by using the classification
reference ID=NAPA\_ApplicationToAxle. If data is provided in field 26,
then the value would be populated in attribute
ID=NAPA\_ApplicationChassis. If data is provided in field 27, then the
value would be populated in attribute
ID=NAPA\_ApplicationVehicleCountry.

PRODOC note: RDCUST-2559Updated NAPA Application Importer to add a
prefix to the application record ID and add a name to the application
record

Previously, NAPA applications were created without a name and the ID
didn\'t have anything specific to identify that it is a NAPA application
record. NAPA Application Importer has been updated to add a Name to the
application record which uses fields 18 and 19 from the import file, as
well as add the prefix \'NAPA\_App\_\' to the ID hash function.

PRODOC note: RDCUST-2564Updated NAPA Application Importer to create
Product to MPCC local reference on applications

Classification reference with ID=NAPA\_ProductToMPCC has both
applications and products as sources and MPCC as targets. Previously,
NAPA Application Importer did not create a local reference on the
application, but just inherit from the product if one exists. NAPA
Application Importer has now been updated to create a local reference to
MPCC from the application. Field 17 in the input file identifies the
MPCC that the application should be linked to.

PRODOC note: RDCUST-2565Updated Delta Calculation in NAPA Application
Importer

Previously, delta calculation for NAPA Application Importer did not work
properly in reporting the records that need to be deleted or added in
the delta file. NAPA Application Importer has been updated to do delta
calculation using \'context \' method so that the data in the imported
file will be compared to the data in the database.

**Existing implementations:** Please make these changes manually by
going to the NAPA Application Import workflow \> \'Delta Calculation\'
state \> edit Business Action, and changing the \'Delta calculation
method\' parameter to be \'context.\'

PRODOC note: RDCUST-2560Updated NAPA Application Importer to include row
number in error messages

Previously, when an application can\'t be created due to a missing
parent product, vehicle, or MPCC, there isn\'t anything specific in the
error message to indicate which application didn\'t get created. NAPA
Application Importer has been updated to include the row number in the
error message for the application(s) that didn\'t get created.

PRODOC note: RDCUST-2561Fixed ValidateApplication Business Condition in
NAPA Application Importer

Previously, when importing an application file and there were both valid
applications and invalid applications, the entire import would fail and
the valid applications did not get created. The ValidateApplication
Business Condition has been fixed in NAPA Application Importer to
correctly handle valid applications. Applications which have a valid
vehicle, parent product, and MPCC will get created. Applications that
are invalid will get skipped and logged as an error in the Execution
report.

PRODOC note: RDCUST-2056Updated NAPA Easy Setup to make application
attributes be specification type

Previously, NAPA Easy Setup created application attributes as
Description type. NAPA Easy Setup has been updated to now create the
application attributes as Specification type.

This update can be applied by running **Easy Setup via the Automotive -
NAPA Model \> 1. Configure NAPA Data Model**.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete all application attributes below attribute group
    ID=NAPA\_ApplicationAttributes.
2.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to recreate the application attributes.

PRODOC note: RDCUST-2653Updated NAPA Easy Setup to create Product to
MPCC and Product to Interchange references to allow multiple links

A single Product (part) can have multiple MPCCs and multiple
interchanges.

Previously, NAPA Easy Setup created the link type from product to MPCC
and the reference type from product to interchanges to not allow
multiple links. This has now been updated where both are created to
allow multiple links.

This update is part of Easy Setup via Automotive - NAPA Model \> 1.
Configure NAPA Data Model.

**Existing implementations:** Please make these changes manually by
going to the NAPA\_ProductToMPCC and NAPA\_ProductToInterchangeProduct
references, and setting Allow multiple links=Yes.

PRODOC note: RDCUST-2533Updated NAPA Easy Setup to change Option IDs for
LOVs and attributes

Previously, some LOVs and attributes were created with \'Option2,\'
\'Option3,\' and \'Option4\' in the LOV and attribute IDs. NAPA Easy
Setup has been updated to create these LOVs and attributes with new IDs
to include \'Chassis\' or \'Vehicle\' instead of \'Option.\' The updates
can be applied by running **Automotive - NAPA Model \> 1. Configure NAPA
Data Model** Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the following attributes and LOVs: NAPA\_ApplicationOption2,
    NAPA\_Option2, NAPA\_Option2LOV, NAPA\_ApplicationOption3,
    NAPA\_Option3, and NAPA\_Option3LOV.
2.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to recreate the attributes and LOVs.

PRODOC note: RDCUST-2525Updated NAPA Easy Setup change the Name and ID
of the root NAPA attribute group

NAPA Easy Setup has been updated to rename the root NAPA attribute group
from \'NAPA Configuration\' to \'NAPA Attributes.\' All attribute
subgroups that were previously created below NAPA Configuration will now
be created below NAPA Attributes.

These updates can be applied for new and existing implementations by
running Easy Setup via Automotive - NAPA Model \> 1. Configure NAPA Data
Model.

PRODOC note: RDCUST-2534Updated NAPA Easy Setup to clean up Vehicle
attributes

To clean up Vehicle attributes that are not needed, NAPA Easy Setup has
been updated to no longer create the following attributes with
IDs=NAPA\_VehicleTypes, VehTypes, and VehType. Also, the attribute with
ID=NAPA\_VehicleType is now made valid only on NAPA Valid Vehicle
object.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the following attributes with IDs=NAPA\_VehicleTypes,
    VehTypes, and VehType.
2.  Select attribute with ID=NAPA\_VehicleType \> go to the \'Validity\'
    tab \> uncheck the \'NAPA Model\' object so that it is no longer a
    valid classification type (only NAPA Valid Vehicle should be
    selected).

PRODOC note: RDCUST-1761Updated NAPA Easy Setup to clean up Transmission
attributes

NAPA Easy Setup has been updated to no longer create eight Transmission
attributes that were not needed on applications as they already exist on
the Transmission Type object.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the following attributes with IDs:
    NAPA\_ApplicationTransAlsoKnownAs,
    NAPA\_ApplicationTransmissionCommonName,
    NAPA\_ApplicationTransmissionControlType,
    NAPA\_ApplicationTransmissionElecControl,
    NAPA\_ApplicationTransmissionMfringCode,
    NAPA\_ApplicationTransmissionMfrName,
    NAPA\_ApplicationTransmissionSpeeds, and
    NAPA\_ApplicationTransmissionType

PRODOC note: RDCUST-1450Updated NAPA Easy Setup to change Revision Date
attribute ID

Since the Revision Date attribute stores the date for many objects other
than valid vehicles, NAPA Easy Setup has been updated to change the ID
of the attribute from \'NAPA\_ValidVehiclesRevisionVersionDate\' to
\'NAPA\_RevisionDate.\'

The update can be applied by running Automotive - NAPA Model \> 1.
Configure NAPA Data Model Easy Setup.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the attribute with ID=NAPA\_ValidVehiclesRevisionVersionDate.
2.  Run Automotive - NAPA Model \> 1. Configure NAPA Data Model Easy
    Setup to create the new NAPA\_RevisionDate attribute.

PRODOC note: RDCUST-2529Updated NAPA Easy Setup to no longer create
NAPA\_DeleteBasedOnImport attribute and NAPA\_DeleteBasedOnImportLOV

NAPA Easy Setup has been updated to no longer create attribute with
ID=NAPA\_DeleteBasedOnImport and LOV with
ID=NAPA\_DeleteBasedOnImportLOV that were used in the Delta Calculation
state of the workflow. Instead, users should create a delete attribute
to handle deletes as described in the Quick Start Guide.

**Existing implementations:** Please make these changes manually by
following the steps below.

1.  Delete the attribute with ID=NAPA\_DeleteBasedOnImport.
2.  Delete the LOV with ID=NAPA\_DeleteBasedOnImportLOV.

PRODOC note: RDCUST-2573Updated NAPA Attribute Importer to accept both
txt and zip files

NAPA Attribute Importer has been updated to accept both a txt and zip
file format. Previously, importing a txt file would fail during
Conversion workflow state with a STACKTRACE:
java.lang.UnsupportedOperationException error.

PRODOC note: RDCUST-1557Updated NAPA Attribute Importer to write a
warning for attributes that have been unlinked from the MPCC

If an attribute is no longer included in the import file for an MPCC,
NAPA Attribute Importer has been updated to write a warning message in
the Background Process of the Conversion state to indicate that the
attribute is no longer linked to the MPCC and should be removed
manually. An example of the warning message:

Attribute \'NAPA\_PHdb\_3240480\' is no longer linked to
\'NAPA\_MPCC\_3334565\' and should be removed manually.

PRODOC note: RDCUST-2574Updated NAPA Attribute Importer to report a
product that can\'t be found from the DATA segment

The DATA segment in the NAPA Attribute import file can contain products
that should have attribute values written to it by the Attribute
Importer. Previously, there wasn\'t any reporting to indicate that a
product couldn\'t be matched. The Attribute Importer has been updated so
that if it finds a match, it writes the attribute data to the product.
But if a match is not found, then the execution report will report an
error stating that the product with ID \'\[ID\]\' cannot be found and
was skipped.

PRODOC note: RDCUST-2575Updated NAPA Attribute Importer to create LOVs
in a subgroup

In order to prevent too many LOVs from being created directly under the
NAPA\_LOVGroup root level, NAPA Attribute Importer has been updated to
create a subgroup with ID=NAPA\_AttributeLOVGroup and create LOVs with
hard domaintype below this new subgroup.

PRODOC note: RDCUST-2545/2652/2711Updated NAPA Vehicle Importer ID
structure to account for makes being used by more than one Vehicle Type

Previously, the Make ID does not take Vehicle Type into account, which
doesn\'t allow for a Make to exist for more than one Vehicle Type. In
order to support Make for multiple Vehicle Types, the NAPA Vehicle
Importer has been updated to change the ID structure of NAPA\_Make and
NAPA\_Model object types to include the Vehicle Type in the ID. For
example, NAPA Make previously would have the ID structure of
NAPA\_Make\_\[MakeID\], e.g., NAPA\_Make\_1. Now the ID structure would
be NAPA\_Make\_\[VehicleTypeID\]\_\[MakeID\], e.g., NAPA\_Make\_1\_1.

PRODOC note: RDCUST-2536Updated NAPA Easy Setup and Vehicle Importer to
clean up NAPA Transmission data

To make NAPA Transmission data more consistent with other data models,
Easy Setup has been updated to do the following:

-   No longer create the attribute with ID=TransMFGCode and
    TransMfrName.

```{=html}
<!-- -->
```
-   Change the attribute ID=NAPA\_TransmissionManufacturingCode to
    ID=NAPA\_TransmissionManufacturerCode and STEP Name to \'NAPA
    Transmission Manufacturer Code.\'
-   Change attribute with ID=NAPA\_TransmissionElectricControl to use
    LOV validation.
-   Create new object type ID=NAPA\_TransmissionTypeManufacturer that
    lives below the Transmission Root.

**Existing implementations:** Please make these changes manually to
delete the TransMFGCode, TransMfrName,
NAPA\_TransmissionManufacturingCode, and
NAPA\_TransmissionElectricControl attributes. Then run Automotive - NAPA
Model \> 1. Configure NAPA Data Model Easy Setup to create the new
NAPA\_RevisionDate attribute.

The Vehicle Importer has been updated to do the following:

-   Create NAPA\_TransmissionTypeManufacturer objects below the
    Transmission Root and create Transmission Type objects below the new
    Transmission Type Manufacturer objects.

```{=html}
<!-- -->
```
-   Import values to the new attributes from the NapaTransmission.txt
    file that is part of the NAPA Valid Vehicles reference data.

PRODOC note: RDCUST-2539Updated NAPA Easy Setup and Vehicle Importer to
clean up Axle data

To make Axle objects more consistent with other data models, Easy Setup
has been updated to create a new NAPA\_AxleManufacturer object, and two
new attributes to hold Axle Position and Axle Model values. Vehicle
Importer has been updated to create Axle object types as children of
Axle Manufacturer; change the STEP Name of the Axle to include
Manufacturer, Position, and Model; and populate the Axle Position and
Axle Model attributes with values from the imported file.

PRODOC note: RDCUST-2549Updated NAPA Vehicle Importer to write Year data
to NAPA Year objects

NAPA Vehicle Importer has been updated to write data to the NAPA\_Year
attribute that is valid on the NAPA\_Year objects, which it did not do
previously. The data for the value comes from the NapaValidVehicleMaster
file in the valid vehicles zip file.

PRODOC note: RDCUST-2550Updated NAPA Easy Setup and Vehicle Importer to
handle NAPA Engine Qualifier data

The NAPA Vehicle NapaEngine file that is part of the NAPA vehicle import
includes a 4th field referred to as the Engine Qualifier that was
previously not being handled. In order for the Engine Qualifier data to
be handled, Easy Setup has been updated to create a new attribute with
ID=NAPA\_EngineQualifier, and NAPA Vehicle Importer has been updated to
write data to the new attribute for Engine objects.

PRODOC note: RDCUST-2551Updated NAPA Vehicle Importer to add spaces to
Valid Vehicle STEP Name

NAPA Valid Vehicle Importer has been updated to add spaces to the STEP
Name for Valid Vehicle objects. For example, the previous name would be
\'ValidVehicle\_873821\' and is now changed to \'Valid Vehicle 873821.\'

PRODOC note: RDCUST-2552Updated NAPA Easy Setup and Vehicle Importer to
handle NAPA Sister Vehicle data

The NapaValidVehicleMaster file that is part of the NAPA vehicle import
includes field 30 (Sister Vehicle ID) and field 31 (Sister Vehicle Note)
which was previously not being handled. The Sister Vehicle ID is used to
identify records of vehicles in the single year table that are related
to each other (i.e., a 1993 Chevrolet Camaro and 1993 Pontiac Firebird
both have Sister Vehicle ID 193). In order for the Sister Vehicle data
to be handled, Easy Setup has been updated to create two new attributes
with ID=NAPA\_SisterVehicleID and NAPA\_SisterVehicleNote. And NAPA
Vehicle Importer has been updated to write data to the new attributes
for Valid Vehicle objects.

PRODOC note: RDCUST-2553Updated NAPA Easy Setup and Vehicle Importer to
handle NAPA Vehicle Comments data

The NapaValidVehicleMaster file that is part of the NAPA vehicle import
includes field 26 (Vehicle Comments) which was previously not being
handled. In order for the Vehicle Comments data to be handled, Easy
Setup has been updated to create a new attribute with
ID=NAPA\_VehicleComment, and NAPA Vehicle Importer has been updated to
write data to the new attribute for Valid Vehicle objects.

PRODOC note: RDCUST-2531Updated NAPA Vehicle Importer to transform date
into \'ISO Date and Time\' format

The date fields in the NapaValidVehicleMaster file from columns 19 and
20 is formatted in the M/D/YYYY H:MM:SS format. This doesn\'t conform to
\'ISO Date and Time\' format and would cause an error when the NAPA
Vehicle Importer tries to populate the attribute ID=NAPA\_RevisionDate
with the value from the NapaValidVehicleMaster file. NAPA Vehicle
Importer has been updated to transform the date to be in \'ISO Date and
Time\' format (YYYY-MM-DD HH:MM:SS) so that the value can be populated
for the Revision Date attribute.

PRODOC note: RDCUST-2070Updated NAPA and TecDoc Easy Setup to create
object types with names

NAPA and TecDoc Easy Setup has been updated to provide STEP names for
some Classification, Entity, and Product object types that previously
didn\'t have a name.

The update can be applied by running Automotive - NAPA/TecDoc Model \>
1. Configure NAPA/TecDoc Data Model Easy Setup. Some objects are also
created in step 3. Configure NAPA/TecDoc Type for Application Editor.

The Classification object types that had the STEP Names updated are:

-   TecDoc Supplier Images Root (ID=TD\_SupplierImagesRoot), Part Type
    Group Folder (ID=TD\_PartTypeGroupFolder), Part Type Group
    (ID=TD\_PartTypeGroup), Standard Assembly GA
    (ID=TD\_StandardAssemblyGA), Universal Assembly GA
    (ID=TD\_UniversalAssemblyGA), NAPA Part Terminology List Root
    (ID=NAPA\_PartTerminologyListRoot), and NAPA Part Terminology List
    (ID=NAPA\_PartTerminologyList)

The Entity object types that had the STEP Names updated are:

-   TecDoc Supplier Price List Root (ID=TD\_DS\_SupplierPriceListRoot),
    TecDoc Prices (ID=TD\_TecDocPrices), TecDoc Manufacturer Root
    (ID=TD\_Manufacturer\_Root), and TecDoc Resource Root
    (ID=TD\_ResourceRoot)

The Product object types that had the STEP Names updated are:

-   TecDoc Supplier Data Root (ID=TD\_DS\_SupplierDataRoot), TecDoc
    Reference Data Objects (ID=TD\_ReferenceDataObjects), LOV Filters
    (ID=TD\_LOVFilters), and LOV Filter GA (ID=TD\_LOVFilterGA)

**Existing implementations:** Please make these changes manually by
updating the STEP Name for each object type mentioned above.

PRODOC note: RDCUST-1943Updated NAPA and TecDoc Easy Setup to create
references with more consistent names

NAPA and TecDoc Easy Setup has been updated to provide STEP names for
some references that previously didn\'t have a name (e.g.,
\'NAPA\_PartRelation\' and \'TD\_PartRelation\'). And also to remove
\'NAPA\' and \'TD\' as a prefix in the reference names. The prefix in
the reference ID can be used to distinguish between the standards if the
reference names are the same.

The updates can be applied by running **Automotive - NAPA/TecDoc Model
\> 1. Configure NAPA/TecDoc Data Model** Easy Setup. Some references are
also created in step **3. Configure NAPA/TecDoc Type for Application
Editor**.

**Existing implementations:** Please update the STEP Name for these
references manually:

The name should not include the prefix standard (AutoCare, NAPA, or
TecDoc). The prefix in the ID can be used to distinguish between the
standards if the name is the same (e.g., Part Relation).

1.  Product Reference Types:

-   NAPA\_NoteSuggestionRelation has no name - should be "Note
    Suggestion Relation"

-   NAPA\_PartRelation has no name - should be "Part Relation"

-   TD\_PartRelation has no name - should be "Part Relation"

-   NAPA\_ApplicationToComment has a name, but it should be updated to
    "Application To Comment"

-   NAPA\_ProductToInterchangeProduct has a name, but it should be
    updated to "Product To Interchange Product"

-   TD\_GenericArticleToTextBlock has a name, but it should be updated
    to "Generic Article To Text Block"

    ![](../../Resources/Images/MPNotes/Reference%20Types%20for%20Name%20Update.png)

2.  Image and document Reference Types:

-   NAPA\_PartNumberToImage has a name, but it should be updated to
    "Part Number To Image"

    ![](../../Resources/Images/MPNotes/3.png)

3.  Classification Reference Types:

-   NAPA\_PartTerminologyListToNAPA\_PartTerm has no name - should be
    "Part Terminology List To NAPA Part Term"

-   NAPA\_PartTypeRelation has no name - should be "Part Type Relation"

-   TD\_ManufacturerToKBA has no name - should be "Manufacturer To KBA"

-   TD\_PartTypeGroupToPartType has no name - should be "Part Type Group
    To Part Type"

-   TD\_PartTypeRelation has no name - should be "Part Type Relation"

-   TD\_VehicleType(CV)ToKBA has no name - should be "Vehicle Type (CV)
    To KBA"

-   TD\_VehicleType(LCV)ToKBA has no name - should be "Vehicle Type
    (LCV) To KBA"

-   TD\_VehicleType(PC)ToKBA has no name - should be "Vehicle Type (PC)
    To KBA"

-   NAPA\_ApplicationToOption1 has a name, but it should be updated to
    "Application To Axle"

-   NAPA\_ApplicationToEngine has a name, but it should be updated to
    "Application To Engine"

-   NAPA\_ApplicationToSubmodel has a name, but it should be updated to
    "Application To Submodel"

-   NAPA\_ApplicationToTransmissionType has a name, but it should be
    updated to "Application To Transmission Type"

-   NAPA\_ApplicationToYear has a name, but it should be updated to
    "Application To Year"

-   NAPA\_SisterVehicle has a name, but it should be updated to "Sister
    Vehicle"

-   NAPA\_ValidVehicleToAxle has a name, but it should be updated to
    "Valid Vehicle To Axle"

-   NAPA\_ValidVehicleToEngine has a name, but it should be updated to
    "Valid Vehicle To Engine"

-   NAPA\_ValidVehicleToTransmissionType has a name, but it should be
    updated to "Valid Vehicle To Transmission Type"

    ![](../../Resources/Images/MPNotes/4.png)

4.  Product to Classification Link Types

-   TD\_SupplierArticleToUniversalGA has no name - should be "Supplier
    Article To Universal GA"

-   NAPA\_ProductToMPCC has a name, but it should be updated to "Product
    To MPCC"

    ![](../../Resources/Images/MPNotes/Product%20to%20classification%20link%20rename.png)

PRODOC note: RDCUST-2054Updated TecDoc Easy Setup to add the STEP Name
for root objects

Previously, certain TecDoc root objects didn\'t have a STEP Name. TecDoc
Easy Setup has been updated to add the STEP Names to the objects. The
updates are part of Automotive - TecDoc Model \> 1. Configure TecDoc
Data Model Easy Setup.

The root Classification object that had the STEP Name updated is:

-   TecDoc Assets Root (ID=TD\_TecDoc\_Assets\_Root)

The root Entity objects that had the STEP Names added are:

-   TecDoc Manufacturer Root (ID=TD\_TecDocManufacturerRoot) and TecDoc
    Resource Root (ID=TD\_TecDocResourceRoot)

The root Product object that had the STEP Name added is:

-   TecDoc Supplier Root (ID=TD\_DS\_Supplier Root)

**Existing implementations:** Please make these changes manually by
updating the STEP Names for the root classification objects listed
above.

PRODOC note: RDCUST-2538Updated TecDoc Easy Setup to clean up LOVs that
are created by Easy Setup

TecDoc Easy Setup has been updated to change some LOV names and create
some LOVs in a different LOV Group to make it look cleaner.

The update can be applied by running Automotive - TecDoc Model \> 1.
Configure TecDoc Data Model Easy Setup.

The LOV Group and LOVs that had the STEP Names updated are:

-   TecDoc LOV Group (ID=TD\_Top\_Level\_Lov\_Group), LOV-Comparative
    Manufacturer (ID=TD\_LOV-Comparative-Manufacturer), and LOV-OE
    Manufacturer (ID=TD\_LOV-OE-Manufacturer)

Eight LOVs are now created under the TD\_TecDocLOV group:

-   TD\_LOV-AttributeValidFor, TD\_LOV-LinkTargets,
    TD\_LOV-Comparative-Manufacturer, TD\_LOV-Country Code,
    TD\_LOV-OE-Manufacturer, TD\_LOV-213, TD\_LOV-214, and TD\_LOV-216

LOV Group \'Display Condition LOV\' (ID=TD\_DS\_LOV) is no longer
created by Easy Setup.

**Existing implementations:** Please make these changes manually by
updating the STEP Names for the LOVs, moving the LOVs, and deleting the
TD\_DS\_LOV group.

PRODOC note: RDCUST-2592/2593/2634Updated TecDoc Easy Setup Article
Number to be Specification attribute and add a warning for attributes
that have changed Type

Easy setup for TecDoc has been updated to change attribute with
ID=TD\_ATTR\_ArtNr from Description to Specification Type. Also, if a
user changes the type for an attribute that is created through Easy
Setup from Description to Specification, then a warning will appear
indicating that the, \'Attribute \[ID\] has been manually modified to be
a Specification attribute rather than a Description attribute.
Therefore, it cannot be made valid on the non-product object type.\'

PRODOC note: RDCUST-1089Updated TecDoc Easy Setup to add link types and
Axle object types as assemblies to Application Model component

TecDoc Easy Setup has been updated to add Axle object types as
assemblies, and \'Supplier Article to Axle\' and \'Supplier Article To
CV Producer\' as application to assembly link types in Automotive -
Application Model component.

The updates can be applied by running Automotive - TecDoc Model \> 3.
Configure TecDoc Types for Application Editor Easy Setup.

PRODOC note: RDCUST-2615Updated TecDoc Easy Setup to no longer add
Business Condition to Reference and Supplier workflows

Previously, TecDoc Easy Setup created the Reference and Supplier
workflows with a Start Condition that contained a Business Rule that
looks for a specific Final state in the workflow. If the specified state
does not exist in the Reference workflow, this would prevent the
Supplier import to be started. TecDoc Easy Setup has been updated to no
longer add the Business Rule to the Start Condition in the Reference and
Supplier workflows.

The start condition rule is still available and can be found under the
\'TecDoc\' Business Condition menu if a user wants to manually create a
business rule that controls when to import reference and supplier data.

**Existing implementations:** Please make these changes manually by
going to the TecDocReferenceImport and TecDocSupplierImport workflows
and removing the Business Rule from the Start Condition field.

PRODOC note: RDCUST-2518Updated TecDoc component model to no longer
mention \'attribute block object types\' in Linkage Source aspect

Since there is no concept of an attribute block any longer in the latest
STEP release, the TecDoc component model Configuration description has
been updated for Linkage Source aspect to no longer mention \'attribute
block object types.\'

PRODOC note: RDCUST-2580Fixed TecDoc Reference data load to make it
possible to run Business Rules

Previously, setting a change flag business rule in the TecDoc Reference
data importer would generate an error because some files were generated
with data after the child item in the STEPxml. The error that was
encountered was: Import encountered node data after node children while
using Business Rules. TecDoc Reference data importer has been fixed to
make it possible to run Business Rules so that the data and object
elements are created in the correct order in the STEPxml.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.7.spr**

Note that the above recipe is compatible only with the STEP 8.3 baseline
(**to:step/trailblazer/step-8.3.spr**).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
