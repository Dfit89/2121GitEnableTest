---
description: 'Automotive Solution: PMDM for Automotive 8.3 MP1 Patch
  Notes'
title: PMDM for Automotive 8.3 MP1 March 2018 Maintenance Patch Notes
---

PMDM for Automotive 8.3 MP1 Patch Notes {#pmdm-for-automotive-8.3-mp1-patch-notes .MPN}
=======================================

Release Date: March 29, 2018 {#release-date-march-29-2018 .MPN}
----------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: MEDU RDUCST- New Application Manager

With PMDM for Automotive 8.3 MP1, we are excited to introduce the new
Application Manager. It is faster and easier to use than its
predecessor, Application Editor. Application Manager allows Web UI users
to search, view, create, edit, and delete part application data. Users
can also export reports to Excel using the new Application Coverage
Report button, and manage interchange data using improved features
within the results table. For more information, see the **Application
Manager** topic ([here]{.mcFormatColor style="color: Blue;"}) within the
**Automotive Reference Guide**.

![](../../Resources/Images/MPNotes/Application%20Manager%20Page.png)

![](../../Resources/Images/MPNotes/Application%20Manager%20Page.png)

 

 

Improved accuracy when searching for missing applications

Missing Coverage accuracy has been improved by taking both the Condition
and Part Type values into consideration.

PRODOC note: MEDU RDUCST-2732 2713Previously, when searching for missing
applications within the Application Manager, conditions for specific
part types were not considered, resulting in the display of invalid
missing application records. For example, when searching for spark plugs
for a 2013 Audi A3, the results table would list both Gas and Diesel
engines, even though Diesel engines do not use spark plugs, and are
invalid in the search results. Now, we have improved the missing
application search by introducing a Business Condition plugin (\'Check
path for missing application\') where a validation path can be
configured so that the invalid missing applications for a specific part
type are filtered away, and only valid values are returned.

PRODOC note: MEDU RDCUST-2713 This portion removed and replaced with the
above per NIFE Additionally, our previous application data model did not
include any information to indicate that certain part types are never
needed for certain vehicles, and as a result the Application Manager
could display missing applications erroneously. Now, we have improved
the application data model to include a relationship between conditions
on applications and different configurations of vehicles. This allows
the Application Manager to search for applications with conditions for
all sub models. For example, when searching for spark plugs for a 2013
Audi A3, the result table will list both Gas and Diesel engines, since
Diesel engines do not use spark plugs, this is inaccurate. When the new
\'Missing Application Conditions\' attribute is used in conjunction with
the new \'Check path for missing application\' business condition, and a
validation path, the results will not display the inaccurate option.

PRODOC note: MEDU RDUCST-2734, 2738,2812, 2811 New Application Coverage
Report

Within the new Application Manager, you will find the new Application
Coverage Report that allows users to export missing and/or existing
application data into an Excel spreadsheet (XLSX file type). The
Application Coverage Report includes the same column headings found in
the search results table, therefore the Web UI designer can be used to
easily add or remove the display of columns. Once the \'Report\' button
is clicked, a background process is initiated, and a notification
displays informing users of the linked background process ID, and that
the process has started. For more information, see the new **Application
Manager Application Coverage Report** topic[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: RDCUST-2204 2205 Improved how users add, delete, and edit
AutoCare qualifiers in Application Manager

Improvements have been made allowing users to easily add, delete, and/or
edit AutoCare qualifiers within the Application Manager results table.
Previously, users could only view Qualifiers in the results table. Now,
when the results table is populated, users can navigate to a cell within
the Qualifiers column and either double click with their mouse pointer
(or click the Enter key on their keyboard) to display the Value editor.
Within the Value editor, the \'Add Qualifier\...\' link can be clicked
to display a \'Select qualifier\' dialog, where users can browse or
search for the necessary Qualifier, and then click the OK button to save
the selection.

PRODOC note: RDCUST-2768 Updated VCdb importer to better handle model
IDs

Previously, the VCdb importer would create the Model ID without
considering the Make. This was an issue for those Model Names that occur
across multiple Makes, because it resulted in the Models for multiple
makes being referenced to one make classification folder.

For example, the 200 Model is offered by many different manufacturers
(i.e., Audi, Chrysler, Griffith, Mercedes-Benz, Packard). Upon import,
the Audi 200 would be created as a child classification folder beneath
the Audi classification folder (since it was the first make with the 200
model listed within the import). Then, when the Chrysler 200 was
processed, it would erroneously be added to the Audi 200 classification
folder.

Now, the importer considers the make in the Model ID structure, and the
Model Names that occur across multiple makes are properly created within
their own make classification folder.

The new Model ID structure is: AC\_Model\_\[MakeID\_\[ModelID\]. For
example, the Chrysler 200 Model ID = AC\_Model\_39\_975.

**Existing Implementations**: Complete the steps below.

1.  If existing classification references to VCdb objects exist, then
    export those.
2.  Manually delete the VCdb structure.
3.  Import the VCdb file so that the Model objects are created using the
    new ID structure.
4.  If existing classifications were exported in step 1 above, be sure
    to import them now.

Because there are no references linked directly to the Model objects
(only to Base Vehicle children and Vehicle objects), those IDs will
remain the same.

PRODOC note: MEDU RDCUST-2724 New \'VCdb Year\' attribute for the VCdb
importer

Now AutoCare Easy Setup creates a new attribute \'VCdb Year\'
(AC\_VCdbYear). This attribute allows the year data for the AutoCare
base vehicles to be set by populating \'VCdb Year\' (AC\_VCdbYear)
attribute with data from the VCdb import.

This update is part of Easy Setup via **Automotive - AutoCare Model \>
1. Configure AutoCare Data Model.**

**Existing Implementations**: Run the AutoCare Easy Setup step 1
\'Configure AutoCare Data Model\' to automatically create the new
attribute, and automatically make it valid for the Base Vehicle
classification object type.

PRODOC note: MEDU RDCUST-2073 Updated PAdb Importer to handle
hierarchical LOV filtering

Previously, the PAdb import did not include hierarchical LOV filtering.
Now, once a PAdb import is run, the attributes are created, and linked
to the appropriate part terminology classifications. This allows for the
available LOV values to be filtered based on the part type that the
attribute references.

PRODOC note: RDCUST-2222 Updated PAdb Importer to set the PADescr value
as the attribute help text metadata for the part

Previously, when a PAdb file was imported, the Part Attribute
Description \[PADescr\] within the PartAttributes.txt file was ignored.
Now, when a PAdb file is imported, the values found within the
\'PADescr\' parameter are set as the respective part\'s attribute help
text \[AttributeHelpText\], as shown below.

![](../../Resources/Images/MPNotes/1.png)

![](../../Resources/Images/MPNotes/1.png)

PRODOC note: MEDU RDCUST-2722Updated PIES Exporter with mandatory field
validation

Previously, when using the Export Manager to create a PIES export, it
was possible to create an export without the required information.
Because no mandatory field validations were in the Export Wizard, the
export would be allowed to complete successfully even though the content
in the delivered file would eventually fail PIES XSD validation when the
file is used to by the importer.

Now, the Export Manager will only enable the \'Next\' and \'Finish\'
buttons when all the mandatory fields are populated, and at least one of
the Brand Owner DUNS or GLN fields are populated with the correct number
of characters. The \'Brand Owner DUNS\' value must be between 9 and 13
digits; whereas the \'Brand Owner GLN\' value must have 13 digits.
Additionally, the required fields will display a red fill until the
correct number of characters have been entered.

PRODOC note: MEDU RDCUST-2007 Improved ACES Importer and Exporter to
handle the order of multiple Notes / Comments

It is common for applications to have more than one Note / Comment, and
for the output order of these comments to matter. To handle this, the
metadata attribute (DisplaySequence) is now made valid for the necessary
reference (AC\_ACESApplicationToApplicationNote) during the Easy Setup
steps. The ACES Importer now reads the order of the Notes / Comments,
and applies the corresponding number to the Display Sequence metadata
attribute on the reference between the application record and the
comment. Additionally, the ACES Exporter now inserts the Notes /
Comments in the order indicated.

In the example below, the ACES XML file is shown above the workbench.
Since the \'OE Quality\' Note is listed before the \'80c Mounts in
Radiator for Trans Oil Cooler\' Note within the XML file, the \'OE
Quality\' Target object is listed with a Display Sequence of \'1,\' and
the \'80c Mounts in Radiator for Trans Oil Cooler\' Note with a Display
Sequence of \'2\' within the ACES Application To Application Note
Reference Type within the workbench.

![](../../Resources/Images/MPNotes/ACESNotesOrder.png)

![](../../Resources/Images/MPNotes/ACESNotesOrder.png)

**Existing Implementations**: Run the AutoCare Easy Setup step 1.
Configure AutoCare Data Model to automatically update the metadata
attribute Display Sequence (DisplaySequence) validity.

PRODOC note: MEDU RDUCST-2316 Added XSD validation to PIES and
ACES Exporters

Previously, the PIES and ACES Exporters did not contain any XSD
validation against the PIES and ACES specifications, so a file would be
exported even if required data was missing. For example, for PIES
packaging dimensions, if Height value was missing, the part would still
be exported with the Length and Width values, even though Height is
required. If the same exported file was imported into STEP, it would
fail validation because the Height value was missing.

Now, the PIES and ACES Exporters validate against the PIES and ACES XSD.
When errors do occur, they are listed in the Background Process
Execution report. To accomplish this, a new parameter (Deliver a file if
there are validation errors?) has been added to the PIES and ACES export
wizards. The parameter defaults to \'no.\'

When the parameter is set to \'no,\' the following will occur:

-   If XSD validation errors are encountered in the export, then the
    errors are listed in the Background Process Execution Report. The
    errors will include the ID of the object that failed XSD validation
    and which requirement it failed on.
-   A file will not get delivered with objects that meets XSD
    validation.
-   The Background Process will have a status of \'failed.\'

When the parameter is set to \'yes,\' the following will occur:

-   If XSD validation errors are encountered in the export, then the
    errors are listed in the Background Process Execution Report. The
    errors will include the ID of the object that failed XSD validation
    and which requirement it failed on.
-   A file will get delivered with objects that meets XSD validation.
-   The Background Process will have a status of \'succeeded.\'

PRODOC note: RDCUST-2799 Updated NAPA Easy Setup, Application Importer,
and Application Exporter to properly handle the order of Comments

Previously, when more than one Comment existed for an application, the
Comments would be displayed in alphabetical order when viewed in
workbench, or brought into a table set up for print. Now, to define the
display order for Comments based on the data that is provided in the
application import file, the following changes have been made:

-   Updated Easy Setup action for Automotive - NAPA Model \> 1.
    Configure NAPA Data Model to make the Display Sequence
    (DisplaySequence) attribute valid for the NAPA\_ApplicationToComment
    Product Reference Type, and the NAPA Interchange Comment
    (NAPA\_InterchangeComment) attribute valid for the
    NAPA\_ProductToInterchangeProduct reference.
-   Updated NAPA Application Importer to assign a sequence number
    starting with \'1\' to Display Sequence (DisplaySequence) attribute
    on the Application To Comment reference based on the order that the
    comment is listed in the import file.
-   Updated NAPA Application Exporter to export the comments in the
    order stored in the Display Sequence (DisplaySequence) attribute on
    the product reference, rather than in the order stored in the
    database.
-   **Existing Implementations**: Run the Easy Setup action for
    Automotive - NAPA Model \> 1. Configure NAPA Data Model or manually
    update the Display Sequence (DisplaySequence) attribute to be valid
    for the NAPA\_ApplicationToComment Product Reference Type, and the
    NAPA Interchange Comment (NAPA\_InterchangeComment) attribute to be
    valid for the NAPA\_ProductToInterchangeProduct reference.

 

 

PRODOC note: RDCUST-2814 Updated NAPA Easy Setup and NAPA Vehicle
Importer to utilize the NAPA Year attribute with LOV validation

Previously the NAPA Year attribute was not required to use the LOV
validation type. However, this caused problems within the Application
Manager Year search box. The following changes have been made:

1.  NAPA Easy Setup action creates a new LOV with the following
    configurations: ID = NAPA\_YearLOV, Name = NAPA Year LOV, Validation
    Base Type = Number, Allow Users to Add Values = Yes, Mask = 9999.
2.  NAPA Easy Setup action creates the NAPA Year (NAPA\_Year) attribute
    with \'List Of Values\' validation using the NAPA\_YearLOV.
3.  NAPA Vehicle Importer applies the year value from the
    NapaValidVehicleMaster.txt file (field \#6) to the NAPA Year
    (NAPA\_Year) attribute on the NAPA Year (NAPA\_Year) object type.

**Existing Implementations**: In order to avoid single update mode, the
following needs to be done manually:

1.  Run the Easy Setup actions for the NAPA standard.
2.  Duplicate the existing NAPA Year (NAPA\_Year) attribute, and give
    the new attribute the following: ID = NAPAYear2, Name = NAPA Year 2.
3.  Make the NAPA Year 2 (NAPAYear2) attribute Externally Maintained,
    and change the Validation Base Type to List Of Values using the new
    NAPA\_YearLOV.
4.  Change Externally Maintained back to \'No.\'
5.  Run a bulk update to merge the values from NAPA\_Year to NAPAYear2.
6.  Switch IDs between the two attributes so that NAPA\_Year now uses
    the LOV.
7.  Force Delete the NAPAYear2 attribute that used to be the NAPA\_Year
    with Number Validation Base Type.
8.  Change the Name of NAPA Year 2 to NAPA Year.

PRODOC note: RDCUST-2699 Improved the display of the Web UI Title during
Easy Setup for each standard, and Login for each default Web UI

Previously when the step 2 Configure \[standard\] Import Process was
selected, the confirmation dialog used the ID of the Web UI, instead of
the Name, this made it difficult to read. Now Easy Setup uses the Name.
In the example below, step 2 for the AutoCare standard has been
selected, and the dialog displays an easy-to-read name of what is being
created.

![](../../Resources/Images/AppMgr/AC2.png)

Additionally, the Web UI Login screen Web UI title parameter has been
updated so that once the Web UI is created, the login prompt
automatically displays with the following title: \[Standard\] Web UI. In
the example below, the AutoCare Web UI login screen is displayed on the
left using the value within the Web UI Title parameter found within the
Web UI designer Login Screen Properties, displayed on the right.

![](../../Resources/Images/AppMgr/Web%20UI%20Login%20AutoCare.png)

![](../../Resources/Images/AppMgr/Web%20UI%20Login%20AutoCare.png)

**Existing implementations:** Please access the Web UI Title Parameter
within each of your Web UIs and edit the parameter value accordingly.

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST-2819 Corrected Export Manager\'s display of
parameters

Previously, when step 3 of the Export Manager was configured to use an
\'Excel\' format, but later changed to a different format (i.e.,
AutoCare PIES 6.5 Exporter), the parameters displayed on step 5 were not
updated to the newly selected format. Now, the Export Manager allows
users to change the format selection on step 3 of the importer, and see
the correct parameters on step 5.

### AutoCare Standard

PRODOC note: RDCUST-2781Corrected PIES Importer \'context\' method

Previously, when the \'Delta calculation method\' parameter in PIES
import workflow was set to \'context,\' and a PIES file included the
\<PriceSheets\> segment containing attributes that do not exist in STEP,
the import validation failed. Now the importer will create the new
pricing attribute group and attributes, so that the importer can
complete successfully.

PRODOC note: RDCUST-2751 Corrected PIES Importer interchange section

A missing tag was added to the PIES XML file to handle the error caused
by the Interchange segment.

**HOTFIX:** A hotfix has been created to address this issue for the
following versions only: step-8.2-mp3-2017-11-15-12-24-52 and
automotive-7.0.6. The hotfix can be applied using the following recipe:

``` {.PreIndent space="preserve"}
to:hotfix/303/issue-303114-HOTFIX-2237.spr
```

PRODOC note: RDCUST-2700 Corrected handling of PIES and ACES files that
contain the same company name

Previously, when ACES and PIES files had the same company name, upon
import an error would occur causing the BGP to fail. This was caused by
the ID Prefix for both importers being set to \'AC\_.\' This has been
corrected by updating Easy Setup to set the ID Prefix for the AutoCare
ACES IIEP to \'ACES,\' and the AutoCare PIES IIEP to \'PIES.\'

**Existing Implementations**: Existing AutoCare ACES and PIES IIEPs can
be deleted, and Easy Setup can be used to create them with the
appropriate ID Prefixes, or the following changes can be made manually.

1.  Go to workbench \> System Setup \> Inbound Integration Endpoints \>
    Edit the **AutoCare ACES Inbound Endpoint** or the **AutoCare PIES
    Inbound Endpoint**.

2.  Use the **Next** button to access step 5 \'Configure Processing
    Engine.\'

3.  Within the ID Prefix parameter enter \'**ACES**\' or \'**PIES**\'
    for the respective IIEPs.

    ![](../../Resources/Images/MPNotes/2700CorrectedACESandPIESPrefixID.png)

### NAPA Standard

PRODOC note: RDCUST-2714Updated NAPA Easy Setup to use the \'context\'
method when the workflows for the Application Importer and Interchange
Importer are created

Previously, NAPA Application Import and Interchange Import workflows
were set up to use the \'file\' method. Because NAPA application and
interchange files come from multiple sources, it is required that the
files are imported using \'context\' method for delta calculation so
that the data is compared against the database instead of the previously
imported file. Now, the NAPA Easy Setup action creates the importer
workflows using the \'context\' method.

**Existing Implementations**: Existing Application Import and
Interchange Import workflows should be deleted. Then Easy Setup can be
used to recreate them automatically with the appropriate delta
calculation method, or the following changes can be made manually.

1.  Go to workbench \> System Setup \> Workflows \> Edit the **NAPA
    Application Import workflow**.

2.  Select the Delta Calculation state \> Right-click \> Select **Edit
    State**.

3.  Select the \'On Entry\' tab \> Click the **edit button** for the
    business action, and the Edit Operation dialog will display.

4.  Populate the \'Delta calculation method\' parameter with
    \'**context**\' (as shown below).

5.  Click the **Save** button and close the Workflow Designer.

6.  Repeat these steps for the **NAPA Interchange Import workflow**.

    ![](../../Resources/Images/BRs/Delta%20calculation%20method%20context.png)

PRODOC note: RDCUST-2727Updated Supplier Data Importer error message to
better handle invalid LOVs

Previously, when an invalid LOV Value ID was supplied within the
NAPA Interchange import, a vague error message displayed and did not
include the invalid value ID. Now the error message displays with the
invalid value ID. For example, when the 979 LOV value is invalid, the
following error message displays: Error: The value for attribute
\'NAPA\_InterchangeComment\' on reference \'NAPA\_Product\_UJQUJ690648\'
\> \'NAPA\_InterchangeProduct\_001\' isn\'t valid (IllegalLOVValue: 979
for LOV: com.stibo.core.domain.impl.ListOfValuesImpl:
NAPA\_InterchangeComment).

### TecDoc Standard

PRODOC note: RDCUST-2813 Corrected export format display in Export
Manager

Previously, the TecDoc export format was not displaying in the Export
Manager dropdown. This is now fixed.

PRODOC note: MEDU RDUCST-2802 Corrected Supplier Importer \'context\'
method

Previously, when the \'Delta calculation method\' parameter in TecDoc
Supplier import workflow was set to \'context,\' and an import was run
with data that should no longer be active, the DeleteStatus change flag
was not populated. Now the importer will properly update the
DeleteStatus attribute to \'true.\'

PRODOC note: RDCUST-2409 Corrected TAF stacktrace error when files are
missing in the supplier import file

Previously, the following files were missing in the supplier package:
216, 225, and 226. This would cause a stacktrace error to occur during
conversion. These tables have now been removed from validation,
therefore the validation state no longer displays the \'TAF file(s) are
missing in supplier package: 216, 225, 226\' message.

Additionally, when the supplier data did not contain the 403 table, an
Error displayed within the Import Details screen. The error message was
\'TAF File(s) are missing in supplier package: 403.\' Now the import
process overview status and the Import Details screen display more
user-friendly text, as shown in the screenshot below.

![](../../Resources/Images/MPNotes/403.png)

 

 

PRODOC note: RDCUST-2686 Improved Reference and Supplier Importer
handling of digital assets

Previously, the TecDoc asset placeholder created by Supplier importer
did not have a STEP Name and the importer could not find the asset to
replace the content. Since the importer expected the asset\'s extension
field to be mandatory, this caused an unnecessary conversion error
regarding asset creation to occur. Now the importer properly creates the
STEP Name, and error handling has been added for the importer\'s digital
assets so that when an asset does not exist in a reference file, the
asset is no longer imported, and a helpful error message will display in
the background process details. In the example below, the new error
message is displayed within the \'Text\' column of the background
process details screen.

![](../../Resources/Images/MPNotes/TD%20Error%20handling%20Assets.png)

PRODOC note: RDCUST-2690Corrected import failure that occurred when the
same file was imported more than once

Previously, when the same file containing LOVs was imported more than
once, the subsequent imports would fail. This has been corrected by
adding the correct end tags for LOVs.

**Existing Implementations**: Additional steps are not necessary unless
your previous delta calculation file is in a failed state. If this is
the case, prior to importing, remove the delta files from the
StepXMLDeltaCalculationService folder, as well as the
ImportingFlowImportService folder on the STEP application server.

PRODOC note: RDCUST-2709Corrected Reference data importer to no longer
duplicate Language Dimension points

Previously, when TecDoc Reference import files contained different ID
and Name values for the same Language Number, the TecDoc Reference Data
Importer would create a new language context.

In the example provided below, three Reference Data import files, each
containing the Language Number 004 with three different ID and Name
values, have been imported. Because each import file contained different
ID and Name values for their occurrence of Language Number 004, three
different Dimension points were created: en, English, English (GB).

![](../../Resources/Images/MPNotes/Duplicated%20Language%20Number.png)

![](../../Resources/Images/MPNotes/Duplicated%20Language%20Number.png)

Now the importer will do the following:

-   If the Language Number value does not exist in STEP, then create a
    new Language Dimension point.
-   If the Language Number value does exist in STEP, and all data is the
    same as in the imported file, then do nothing.
-   If the Language Number value does exist in STEP, and metadata is
    different in the imported file compared to STEP, then update the
    metadata in the existing Language Dimension point.

**Existing Implementations**: Additional steps are not necessary unless
your import fails after update. If your Reference Data Importer fails
during conversion, please do the following:

1.  Delete all Language dimension points.
2.  Delete the Language Dimension LOV.
3.  Delete all files on the STEP application server in
    /workarea/background-processarea/TAFValidationService.
4.  Delete all files on the STEP application server in
    /workarea/background-processarea/TAFToStepXMLConvertService.
5.  Delete all files on the STEP application server in
    /workarea/background-processarea/StepXMLDeltaCalculationService.
6.  Delete all files on the STEP application server in
    /workarea/background-processarea/ImportingFlowImportService.
7.  Delete all files on the STEP application server in
    /upload/hotfolders/TecDocReferenceInputFolder/save.
8.  Use \'Force Delete & Purge\' on all controller entities in workbench
    under Import Flow Root \> TecDoc Reference.
9.  Run step 1 of TecDoc easy setup to create the TD\_ATTR\_BezNr
    attribute.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

Downloadable Documentation now available for Automotive

Users can now easily access the latest Downloadable PDF version of the
Automotive Quick Start Guide and the Automotive Reference Guide. These
can be found within Online Help \> Downloadable Documentation.

![](../../Resources/Images/MPNotes/DD.png)

All Automotive Release Notes and Maintenance Patch Notes now available
in the online help

Users can now easily search for and view the content available within
all of the Automotive Release and Maintenance Patch Notes. Additionally,
the content is now searchable. In other words, when the online help
search feature is used, and content within the Release and Maintenance
Patch Notes matches the search criteria, the content will now display
within the search results.

To view these within online help, navigate to the Automotive Solution
Enablement section and expand the Release and Patch Notes for PMDM for
Automotive section (or search for \'Automotive Notes\').

![](../../Resources/Images/MPNotes/OLH.png)

PRODOC note: MEDU RDCUST-2769 Documentation for changing application
names during import now complete

Application names can be automatically changed during import using a
JavaScript within a business action that is added to the Import State of
a workflow. Our documentation has been updated with detailed steps on
how to do this, including two usable examples of JavaScript.

A new topic titled **8. Specify Application Naming** **Convention** has
been added ([here]{.mcFormatColor style="color: Blue;"}) to the
**Automotive Quick Start Guide** to provide instructions on how to
implement this change.

ID Structures in Importers

The purpose of the ID Structures in Importers topic is to help users
better understand the required ID structures for the importers and other
components within the Automotive solution to function properly. Please
make sure you review the latest version of this, and have implemented
the most up to date ID Structures. For more information, see the ID
Structures in Importers topic within the .

Terminology

The purpose of the Terminology topic is to help users better understand
the language and labels used within the Automotive Solution. The
Terminology topic can now be found within the XXX.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.8.spr**

The above recipe is compatible only with the STEP 8.3 MP2 baseline
(to:step/trailblazer/step-8.3-mp2.spr).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
